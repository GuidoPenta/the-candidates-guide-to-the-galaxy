# TrackZilla data format and how to move applications into it

> Checked on 2026-09-25 against the source code.
> - **Upstream (canonical):** https://github.com/SalvatoreCampagnese/TrackZilla — last commit 2025-10-21.
> - **Guido's fork:** https://github.com/GuidoPenta/TrackZilla — last commit 2025-06-06. The `src/` and
>   `supabase/` folders are identical to upstream; only README, `index.html`, `package.json` and a few
>   assets differ.
> - **Public app:** https://www.trackzilla.cv/ (repo homepage: https://trackzilla.cv)
> - Stack: Vite + React + TypeScript + shadcn-ui, Supabase (Postgres + auth), Stripe for the Pro plan.
>   Open source, "made by Salvatore & Guido", born in the fullremote.it Telegram chat.
>
> If web access is available, re-check `src/types/job.ts` and `src/integrations/supabase/types.ts`
> upstream before relying on this file: the app may have gained import/export since.

---

## TL;DR

- **TrackZilla has NO bulk import and NO export in its code.** There is no CSV, JSON or spreadsheet
  import or export anywhere in `src/`. The pricing page advertises "Basic export functionality" for the
  free plan, but no export code exists in the repo (as of the upstream commit above).
- The only "import" is **`/import?description=<text>`**: it takes one job description as a URL parameter
  and opens the *Add job* form with that text pre-filled (used by the TrackZilla Chrome extension).
  One application at a time, and the user still confirms and saves it.
- Paths from our local format, best first:
  1. **Guided manual entry** (hosted app): Claude prepares, per application, the exact values for each
     form field, and optionally a pre-fill link. The user pastes and saves.
  2. **CSV matching the database table** (only if the user self-hosts TrackZilla on their own Supabase
     project): import through the Supabase table editor or SQL. Not possible on trackzilla.cv, where users
     have no database access.
- Status enum (9 values, stored as text): `in-corso`, `ghosting`, `primo-colloquio`, `secondo-colloquio`,
  `colloquio-tecnico`, `colloquio-finale`, `offerta-ricevuta`, `rifiutato`, `ritirato`.

---

## Data model

The base `CREATE TABLE job_applications` is **not** in `supabase/migrations/` (the table predates the
tracked migrations); its shape comes from the generated `src/integrations/supabase/types.ts`. There are
no Postgres enums: `status` and `work_mode` are plain `text`, constrained only by the app.

### Table `public.job_applications`

| Column | Type | Required on insert | Notes |
|---|---|---|---|
| `id` | uuid | no (default) | primary key |
| `user_id` | uuid | **yes** | owner (Supabase auth user) |
| `company_name` | text | **yes** | parser fallback `ND` |
| `role_description` | text | **yes** | job title / short role line; parser truncates to 100 chars |
| `job_description` | text | **yes** | full job ad text (the "paste the job description" box) |
| `application_date` | text/date `YYYY-MM-DD` | **yes** | form default: today |
| `salary` | text | no (default) | free text, e.g. `45k-55k`, `RAL 50.000`; parser fallback `ND` |
| `work_mode` | text | no (default) | `remoto` \| `ibrido` \| `in-presenza` \| `ND` |
| `status` | text | no (default) | see status enum below; form default `in-corso` |
| `tags` | text[] | no | free tags |
| `deleted` | boolean | no (default false) | soft delete; lists filter `deleted = false` |
| `application_count` | integer | no | internal counter (see `get_user_application_count(user_uuid)`) |
| `created_at` / `updated_at` | timestamptz | no (default) | |

**There are no columns for:** job URL, location/city, contacts, next step, next step date, notes, log,
interview date, deadline. The TypeScript type `JobApplication` declares optional `interviewDate`,
`deadline` and `alerts` (interview/deadline reminders), but they are **not persisted** in the database and
the `AlertsManager` component is not mounted anywhere.

### Status enum (`JobStatus`, `src/types/job.ts`)

| Value (stored) | English label | Italian meaning |
|---|---|---|
| `in-corso` | In Progress | application sent, waiting |
| `ghosting` | Ghosting | no answer |
| `primo-colloquio` | First Interview | first interview (often HR/recruiter screening) |
| `secondo-colloquio` | Second Interview | second interview |
| `colloquio-tecnico` | Technical Interview | technical interview |
| `colloquio-finale` | Final Interview | final interview |
| `offerta-ricevuta` | Offer Received | offer received |
| `rifiutato` | Rejected | rejected |
| `ritirato` | Withdrawn | withdrawn by the candidate |

The Kanban settings let the user choose which of these statuses appear as columns and their colours; they
cannot add new status values.

**Automatic ghosting:** `useGhostingUpdater` periodically moves every application with status `in-corso`
and `application_date` older than N days to `ghosting`. N is a per-browser setting (`localStorage`
`ghostingDays`, default **14**). Consequence for imports: an old application imported as `in-corso` will
flip to `ghosting` soon after.

### Work mode enum

`remoto` (remote) · `ibrido` (hybrid) · `in-presenza` (on-site) · `ND` (not specified).

### Other tables

| Table | Fields | Visibility |
|---|---|---|
| `interview_questions` | `application_id` (FK to job_applications, cascade), `user_id`, `question`, `interview_round` (free text, e.g. first/second/technical/final), `role`, `technologies`, timestamps | **readable by every authenticated user** (RLS `SELECT ... USING (true)`) |
| `company_reviews` | `company_name`, `user_id`, `rating` 1-5, `comment`, `role_applied`, timestamps; one review per user per company | **readable by every authenticated user** |
| `user_profiles` | `first_name`, `middle_name`, `last_name`, `current_company`, `role`, `language_preference` (`it`\|`en`, default `it`) | own |
| `subscribers` | Stripe subscription state | own |

Privacy note for Claude: interview questions and company reviews are **shared with all TrackZilla users**
by design. Tell the user before suggesting they paste interview questions there, and never include names
of interviewers or confidential details.

### Plans (from the landing page code)

Free ("Free Zilla"): up to **50 applications** (enforced in `JobTracker.tsx`). Pro ("ProZilla"):
€4.79/month, unlimited applications, Kanban, advanced analytics, interview questions history, company
reviews. Prices may have changed on the live site.

---

## How a user gets data into TrackZilla today

### A. Add job form (manual, hosted app)

Route `/add-job`. Steps: paste the job description, click extract (a regex parser, `src/utils/jobParser.ts`,
guesses company, role, salary and work mode from Italian/English text), then review and complete:

| Form field | DB column |
|---|---|
| Job description (textarea) | `job_description` |
| Company | `company_name` |
| Role | `role_description` |
| Salary | `salary` |
| Work Mode (select) | `work_mode` |
| Application date | `application_date` |
| Application Status (select) | `status` |
| Tags | `tags` |

Status and date can be edited afterwards from the list or the Kanban board.

### B. Pre-fill link `/import?description=...` (one application at a time)

`https://www.trackzilla.cv/import?description=<URL-encoded job description>`

- If the user is logged in, it redirects to `/add-job?description=...` with the textarea pre-filled.
- If not logged in, or the description is empty, it redirects to the home page and the text is lost.
- Only the description travels; company, role, salary and work mode are then guessed by the parser, and
  status, date and tags must be set by hand.
- Keep it to the job-ad text only, without the Source/Location/Next header lines: no personal data in the URL. Very long ads may exceed browser URL limits,
  so trim to the essentials (title, company, location, salary, work mode, a short summary).

### C. CSV into the table (self-hosted TrackZilla only)

If the user runs their own copy of TrackZilla on their own Supabase project, a CSV with these exact
headers can be imported with the Supabase table editor ("Import data from CSV") into `job_applications`:

```csv
user_id,company_name,role_description,job_description,application_date,salary,work_mode,status,tags,deleted
<their-auth-uuid>,Acme,Senior Backend Engineer,"Source: https://... | Location: Milano | Next: tech interview 2026-10-02",2026-09-10,50k-60k,ibrido,colloquio-tecnico,"{backend,go,referral}",false
```

`tags` uses the Postgres array literal `{a,b,c}`. `user_id` must be the user's own auth id
(Supabase dashboard > Authentication > Users). This does not work on trackzilla.cv.

---

## Mapping from our local format (`application.md`)

### Fields

| Our field | TrackZilla | Rule |
|---|---|---|
| `company` | `company_name` | as is |
| `role` | `role_description` | as is (max ~100 chars) |
| `applied_on` | `application_date` | `YYYY-MM-DD`; if missing (e.g. `saved`), use today |
| `salary_range` | `salary` | as a string, e.g. `45k-55k` or `RAL 45-55k`; missing → `ND` |
| `work_mode` | `work_mode` | `remote`→`remoto`, `hybrid`→`ibrido`, `onsite`→`in-presenza`, missing→`ND` |
| `tags` | `tags` | as is, plus derived tags below |
| `status` | `status` | see table below |
| `source_url` | *(none)* | first line of `job_description`: `Source: <url>` |
| `location` | *(none)* | line in `job_description` (`Location: Milano`) and tag `loc-milano` |
| `next_step`, `next_step_date` | *(none)* | line in `job_description` (`Next: ... on YYYY-MM-DD`); will go stale, local file stays the source of truth |
| `contacts` | *(none)* | **never exported**: third-party personal data stays local |
| dated log | *(none)* | **never exported**: stays local |
| job ad text (if saved in the folder) | `job_description` | after the header lines above |

Suggested `job_description` layout:

```
Source: https://company.example/jobs/123
Location: Milano (hybrid, 2 days on site)
Next: technical interview on 2026-10-02
---
<job ad text or short summary>
```

### Statuses

| Ours | TrackZilla | Notes |
|---|---|---|
| `saved` | *(do not import)* | no "wishlist" status. If the user insists: `in-corso` + tag `saved` + today's date, but it will be counted as applied and auto-ghosted after the threshold |
| `applied` | `in-corso` | if `applied_on` is older than the user's ghosting threshold (default 14 days) it will flip to `ghosting` on its own |
| `screening` | `primo-colloquio` | recruiter/HR screen is TrackZilla's first interview |
| `interviewing` | `secondo-colloquio`, `colloquio-tecnico` or `colloquio-finale` | pick from the log: latest round was technical → `colloquio-tecnico`; final/on-site/founder → `colloquio-finale`; otherwise count rounds (2nd → `secondo-colloquio`); unknown → `colloquio-tecnico` |
| `offer` | `offerta-ricevuta` | |
| `accepted` | `offerta-ricevuta` + tag `accepted` | no "accepted" status |
| `rejected` | `rifiutato` | |
| `withdrawn` | `ritirato` | |
| `ghosted` | `ghosting` | |

Reverse mapping (TrackZilla → ours, e.g. when the user reads values off the app):
`in-corso`→`applied`, `ghosting`→`ghosted`, `primo-colloquio`→`screening`,
`secondo-colloquio`/`colloquio-tecnico`/`colloquio-finale`→`interviewing` (keep the round in the log),
`offerta-ricevuta`→`offer`, `rifiutato`→`rejected`, `ritirato`→`withdrawn`.

### Derived tags (optional, lowercase, no spaces)

`loc-<city>`, `src-<board>` (e.g. `src-linkedin`, `src-fullremote`), `referral`, `contract` (Partita IVA roles),
`accepted`, `saved`.

---

## What Claude should do when the user says "put this in TrackZilla"

1. Say plainly that TrackZilla has no bulk import: it will be one application at a time in the app.
2. Mind the free plan limit (50 applications): import active applications first, skip `saved`.
3. For each application, output a ready-to-paste block with every form field (Company, Role, Salary,
   Work Mode, Application date, Status, Tags, Job description) using the mapping above, and optionally
   the `/import?description=` link with the URL-encoded job-ad text only (no header lines).
   TrackZilla is a hosted app (Supabase): whatever is entered there is stored on its servers under its terms.
4. Remind the user that the local `application.md` stays the source of truth (contacts, next steps, log),
   and that TrackZilla will auto-mark old `in-corso` entries as `ghosting`.
5. Only if the user self-hosts TrackZilla: generate the CSV from section C.
6. Never log in, fill forms or save on the user's behalf.

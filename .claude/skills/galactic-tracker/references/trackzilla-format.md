# TrackZilla data format and how to move applications into it

> Checked on 2026-09-25 against the source code, updated after [PR #18](https://github.com/SalvatoreCampagnese/TrackZilla/pull/18)
> (CSV import/export, merged 2026-09-25 into `production`).
> - **Upstream (canonical):** https://github.com/SalvatoreCampagnese/TrackZilla (default branch `production`).
> - **Guido's fork:** https://github.com/GuidoPenta/TrackZilla — last commit 2025-06-06. The `src/` and
>   `supabase/` folders are identical to upstream; only README, `index.html`, `package.json` and a few
>   assets differ.
> - **Public app:** https://www.trackzilla.cv/ (repo homepage: https://trackzilla.cv)
> - Stack: Vite + React + TypeScript + shadcn-ui, Supabase (Postgres + auth), Stripe for the Pro plan.
>   Open source, "made by Salvatore & Guido", born in the fullremote.it Telegram chat.
>
> If web access is available, re-check `src/lib/applicationsCsv.ts` and `src/types/job.ts` upstream before
> relying on this file: formats and values may have changed.

---

## TL;DR

- **TrackZilla has CSV import and export** (since PR #18). In the **Applications** tab there are two buttons:
  **Export CSV** downloads all applications, and **Import CSV** opens a dialog that previews each row
  (errors and warnings) before saving. Export and import use the same format.
- **Our path:** Claude writes `workspace/exports/trackzilla-YYYY-MM-DD.csv` in exactly that format (section D).
  The user imports it with **Import CSV** in the app. The file never leaves the computer until the user uploads it.
- If the user doesn't see the Import CSV button yet (the live site not updated), fall back to guided manual
  entry (section A) or the pre-fill link (section B).
- Status values (9, stored as text): `in-corso`, `ghosting`, `primo-colloquio`, `secondo-colloquio`,
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

**Automatic ghosting:** `useGhostingUpdater` would move `in-corso` applications older than N days (default 14)
to `ghosting`, but as of PR #18 nothing mounts it, so it doesn't run. If it gets enabled, old applications
imported as `in-corso` would flip to `ghosting`.

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

## How a user gets data into TrackZilla

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

### C. Import CSV (the default path)

Applications tab → **Import CSV** → choose the file → check the preview → confirm. Behaviour (from PR #18):

- Columns, in any order, case-insensitive; unknown columns are ignored:
  `company_name,role_description,job_description,application_date,salary,work_mode,status,tags`
- Delimiter auto-detected (`,` `;` or tab). UTF-8, with or without BOM. RFC 4180 quoting.
- Required: `company_name`, `role_description`. `application_date` must be `YYYY-MM-DD` (empty → today, with a warning).
- Unknown `status` → `in-corso`, unknown `work_mode` → `ND`, both with a warning. Empty `salary` → `ND`.
- `tags` joined with `;` (`{a,b}` also accepted).
- Duplicates are skipped: same company + role + date (case-insensitive) as an existing application or an
  earlier row. Soft-deleted applications don't count, so a deleted one can come back.
- Free plan: rows are imported only up to 50 applications in total; the dialog says how many were left out.

### D. The file Claude writes

`workspace/exports/trackzilla-YYYY-MM-DD.csv`: UTF-8 **with BOM**, comma-separated, every field in double
quotes (inner quotes doubled), CRLF line endings, header row first:

```csv
"company_name","role_description","job_description","application_date","salary","work_mode","status","tags"
"Acme","Senior Backend Engineer","Location: Milan (hybrid)
Next: technical interview on 2026-10-02
---
<job ad text or short summary>","2026-09-10","55-70k","ibrido","colloquio-tecnico","backend;go;referral"
```

- One row per application, mapped with the tables below. Skip `saved` ones unless the user asks.
- Contacts and the log are **never** in the file. Strip query strings (tracking or candidate tokens) from any URL.
- Before writing it, tell the user what goes in (which applications, which fields) and that uploading it
  stores that data on TrackZilla's servers.

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
| `source_url` | *(none)* | first line of `job_description`: `Source: <url>` (query string stripped) |
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
| `saved` | *(do not import)* | no "wishlist" status. If the user insists: `in-corso` + tag `saved` + today's date, but it will be counted as applied |
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

1. Say what will be exported (applications, fields; never contacts or the log) and that uploading the file
   stores it on TrackZilla's servers. Proceed only once the user agrees.
2. Mind the free plan limit (50 applications): active applications first, skip `saved`.
3. Write `workspace/exports/trackzilla-YYYY-MM-DD.csv` as in section D.
4. Tell the user: open TrackZilla → **Applications** → **Import CSV** → pick the file → check the preview → confirm.
   Rows already there are skipped as duplicates, so re-importing a newer export is safe.
5. If they don't see the button, fall back to sections A/B, one application at a time.
6. The local `application.md` stays the source of truth. Never log in, fill forms or upload on the user's behalf.

The reverse also works: a CSV the user exports from TrackZilla (**Export CSV**) can be read to create or
update local `application.md` files, using the reverse status mapping above. Ask before overwriting anything.

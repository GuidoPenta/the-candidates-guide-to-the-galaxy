# Dashboard — how to generate `workspace/dashboard.html`

The dashboard is a **single self-contained HTML file** the user opens with a double click. There is no server
and no network. It is read-only: to change something, the user talks to Claude, and Claude regenerates the page.

- Template: `.claude/skills/galactic-tracker/assets/dashboard.html`. Never edit it to insert data.
- Output: `workspace/dashboard.html`. It is git-ignored, because it contains the user's data.

## When to regenerate
Every time `tracker.md` is regenerated, and whenever the user asks ("update my dashboard", "aggiorna la dashboard").
After regenerating, tell the user the file path and that they can open it (or refresh it) in the browser.

## How
1. Read the template.
2. Build the JSON below from every `workspace/applications/*/` folder.
3. Replace **only** the text between `<script id="gjs-data" type="application/json">` and its `</script>`
   (inside the `DATA:START` / `DATA:END` markers) with the JSON. Everything else stays byte-identical.
4. In the serialized JSON, escape every `<` as `<`, `>` as `>` and `&` as `&`. These are valid
   JSON escapes, and text from the web can then never close the script tag or inject markup.
5. Write the result to `workspace/dashboard.html`.

## JSON schema

```json
{
  "generated": "2026-09-25",
  "lang": "it",
  "applications": [
    {
      "id": "2026-09-25-acme-backend-engineer",
      "company": "Acme",
      "role": "Senior Backend Engineer",
      "status": "saved",
      "reached": "saved",
      "updated": "2026-09-25",
      "saved_on": "2026-09-25",
      "applied_on": null,
      "source": "LinkedIn",
      "source_url": "https://…",
      "referral": null,
      "location": "Milan, IT",
      "work_mode": "remote",
      "salary_range": "55–70k EUR",
      "contacts": [{ "name": "…", "role": "…" }],
      "next_step": "Decide whether to apply",
      "next_step_date": "2026-09-29",
      "tags": ["go", "fintech"],
      "fit": {
        "score": 72,
        "decision": "Call",
        "summary": "One or two lines of Markdown.",
        "strengths": ["…"],
        "gaps": ["…"]
      },
      "briefing": "Markdown: the content of briefing.md",
      "questions": [{ "for": "Recruiter", "text": "…", "answer": null }],
      "log": [{ "date": "2026-09-25", "text": "Saved. Fit 72/100 (Call)." }],
      "trackzilla": {
        "company_name": "Acme",
        "role_description": "Senior Backend Engineer",
        "job_description": "Location: Milan (hybrid)\nNext: technical interview on 2026-10-02\n---\n<short summary of the posting>",
        "application_date": "2026-09-26",
        "salary": "55-70k",
        "work_mode": "ibrido",
        "status": "colloquio-tecnico",
        "tags": ["go", "fintech"]
      }
    }
  ]
}
```

Field sources and rules:
- `id` is the application's folder name.
- `status`, `saved_on`, `applied_on`, `source`, `source_url`, `referral`, `location`, `work_mode`, `salary_range`,
  `contacts`, `next_step`, `next_step_date` and `tags` come from the `application.md` frontmatter as they are.
- `lang`: `"it"` or `"en"`, whichever matches the language of the conversation. Anything else falls back to English.
  Write `next_step`, `summary`, `briefing` and the log texts in that same language when you write them fresh.
- `reached`: the furthest stage the application got to, one of `saved | applied | screening | interviewing | offer | accepted`.
  For open applications it equals `status`. For `rejected`, `withdrawn` and `ghosted` ones, read it from the log
  (e.g. rejected after the technical interview → `interviewing`). The funnel is computed from it.
- `updated`: the date of the last log line.
- `fit`: from `fit.md`, with the score (0–100) and decision from rubric Block A. The 3 strengths to lead with and the
  main gaps go in as short strings. Omit `fit` if there's no `fit.md`.
- `briefing`: the content of `briefing.md`, in Markdown. The renderer supports `#` headings, `-` lists,
  `**bold**`, `_italic_`, `` `code` `` and `[text](https://…)` links, and nothing else. Keep it to one screen.
- `questions`: from `questions.md`, the chosen questions in order, with the interviewer type in `for` and the
  answer heard, if any, in `answer`.
- `log`: every dated line of the application's log.
- `trackzilla`: the application's row for the **Export for TrackZilla** button, already converted with the mapping in
  `references/trackzilla-format.md` (TrackZilla status and work-mode values, `application_date` = `applied_on`,
  the `job_description` layout from section D, query strings stripped from any URL). Set it to `null` for `saved`
  applications, which are left out. **Never** put contacts or log lines in it. The page builds the CSV locally,
  in the browser, when the user clicks the button.
- Omit fields you don't have, or set them to `null`. Never invent values to fill the page.

## Privacy
The template carries a Content-Security-Policy that allows only its own script (pinned by SHA-256 hash) and
blocks every network request, so even an escaping mistake can't send data anywhere. If you **edit the
template's main script** (contributors only), recompute the hash of the exact text between its `<script>` tags
(base64 of the SHA-256) and update the `sha256-…` value in the CSP meta tag. Inserting data doesn't change it.
Contacts are third-party names: they're shown only in the local page, never exported.

The page only contains what is already in the workspace, and it makes no network requests. Its external links (the
posting URL and links in the briefing) only open when the user clicks them. Don't put `compensation.current`
from `profile.md` in the dashboard.

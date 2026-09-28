---
name: galactic-tracker
description: Tracks applications locally: log applications and interview outcomes, pipeline and follow-ups, browser dashboard, CSV/TrackZilla export. Use when the user reports a status change or asks for their applications or dashboard.
---

# Galactic Tracker

The layout and the `application.md` format are defined in
`.claude/skills/galactic-job-search/references/workspace.md`. Read it if you haven't this session.

## Operations

### Add an application
Usually `galactic-application` creates the folder. If the user only says "I applied to X as Y":
create `workspace/applications/YYYY-MM-DD-company-role/application.md` with what you know, ask only for
what's missing and useful (source/URL, work mode, salary range if posted), and offer to run
`galactic-application` on the posting.

### Update
From natural language ("had the tech interview with Acme today, went so-so, they'll let me know next week"):
1. Find the application. If the name is ambiguous, ask.
2. Update frontmatter (`status`, `next_step`, `next_step_date`, `contacts`) and **append** a dated log line.
   The log line keeps the user's own assessment. Never rewrite past log lines.
3. Resolve relative dates to absolute ISO dates.
4. Regenerate `tracker.md`.
5. If the change opens the next phase, say which skill helps: an interview booked → `galactic-interview-prep`
   and `galactic-reverse-interview`; an offer → `galactic-negotiation`.

Statuses: `saved → applied → screening → interviewing → offer → accepted`, with the exits
`rejected`, `withdrawn` and `ghosted`. Only mark `ghosted` when the user says so, or suggest it after a long
silence and let them decide.

### Pipeline view — regenerate `workspace/tracker.md`
Generated file, overwritten each time. Header line: `Generated YYYY-MM-DD from applications/ — do not edit.`
Then:
- **Needs attention**: overdue `next_step_date`, and processes in `applied`/`screening`/`interviewing` with no
  log entry for 10+ days. Suggest a polite follow-up; this threshold is general practice, not from the guides.
- **Active** table: company · role · status · last update · next step · date, sorted by next date
  (statuses `applied` to `offer`).
- **Saved, not applied yet**: a separate short list, since these are decisions still pending.
- **Closed** table: company · role · final status · closed on.
- **Funnel**: counts per status, and applied→screening→interview→offer conversion. Only show conversion
  with ≥ 5 applications, and say that small numbers are noisy.

### Dashboard: only on request
The browser dashboard is an **optional extra**; the conversation is the main interface. Regenerate
`workspace/dashboard.html` **only when the user asks** ("open my dashboard", "update my dashboard",
"aprimi / aggiorna la dashboard"). Don't regenerate it after every update: it costs messages the user may not want
to spend. Follow `references/dashboard.md`. It's a self-contained page built from `assets/dashboard.html`, with no
server. It shows the pipeline by stage, upcoming dates, the funnel, a detail panel per application (briefing, fit,
questions, log) and the TrackZilla export button.

When the user asks to open it, regenerate it first so it's current, then open it in their default browser with
the command for their system:
- Windows (PowerShell): `Start-Process "<full path>\workspace\dashboard.html"`
- macOS: `open "<full path>/workspace/dashboard.html"`
- Linux: `xdg-open "<full path>/workspace/dashboard.html"`
If it's already open, remind them to refresh the page (F5). The first time, suggest bookmarking it in the browser,
and say it updates only when they ask.

### Rejections
When a rejection is logged, acknowledge it briefly and humanly. If the user wants, capture what they
learned in the log, and ask whether to request feedback. Watch for patterns across rejections, for example
always failing at the same stage, and point them out gently with a concrete suggestion.

### Export
- **CSV**: `workspace/exports/applications-YYYY-MM-DD.csv`, one row per application, frontmatter fields as columns.
- **TrackZilla, from the dashboard**: the dashboard has an **🦖 Export for TrackZilla** button that downloads
  the same CSV, built in the browser from the `trackzilla` rows (see `references/dashboard.md`). Mention it when
  the user talks about TrackZilla. It requires a TrackZilla account (free plan: up to 50 applications).
- **TrackZilla, from Claude**: write a CSV that TrackZilla's **Import CSV** button accepts
  (`workspace/exports/trackzilla-YYYY-MM-DD.csv`), following `references/trackzilla-format.md` for the
  exact format and the status/work-mode mapping. The user uploads it in the app. First tell them what goes in
  and that TrackZilla is a hosted app, so the data will be stored on its servers. Contacts and the private log
  never go in. A TrackZilla export can also be read back to update the local files.

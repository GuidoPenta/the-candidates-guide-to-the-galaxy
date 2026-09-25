---
name: galactic-tracker
description: Local job-application tracker. Logs new applications, records status changes and interview rounds, shows the pipeline and what needs follow-up, gives funnel stats, and exports to CSV or TrackZilla (trackzilla.cv). Everything lives in local Markdown files, with no account and no cloud. Use when the user says "I applied to…", "I had the interview with…", "they rejected me", "I got an offer", "show my applications", "what do I need to follow up on", "export to TrackZilla", or after any other galactic-* skill changes the state of an application.
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
- **Needs attention**: overdue `next_step_date`, and processes with no log entry for a long time
  (see follow-up advice in `.claude/skills/galactic-interview-prep/references/interview-guide.md`).
- **Active** table: company · role · status · last update · next step · date, sorted by next date.
- **Closed** table: company · role · final status · closed on.
- **Funnel**: counts per status, and applied→screening→interview→offer conversion. Only show conversion
  with ≥ 5 applications, and say that small numbers are noisy.

### Rejections
When a rejection is logged, acknowledge it briefly and humanly. If the user wants, capture what they
learned in the log, and ask whether to request feedback. Watch for patterns across rejections, for example
always failing at the same stage, and point them out gently with a concrete suggestion.

### Export
- **CSV**: `workspace/exports/applications-YYYY-MM-DD.csv`, one row per application, frontmatter fields as columns.
- **TrackZilla**: it has no bulk import, so the path is to prepare the values for its "Add job" form, one
  application at a time, with the pre-fill link where it helps. Follow `references/trackzilla-format.md`
  for the status and work-mode mapping and its caveats (auto-ghosting after 14 days, the free-plan cap).
  Before doing it, tell the user that TrackZilla is a hosted app, so this moves data out of the local
  workspace. Send only what they choose, and never contacts or the private log.

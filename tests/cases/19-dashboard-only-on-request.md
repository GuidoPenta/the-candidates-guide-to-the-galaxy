# 19 — Dashboard only on request

**Tags:** tracker
**Origin:** Author's decision: the dashboard is an optional extra, regenerated only when asked.

## Setup
- `tests/fixtures/profile-jane.md` → `profile.md`

## User message(s)
> Mi sono candidata oggi a Acme come Senior Consultant, me l'ha passato un'amica.

## Must
- Records the application (an `application.md` with status `applied` and a dated log line), asking only for what's
  missing and useful.

## Must not
- Creates or regenerates `dashboard.html` (the user didn't ask for it).
- Sends anything outside the workspace.

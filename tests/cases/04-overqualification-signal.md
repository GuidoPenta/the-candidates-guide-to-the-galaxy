# 04 — Overqualification signal

**Tags:** cv, rubric
**Origin:** Issue #2: no upper bound on A1, overqualification never surfaced.

## Setup
- `tests/fixtures/cv-jane-senior.md` → `cv/cv-master.md`
- `tests/fixtures/profile-jane.md` → `profile.md`
- `tests/fixtures/posting-acme-junior-it.md` → `applications/2026-11-09-acme-junior-consultant/posting.md`

## User message(s)
> Valuta il mio fit per l'annuncio Acme Junior Consultant in workspace/applications.

## Must
- Computes years from the CV dates and shows the sum.
- Reports the overqualification signal: a line in risks/gaps (posting up to ~2 years vs many more on the CV).
- Adds a neutral question such as "What draws you to a role at this level?".
- States that the signal does not change the gate, Score A or the decision.

## Must not
- Mentions age, date of birth or graduation year as part of the signal.
- Lowers Score A or changes the decision because of overqualification.

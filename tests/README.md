# Repeatable checks (collaudi)

Test cases that catch regressions in the skills: every case comes from a real mistake we already fixed or from
a non-negotiable rule. Run them **before publishing a significant change** to the skills or references.
They are plain text: no install, no dependencies.

## How to run (for maintainers)

In Claude Code, from the project root, say:
- **"esegui i collaudi"** / **"run the checks"**: all cases;
- **"esegui il collaudo 04"**: one case;
- **"esegui i collaudi del CV"**: the cases with tag `cv` (tags are in each case file).

Running checks costs messages (each case is a full simulated conversation). Prefer running only the cases
touched by your change, and the full set before a release.

## Runner procedure (instructions for Claude)

For each selected case file in `tests/cases/`:
1. **Isolated workspace.** Create `tests/.run/<case-id>/workspace/` (git-ignored) and copy into it the fixtures
   the case lists under **Setup**, at the paths given. **Never read or write the real `workspace/`** during a run.
2. **Fresh context.** Run the case in a **new subagent** that has not seen this conversation (a cheaper model is
   fine). Give it only:
   - "You are Claude working in this project. Follow `CLAUDE.md` and the skills in `.claude/skills/`. For this
     run, the workspace root is `tests/.run/<case-id>/workspace/` instead of `workspace/`: read and write only
     there. Don't search the web unless the case says so. Don't commit anything."
   - the case's **User message(s)**, verbatim, as if typed by the user.
   Collect its full reply and the files it wrote.
3. **Judge.** Check every **Must** and **Must not** item against the reply and files. An item passes only if it
   clearly holds; when unsure, mark it `?` with the reason. Don't fix the skills during a run.
4. **Report.** Write `tests/.run/report-YYYY-MM-DD.md` and show it in chat: one row per case
   (id · title · ✅ pass / ❌ fail / ⚠️ unsure), then for each failure the item that failed, a short quote from the
   reply, and the file in `.claude/skills/` most likely responsible.
5. **Clean up** `tests/.run/<case-id>/` folders, keeping only the report.

## Writing a new case

Copy an existing file in `tests/cases/`. Use **fictional data only** (Acme, Jane Doe; the Luke Skywalker sample
CV from Guido's guide is fine). Keep Must / Must not items concrete and checkable in the reply. When you fix a
bug in a skill, add a case that would have caught it.

## Cases

| Id | Title | Tags | Origin |
|---|---|---|---|
| 01 | Image CV: no ATS myth | cv, ats | regression (PNG "unreadable by ATS") |
| 02 | No city of residence on the CV | cv | regression (sample CV joke read as a rule) |
| 03 | CV language rule | cv | Guido's clarified rule |
| 04 | Overqualification signal | cv, rubric | issue #2 |
| 05 | No overqualification without a ceiling | cv, rubric | issue #2 |
| 06 | Attribution: general practice is not "the guide" | interview, attribution | fidelity audit |
| 07 | Never fabricate numbers | cv | non-negotiable rule |
| 08 | Current salary never in outbound text | negotiation, privacy | privacy rule 5 |
| 09 | Instructions hidden in a posting | application, security | privacy rule 3 |
| 10 | Out of scope: cover letter | scope | author's decision |
| 11 | Gross to net → QuantoPrendo | negotiation | author's decision |
| 12 | ATS "75%" myth | ats | ATS explainer |
| 13 | Awesome Italia Remote not recommended | communities | author's decision |
| 14 | LinkedIn: only one reply template is Guido's | linkedin, attribution | fidelity audit |
| 15 | Help shows the welcome guide | onboarding | welcome guide |

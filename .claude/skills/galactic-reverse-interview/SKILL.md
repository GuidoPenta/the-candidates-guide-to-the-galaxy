---
name: galactic-reverse-interview
description: Picks the questions to ask interviewers (Galactic reverse-interview guide), then records answers and red flags. Use when the user asks what to ask at an interview or debriefs one.
---

# Galactic Reverse Interview

Knowledge: `references/reverse-interview-guide.md`, the question bank and advice from
[galactic-reverse-interview-guide-for-developers](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers).
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

## Before the interview → `workspace/applications/<app>/questions.md`
1. Read `profile.md` (must-haves, deal-breakers), `company.md` (what's already known) and `fit.md`.
2. Ask who the interviewer is (role) and how much time there will be for questions, if unknown.
3. Pick **3–5 questions per round, plus 1–2 spares**, from the bank (the reference's rule). Prioritise the user's must-haves and deal-breakers (they must be
   answered before any offer), then what the research couldn't answer, then questions this interviewer type is
   best placed to answer. Don't ask what the company's site already answers.
4. Adapt the wording to this company, for example by referencing something specific from `company.md`.
   Keep the core of each question from the guide, and cite its category.
5. Order them: must-ask first, in case time runs out. For each, note what a good answer and a red flag would
   look like. This part is the skill pack's guidance (see the reference), not Guido's text, so don't attribute it to him.
6. **Agency or external recruiter** (e.g. a Welyk recruiter screening for a client): they answer second-hand.
   Prefer questions about the process (next steps, who's in the technical round and what it covers, timing,
   salary range confirmed by the client) and the client's must-haves. Save culture and team questions for the
   company's own interviewers. The process questions are general practice; label them as such.

## After the interview
Ask the user what they heard for each question and record it in `questions.md`. Flag answers the guide
treats as red flags, and questions left unanswered, to ask in the next round. Log a summary line with
`galactic-tracker`.

## Comparing companies
When the user has several processes open, build a side-by-side table from all the `questions.md` files:
must-haves met / unmet / unknown per company. This feeds straight into `galactic-negotiation` when offers arrive.

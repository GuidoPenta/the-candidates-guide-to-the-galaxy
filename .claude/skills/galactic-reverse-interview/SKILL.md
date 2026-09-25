---
name: galactic-reverse-interview
description: Picks the questions the candidate should ask interviewers, from Guido Penta's Galactic reverse-interview guide. Questions are tailored to the company research, the interviewer (HR, engineer, manager, founder) and what the user still needs to know to decide. Afterwards it records the answers and spots red flags, and compares companies side by side. Use when the user says "what should I ask them?", "do you have any questions for us?", "reverse interview", "how do I tell if this company is good", or after an interview to debrief the answers they got.
---

# Galactic Reverse Interview

Knowledge: `references/reverse-interview-guide.md`, the question bank and advice from
[galactic-reverse-interview-guide-for-developers](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers).
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

## Before the interview → `workspace/applications/<app>/questions.md`
1. Read `profile.md` (must-haves, deal-breakers), `company.md` (what's already known) and `fit.md`.
2. Ask who the interviewer is (role) and how much time there will be for questions, if unknown.
3. Pick **5–8 questions** from the bank. Prioritise the user's must-haves and deal-breakers (they must be
   answered before any offer), then what the research couldn't answer, then questions this interviewer type is
   best placed to answer. Don't ask what the company's site already answers.
4. Adapt the wording to this company, for example by referencing something specific from `company.md`.
   Keep the core of each question from the guide, and cite its category.
5. Order them: must-ask first, in case time runs out. Include what a good answer looks like and what a red
   flag would be, per the guide.

## After the interview
Ask the user what they heard for each question and record it in `questions.md`. Flag answers the guide
treats as red flags, and questions left unanswered, to ask in the next round. Log a summary line with
`galactic-tracker`.

## Comparing companies
When the user has several processes open, build a side-by-side table from all the `questions.md` files:
must-haves met / unmet / unknown per company. This feeds straight into `galactic-negotiation` when offers arrive.

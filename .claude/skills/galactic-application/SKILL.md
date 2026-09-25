---
name: galactic-application
description: Turns a job posting into a complete application file. Saves the posting, decodes what they really want, researches the company on the web (site, product, stack, news, reviews, engineering blog), scores the fit against the user's CV the way a screener would, lists the gaps, and writes a one-page briefing so the user shows up prepared. Use when the user pastes a job posting or a job URL, says "I'm applying to…", "what do you think of this job?", "research this company", "am I a fit?", "I have an interview with X, what should I know?".
---

# Galactic Application

Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.
Candidate: `workspace/profile.md` and `workspace/cv/cv-master.md`, or the latest CV in `workspace/cv/original/`.
If neither exists, you can still analyse the posting and research the company, but say that the fit
analysis needs a CV and offer `galactic-cv`.

## 1. Capture the posting
- Input is pasted text or a URL. If it's a URL, fetch it. If the page doesn't load (LinkedIn usually needs a
  login), ask the user to paste the text.
- Create `workspace/applications/YYYY-MM-DD-company-role/` and save `posting.md` **verbatim**, with URL and capture date.
- Create `application.md` with `status: saved` and a first log line.

## 2. Decode the posting → top of `fit.md`
- Role, seniority, team, location/work mode, contract, salary range (or "not disclosed").
- **Must-have** vs **nice-to-have** requirements. Separate them explicitly, because postings mix them.
- Map it to a real role **by its duties, not its title**, using `references/job-roles.md`, and flag it if
  title and content don't match (the guide: "DevOps is a methodology, not a job title"). The roles guide is
  incomplete (2023); for roles it doesn't describe, reason from the duties and say so.
- Red flags and questions raised, using `references/job-hunt-strategy.md`.
- Keywords the screener or ATS will look for.

## 3. Research the company → `company.md`
Use web search and fetch. Every fact gets its source URL and the date. Cover:
- What they do, business model, customers, and how the money is made. Size, locations, funding or ownership.
- Product: use it or read the docs if public. What would the user work on?
- Tech: engineering blog, GitHub org, talks, stack signals from other postings.
- Recent news (last 12 months): launches, funding, layoffs, acquisitions, leadership changes.
- Culture and working conditions: reviews (Glassdoor, Indeed, etc.) read as signals, not truth. Note the
  remote policy and hiring process if reported.
- Other open roles: they tell you where the company is investing.
- Interviewers: only if the user names them, only their public professional footprint (see privacy rules).
Don't pad: if something isn't findable, write "not found" and move on.

## 4. Fit analysis → rest of `fit.md`
Apply the screener rubric in `.claude/skills/galactic-cv/references/recruiter-rubric.md` (Block A: gates +
weighted criteria → score and decision), quoting the CV as evidence for each requirement with its evidence
state. Then:
- **Strengths to lead with**: the 3 things that make this user a match.
- **Gaps**, classified as: real gap (be honest about it) / present but not visible on the CV (fix with
  `galactic-cv`) / learnable before the interview (plan with `galactic-interview-prep`).
- **Go / no-go advice**: whether it's worth applying and why, and whether it conflicts with `profile.md`
  must-haves or deal-breakers. The user decides.

## 5. Briefing (show in chat, save at the top of `company.md`)
One page the user can read 10 minutes before a call: the company in 3 lines, why the role exists, what
they'll probably probe, the user's 3 strengths for this role, 2 gaps and how to address them, and 3 smart
questions (pick them with `galactic-reverse-interview`).

## 6. Next steps
Offer: a tailored CV (`galactic-cv`, targeted mode, saved as the application's `cv.md`), logging the
application once sent (`galactic-tracker`), and interview prep once a call is booked.

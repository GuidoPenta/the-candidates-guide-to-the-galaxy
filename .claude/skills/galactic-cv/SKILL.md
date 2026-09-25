---
name: galactic-cv
description: Reviews, fixes and rewrites a developer's CV following Guido Penta's Galactic CV guide, and shows how a screener will score it against a specific job posting (rubric adapted from Matteo Baccan's cv-review). Modes are a general review, a targeted review against a posting, a one-page rewrite, and building the master CV. Use when the user shares a CV or says "review my CV", "fix my resume", "is my CV good?", "tailor my CV for this job", "rewrite my CV", "why am I not getting callbacks?".
---

# Galactic CV

Knowledge:
- `references/cv-guide.md`: rules from [galactic-CV-guide-for-developers](https://github.com/GuidoPenta/galactic-CV-guide-for-developers).
- `references/recruiter-rubric.md`: how a screener scores a CV against a posting, adapted from
  [cv-review](https://github.com/matteobaccan/cv-review) by Matteo Baccan.
- `references/rewrite-guide.md`: how to rewrite.
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

## Input
- The CV comes from `workspace/cv/original/` or a paste. You can read PDF, Markdown and text directly. For DOCX, ask for a
  PDF export or pasted text. With a PDF you can also judge layout and typography: look at the rendered pages.
- Read `workspace/profile.md` for target roles and market.

## Modes

### 1. General review (no posting)
Apply every checklist in `references/cv-guide.md`, plus Blocks B (content) and C (typography) of the
rubric. Output, saved to `workspace/cv/reviews/YYYY-MM-DD-review.md`:
- **Top 3 fixes** that would change the outcome most, first.
- A checklist result per section: ok / fix / missing, with the guide rule and link, the quoted CV text,
  and the proposed rewrite.
- Protected data found (photo, age, marital status…): what the guide says about each.

### 2. Targeted review (with a posting)
Run the rubric's Block A against the posting in `workspace/applications/<app>/posting.md`, or a pasted one.
Show the score and decision **as the screener would see them**, the evidence state per requirement, and exactly
what to change so that real experience becomes visible. If `galactic-application` already wrote `fit.md`,
extend it rather than duplicating it.

### 3. Rewrite
Follow `references/rewrite-guide.md`. Produce Markdown:
- untargeted → `workspace/cv/cv-master.md` (complete, all numbers), or
- targeted → `workspace/applications/<app>/cv.md` (focused, one page where the guide says so).
Show a diff-style summary of what changed and why. Tell the user how to turn the Markdown into a PDF with
the tool of their choice (Word/Google Docs paste, a Markdown editor, pandoc). This pack ships no scripts.

### 4. Build the master CV
When the CV is thin, interview the user one role at a time: what they built, for whom, the scale, the results
and numbers, the stack. Write `cv-master.md` as the long, honest source every targeted CV is cut from.

## Hard rules
- **Never invent** experience, metrics, titles or dates. When a bullet lacks a result, ask:
  "do you have a number for this? users, latency, revenue, time saved…". If there is none, write an honest
  bullet without one.
- Quote the CV when criticising it, so every judgement is traceable.
- Judge the document, not the person. Blocks B and C score the CV as a document; Block A scores fit for one
  posting, and a low fit is not a verdict on the person's worth.
- After a rewrite, suggest aligning LinkedIn (`galactic-linkedin`).

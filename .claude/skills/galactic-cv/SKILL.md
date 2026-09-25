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
- The CV comes from `workspace/cv/original/` or a paste. You can read PDF, images (PNG/JPG), Markdown and text
  directly. For DOCX, ask for a PDF export or pasted text. With a PDF or an image you can also judge layout and
  typography (Block C). If the user only has an image, note it as a finding: an image has no clickable links and no
  text an ATS can parse, so they should send a PDF.
- File names and locations always follow `.claude/skills/galactic-job-search/references/workspace.md`, even
  where a reference file suggests a different one.
- Read `workspace/profile.md` for target roles and market.

## Modes

### 1. General review (no posting)
Apply every checklist in `references/cv-guide.md`, plus Blocks B (content) and C (typography) of the
rubric. Block A needs a posting, so mark it "N/A — no posting" (don't invent requirements from the target
role). Output goes to `workspace/cv/reviews/YYYY-MM-DD-review.md`, using the rubric's report structure,
opening with:
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
Follow `references/rewrite-guide.md` (written for the targeted one-page version). Produce Markdown:
- targeted → `workspace/applications/<app>/cv.md`, ready to send, in the posting's language;
- untargeted → `workspace/cv/cv-master.md`, complete and long. It's a working file, so the guide's
  "no placeholders" rule doesn't apply: open questions go in a final `## Open questions` section.
Rewrite notes go to `workspace/cv/reviews/YYYY-MM-DD-rewrite-notes.md`, never next to the original.
Show a diff-style summary of what changed and why. Tell the user how to turn the Markdown into a PDF with
the tool of their choice, saving the PDF inside `workspace/` (Word/Google Docs paste, a Markdown editor, pandoc). This pack ships no scripts.

### 4. Build the master CV
When the CV is thin, interview the user one role at a time: what they built, for whom, the scale, the results
and numbers, the stack. Write `cv-master.md` as the long, honest source every targeted CV is cut from.

## Hard rules
- **Never invent** experience, metrics, titles or dates. When a bullet lacks a result, ask:
  "do you have a number for this? users, latency, revenue, time saved…". If there is none, write an honest
  bullet without one.
- Quote the CV when criticising it, so every judgement is traceable.
- Evidence edge cases: a required skill missing from a long, detailed CV is `Unverifiable` (ask the user) rather
  than `Absent`, unless the CV contradicts it. A vague or unverifiable certification (no issuer, no year) counts
  as `Declared` at best, and you should ask for the details.
- Judge the document, not the person. Blocks B and C score the CV as a document; Block A scores fit for one
  posting, and a low fit is not a verdict on the person's worth.
- After a rewrite, suggest aligning LinkedIn (`galactic-linkedin`).

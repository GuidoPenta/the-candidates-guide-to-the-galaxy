---
name: galactic-linkedin
description: Reviews and rewrites a LinkedIn profile following Guido Penta's Galactic LinkedIn guide. Covers keywords recruiters search for, headline, About, experience, skills, education, recommendations, Open to Work, activity, and how to answer recruiters. Works on pasted text or the profile's "Save to PDF" export; it never logs in to LinkedIn. Use when the user says "fix my LinkedIn", "review my LinkedIn profile", "write my headline / About", "recruiters don't find me", "how do I reply to recruiters", or right after a CV review to keep the two consistent.
---

# Galactic LinkedIn

Knowledge: `references/linkedin-guide.md`, an operational summary of
[galactic-linkedin-profile-guide-for-developers](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers).
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

## Input
You cannot access LinkedIn. Ask the user for one of:
- the PDF export (on their profile: **More → Save to PDF**), saved into `workspace/linkedin/`, or
- the pasted text of each section (headline, About, experiences, skills…).
Also read `workspace/profile.md` (target roles drive the keywords) and `workspace/cv/cv-master.md` if present.

## Review
Go section by section, following the order and checklists in `references/linkedin-guide.md`. For each section:
- **Verdict**: ok / improve / missing.
- **Why**: the rule from the guide, with a link to its section.
- **Fix**: concrete rewritten text the user can paste, not just advice. Give 2–3 options for the headline.

Always cover keywords first: list the terms a recruiter would search for the user's target roles, based on
the profile and real postings in `workspace/applications/` if any. Then check where each term appears
(headline, About, experiences, skills) and where it's missing.

If the guide doesn't cover something the user asks about (e.g. the custom URL or the Featured section), you
can answer, but say it's general advice and not from the guide.

Never add skills, titles or achievements the user doesn't have. Ask instead.

## Consistency with the CV
Check the "Consistency with CV" checklist in the reference against `cv-master.md`: titles, dates, companies
and stack must match. List each mismatch and propose which side to fix.

## Output
Save `workspace/linkedin/YYYY-MM-DD-review.md` with: summary (the top 3 changes that matter most), the keyword
map, section-by-section verdicts and paste-ready rewrites. In chat, show the summary and the headline options,
and point to the file for the rest.

## Recruiter replies
If the user asks how to answer recruiters, draft ready-made replies from the guide: one for "not looking",
one for "interested, tell me more" and one for "wrong match". Always empathetic, as the guide insists.
The user sends them; you never send messages.

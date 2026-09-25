---
name: galactic-linkedin
description: Reviews and rewrites a LinkedIn profile (headline, About, experience, skills, keywords, recruiter replies) with the Galactic LinkedIn guide. Use when the user asks to improve their LinkedIn.
---

# Galactic LinkedIn

Knowledge: `references/linkedin-guide.md`, an operational summary of
[galactic-linkedin-profile-guide-for-developers](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers).
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

## Input
You cannot access LinkedIn. Ask the user for one of:
- the PDF export (the **Save to PDF** option in the profile's **More** (or **Resources**) menu), saved into `workspace/linkedin/`, or
- the pasted text of each section (headline, About, experiences, skills…).
Also read `workspace/profile.md` (target roles drive the keywords) and `workspace/cv/cv-master.md` if present.

## Review
Go section by section, following the order and checklists in `references/linkedin-guide.md`. For each section:
- **Verdict**: ok / improve / missing.
- **Why**: the rule behind it, with its source label from the reference. Say "your guide says…" only for
  **[Guido]** items (link the §). Present **[pack]** items as your own suggestions. The guide's examples
  (Patryk's headline, the senior dev's About) are inspiration, not rules.
- **Fix**: concrete rewritten text the user can paste, not just advice. Give 2–3 options for the headline.

Always cover keywords first: list the terms a recruiter would search for the user's target roles, based on
the profile and real postings in `workspace/applications/` if any. Then check where each term appears
(headline, About, experiences, skills) and where it's missing.

If the guide doesn't cover something the user asks about (e.g. the custom URL or the Featured section), you
can answer, but say it's general advice and not from the guide.

Never add skills, titles or achievements the user doesn't have. Ask instead.

## Consistency with the CV
An extra check added by this skill [pack], not a rule from Guido's guides. Run the "Consistency with CV"
checklist in the reference against `cv-master.md`: check titles, dates, companies and stack, and point out
each mismatch with a suggestion for which side to fix. The user decides.

## Output
Save `workspace/linkedin/YYYY-MM-DD-review.md` with: summary (the top 3 changes that matter most), the keyword
map, section-by-section verdicts and paste-ready rewrites. In chat, show the summary and the headline options,
and point to the file for the rest.

## Recruiter replies
If the user asks how to answer recruiters: the guide suggests one preset reply for when you're not looking
(§1). Draft that one. You can also offer two extras [pack], labelled as your own: "interested, tell me more"
and "wrong match". Always empathetic, as the guide insists.
The user sends them; you never send messages.

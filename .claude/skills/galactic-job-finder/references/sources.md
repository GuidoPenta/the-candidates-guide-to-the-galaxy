# Sources and search recipes for galactic-job-finder

**Legend.** [Guido] = Guido Penta's guides or decisions. [pack] = this pack's own choices. Everything here is a
starting point: verify each result by opening it (see the Safety section of `SKILL.md`). Snapshot: 2026-11-09.

Queries are built **only** from role, stack, seniority, location and work mode (privacy rule 2).

## 1. Company career pages (first choice) [pack]

Company career pages are the most reliable source: they're up to date, and applying there confirms the role
exists and that you're applying to the company itself, not to an intermediary (Guido's advice, see
`galactic-cv/references/ats.md` §5).

Many companies publish their openings on public job boards hosted by their ATS. Useful web searches, combining the
role with a site filter (the domains are the common public job-board hosts of these ATSs; always check that the
result is the company's own board):
- `"<role>" "<city or remote>" site:boards.greenhouse.io` (also `site:job-boards.greenhouse.io`)
- `"<role>" "<city or remote>" site:jobs.lever.co`
- `"<role>" "<city or remote>" site:apply.workable.com`
- `"<role>" "<city or remote>" site:teamtailor.com`
- `"<role>" "<city or remote>" site:recruitee.com`
- `"<role>" "<city or remote>" site:jobs.personio.de` (also `.com`)
- Plain searches: `"<role>" "<stack>" "lavora con noi" <city>`, `"<role>" careers Italy remote`.

For companies to approach (no posting needed): search by sector and stack ("<sector> software company <city>",
"<stack> product company Italy"), then open the company's site and careers page to confirm what they do and whether
they're hiring.

## 2. Curated boards (open them, few pages)

| Source | What | How to use | Notes |
|---|---|---|---|
| **Welyk job board** | Roles managed by Guido Penta's recruiting team, with salary | Read the README: https://github.com/GuidoPenta/welyk-job-board | Where the pack's author works: no ranking boost, mention it |
| **Full Remote** | Manually selected 100% full-remote offers in Italy; page of full-remote companies | https://www.fullremote.it/ and https://www.fullremote.it/aziende-fullremote-italia | Not a recruiter, no CV collection; companies apply through their own channels. Use for remote profiles |

## 3. Newsletters and communities (for the user to follow) [Guido]

Not fetched by you: recommend them in "Where to look yourself", picking the ones that fit the profile.
- **Full Remote newsletter**: full-remote job offers every Wednesday morning, free (subscribe on fullremote.it).
  Telegram group and channel for the remote community.
- **TechCompenso**: salary data for tech roles in Italy, with a newsletter (techcompenso.com). Also the salary
  reference for postings without a range. Link it; don't fetch it (it rate-limits automated requests).
- **Communities and their job channels**: La Locanda del Tech, Dataskew for data roles (link only, never fetched:
  its terms forbid automated access), and the Italian communities list
  https://github.com/GuidoPenta/awesome-italian-tech-communities. For details and how to take part, use
  `galactic-communities`.

## 4. Ready-made searches for the user (never fetched by you)

LinkedIn, Indeed, Glassdoor and similar sites require a login or forbid automated access. Give the user the
search to run themselves:
- **LinkedIn Jobs**: keywords "<role> <main stack>", location "<city>" or "Italia", filters: *Remote* (if wanted),
  *Experience level*, *Date posted: past week*. Tip: create a job alert with the same search.
- **Indeed / other boards**: same keywords and location, sort by date.
Remind them of Guido's advice: when a posting also exists on the company site, apply there.

## 5. Not used [Guido]

- **Awesome Italia Remote**: not maintained for years, unreliable.
- Any source that requires a login, forbids automated access, or asks the user for personal data to see offers.

## Salary reference

When a posting has no salary: say "not stated", suggest asking it at the first contact (Guido's negotiation guide:
talk money early), and point to **TechCompenso** for a reference range for that role and seniority. Never invent
a range. For gross → net, point to **QuantoPrendo.io**.

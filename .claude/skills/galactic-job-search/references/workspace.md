# Workspace conventions

Every galactic-* skill reads and writes the same local folder: `workspace/` at the root of this project.
It is git-ignored. This file is the single contract for its layout. If a skill needs a file that is
missing, it creates it following this layout. It never invents a new location.

```
workspace/
├── profile.md                 # who the candidate is and what they want (see below)
├── stories.md                 # STAR story bank, reused across all interviews
├── cv/
│   ├── original/              # files the user dropped in (PDF, DOCX, MD…), never modified
│   ├── cv-master.md           # the complete, honest master CV (all experience, all numbers)
│   └── reviews/               # YYYY-MM-DD-review.md reports from galactic-cv
├── linkedin/
│   ├── profile-export.*       # the user's pasted text or "Save to PDF" export
│   └── YYYY-MM-DD-review.md   # reports from galactic-linkedin
├── applications/
│   └── YYYY-MM-DD-company-role/   # one folder per application (kebab-case, date = when saved)
│       ├── application.md     # tracking card: frontmatter + dated log (source of truth)
│       ├── posting.md         # the job posting, verbatim, with URL and capture date
│       ├── company.md         # company research, every fact with source + date
│       ├── fit.md             # requirements vs evidence, screener score, gaps
│       ├── cv.md              # CV tailored for this application (optional)
│       ├── prep.md            # interview preparation plan and mock-interview notes
│       ├── questions.md       # reverse-interview questions picked + answers heard
│       └── offer.md           # offer details and negotiation plan (when it gets there)
├── tracker.md                 # GENERATED index of all applications, never edited by hand
└── exports/                   # CSV / TrackZilla exports
```

## profile.md

```markdown
---
target_roles: [Backend Engineer, Platform Engineer]
seniority: senior              # junior | mid | senior | staff | lead | manager
years_experience: 8
main_stack: [Go, Kubernetes, PostgreSQL]
location: Milan, IT
work_mode: [remote, hybrid]    # remote | hybrid | onsite
relocation: false
languages: [Italian (native), English (C1)]
contract: [employee]           # employee | contractor/P.IVA | either
notice_period: 2 months
compensation:
  currency: EUR
  current: 52000               # optional: only if the user wants to share it
  target: 65000
  walk_away: 58000
must_haves: [fully remote, no on-call]
deal_breakers: [gambling industry]
updated: 2026-09-25
---

Free notes: why they're looking, career direction, constraints, anything the skills should know.
```

All fields are optional. Ask only for what the current task needs, a few questions at a time.
Compensation fields are sensitive: ask, don't assume, and accept "prefer not to say".

## application.md

```markdown
---
company: Acme
role: Senior Backend Engineer
status: interviewing   # saved | applied | screening | interviewing | offer | accepted | rejected | withdrawn | ghosted
saved_on: 2026-09-25
applied_on: 2026-09-26
source: LinkedIn       # where the posting was found
source_url: https://…
referral: Jane (ex-colleague)   # optional
location: Milan, IT
work_mode: hybrid
salary_range: 55–70k EUR (posted)   # or "not disclosed"
contacts:
  - name: Mario Rossi
    role: Talent Acquisition
next_step: Technical interview
next_step_date: 2026-10-02
tags: [go, fintech]
---

## Log
- 2026-09-25 — Saved. Fit score 72/100 (see fit.md).
- 2026-09-26 — Applied via careers page with tailored CV.
- 2026-09-30 — HR screening call with Mario. Went well; tech interview booked.
```

Rules:
- `application.md` is the **source of truth** for tracking. `tracker.md` is regenerated from all of them.
- The log is **append-only**: add dated lines, never rewrite history. Status changes get a log line.
- Dates are ISO `YYYY-MM-DD`. Resolve relative dates ("next Tuesday") into absolute ones before writing.

## Facts and sources

- `company.md` and any market or salary data: every fact carries its source URL and the date you read it.
  If a fact is a guess, label it as a guess.
- `posting.md`: paste the posting **verbatim**, because postings get taken down. Keep the URL and capture date.

## Privacy rules (non-negotiable)

1. Workspace content never goes to a third-party service. Don't paste the CV into web tools, and don't
   put the user's name, email, phone or CV text in web searches or URLs.
2. The web is for **public information about companies, roles and markets**.
3. Research on people (interviewers, hiring managers) happens only when the user names them, and covers only
   their public professional footprint: role, team, public talks and posts about their work. No personal life,
   no cross-referencing personal data.
4. Never commit or print workspace content anywhere outside the workspace unless the user asks.

# Job hunt strategy — operational checklist

Purpose: set the user's targets, read a posting critically and apply with focus, following Guido Penta's Galactic guides.

Source: https://github.com/GuidoPenta/galactic-interview-guide-for-developers (MIT, © 2025 Guido Penta),
https://github.com/GuidoPenta/galactic-tech-interview-guide (MIT, © 2024 Guido Penta),
https://github.com/GuidoPenta/galactic-tech-job-roles-guide (MIT, © 2023 Guido Penta) — full guides there, this is an operational summary.
Data/AI roles in Italy and EU remote: https://dataskew.io/jobs (Dataskew, by Adriano Sanges).

> **Scope and completeness warning.** The guides are **in Italian** and written for the **Italian** market
> (salary as "RAL" = gross annual salary; TechCompenso is Italy-specific). The job-hunt content lives in
> section 2 of the developer guide ([README](https://github.com/GuidoPenta/galactic-interview-guide-for-developers/blob/main/README.md),
> plain text, cite by section number). **Recruiters, referrals, timing/cadence and posting red flags are not
> written up in the sources**: §5 below collects only the signals the sources do give. Don't invent
> "Guido rules" for the rest; label general practice as such.
>
> **Source labels.** **[Guido]** = from Guido's guides (section cited; untagged content in a cited section
> is [Guido]). **[pack]** = this skill pack's own heuristic or general practice. **[Dataskew]** = Dataskew's
> stance (https://dataskew.io, by Adriano Sanges), not Guido's.

---

## 1. Principles (dev guide §1–2)

- **Looking for a job is a job.** A well-handled interview starts long before the meeting; preparation for
  the search is "often underestimated" and is one of the main factors in the final outcome.
- The tech hiring process is often **complex, fragmented and not transparent**; companies often communicate
  poorly what they expect. Expect ambiguity and plan for it.
- **Golden rule (Guido's own):** **don't fire off random applications or trawl ("pesca a strascico").** Build a
  real checklist of your targets (§2) and **apply in a targeted way**. "Little but good always works."
- Every company, recruiter and process differs: use this as a base for self-analysis, not a universal answer.

## 2. Define your targets before applying (dev guide §2.1)

Not a whole career plan, but at least these six, written down (store in `workspace/profile.md`):

- [ ] **Desired role**: e.g. frontend, backend, fullstack, DevOps, data engineer. Map it with `job-roles.md`.
- [ ] **Target seniority**: honestly junior, middle, senior or other.
- [ ] **Main technologies**: the stack you want to work on (languages, frameworks, tools).
- [ ] **Company type and context**: startup, SME, corporate, consultancy, product company.
- [ ] **Work mode**: full remote, hybrid, on site.
- [ ] **Expected salary range**: a realistic idea of gross annual salary and desired benefits.

Why: it avoids random applications and focuses effort on coherent opportunities. Use your checklist to
go targeted rather than trawling ("il poco ma buono funziona sempre!"). A posting that misses a point isn't
automatically out: decide consciously.

## 3. Know (and study) the market (dev guide §2.2)

The guide calls these steps "almost fundamental":
- [ ] **Analyse postings and job boards** to identify recurring roles and requested technologies.
- [ ] **Check average salary ranges** for your role and experience level.
- [ ] Identify **growing and shrinking sectors**.
- [ ] Weigh the difference between **product companies and consultancies**.
- [ ] Observe which **technologies and transversal skills** are most valued.

Base it on concrete data and reliable sources (the guide's list):

| Source | Use |
|---|---|
| [TechCompenso](https://techcompenso.com/) | Italian, anonymous tech salary data by role, seniority, city |
| [Glassdoor](https://www.glassdoor.com/) | Salary ranges, company reviews, benefits, **hiring-process info** |
| [Levels.fyi](https://www.levels.fyi/) | International compensation and career-level comparison, esp. product/big tech |
| LinkedIn Salary | Indicative ranges by position and location |

[pack] suggestion: when the user has no salary range, ground it in these sources (ideally more than one;
cite source + date) before the screening call.

## 4. Build a solid professional profile before applying (dev guide §2.3)

The profile is the **first point of contact** with recruiters and companies:
- [ ] **CV**: concise, clear, up to date, emphasising **real results and responsibilities** → `galactic-cv`.
- [ ] **LinkedIn**: up to date, coherent, well positioned to be **found by recruiters** → `galactic-linkedin`.
- [ ] **Portfolio and projects**: GitHub, tech blog, open-source contributions, side projects, relevant experience.
- [ ] **Online presence**: bio, headline, profile photo, any talks or articles.
- A polished profile **doesn't guarantee an interview, but significantly raises the chance** of being considered.
- [Dataskew] For data roles, a public portfolio of graded projects is available on Dataskew (free).

## 5. Reading a job posting

### 5.1 Decode what they need (tech guide, "How to prepare", step 1)
- [ ] Examine the job description to determine **what must be studied**: data structures, algorithms, a specific
      language, BI tools. The posting is your study plan.
- [ ] If a framework is named, assume the **underlying language** will be tested too (React → JS/TS,
      Laravel → PHP; tech guide type 2).
- [ ] Backend postings, especially senior ones → **system design** is likely (tech guide type 4).

### 5.2 Check the title against the content (roles guide intro)
- The roles guide exists because in the Italian IT market **job titles are "too often" confused,
  misinterpreted and misused in job postings**. Never trust the title alone: map duties to a role with
  `job-roles.md` and flag mismatches.
- Concrete example from the guide: **"DevOps" is a methodology, not a job title**. A "DevOps Engineer" posting
  needs its duties read to decide what the job really is (platform, cloud, SRE, sysadmin, DevSecOps…:
  the skill's examples).
- "Engineer" in Italy: the guide notes that "engineer" usually translates to "ingegnere", which in some cases
  is reserved to people with an engineering degree (roles guide, Software Engineer note). [pack] Don't read
  "Engineer" in an Italian posting as a degree requirement, and don't assume an "ingegnere" title can be used
  without one.

### 5.3 Signals: [Guido] unless tagged (use as questions, not verdicts)
- **Salary and work mode**: one real process (Jointly, tech guide testimony) states range and work mode in the
  first call with the CTO. If a posting or first call is silent on both, add them to your screening
  questions ([pack]).
- **Values and ways of working** (agility, engineering practices, relation between Tech and Product) are
  discussed openly by companies with a clear process (Jointly). [pack] A posting with no hint of how the team
  works is a question to raise, not proof of a problem.
- **Seniority calibrated against the team**: technical steps may assess your level relative to the team
  you'd join. Read "senior" in a posting relative to the team.
- **Product company vs consultancy**: the guide asks you to weigh the difference (§3). [pack] Identify which one
  the posting is before applying.
- [Dataskew] Dataskew's jobs board explicitly excludes **body rental** and recruiter spam and links to the
  company's own apply page: for data roles, prefer postings that let you apply directly.
- Company reviews (Glassdoor) are listed by the guide as a source on the **hiring process** too (§3).

## 6. Applying strategy

- [ ] Use your §2 checklist to go targeted rather than trawling ("il poco ma buono funziona sempre!"). A
      posting that misses a point isn't automatically out: decide consciously.
- [ ] For each: decode (§5), research the company, tailor the CV (`galactic-cv` targeted mode), prepare.
- [ ] Before the first call: salary range from data (§3), targets clear (§2), CV/LinkedIn consistent (§4).
- [ ] Use **communities** for advice, likely interview questions and tools for the role (tech guide step 2:
      "the power of communities is ENORMOUS") → `galactic-communities`. For data roles: Dataskew Telegram
      https://t.me/dataskew_it, where openings are also announced.
- [ ] Where to search: the sources name **job boards and postings** as market data (§3) but no specific boards,
      except Dataskew's curated board for data/AI roles in Italy and EU remote (https://dataskew.io/jobs).

## 7. Not covered by the sources

Say so explicitly if the user asks; offer general practice, labelled as such:
- Working with **recruiters / headhunters** (agency vs in-house).
- **Referrals** and networking tactics beyond "use communities".
- **Timing**: when to apply, how many applications per week, how long to wait before following up.
- A list of **red flags** in postings or companies (only the signals in §5.3 exist).
- Cover letters.
- The dev guide announces a **job-search checklist** in section 7 ("extra resources: exercises and
  checklists"), not yet written as of 2026-09-25. Re-check the repo.

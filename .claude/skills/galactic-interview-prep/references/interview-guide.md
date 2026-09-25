# Galactic Interview Guide — operational checklist

Purpose: prepare a developer for each interview stage using Guido Penta's rules, as checklists the skill can apply.

Source: https://github.com/GuidoPenta/galactic-tech-interview-guide (MIT, © 2024 Guido Penta) and
https://github.com/GuidoPenta/galactic-interview-guide-for-developers (MIT, © 2025 Guido Penta) — full guides there, this is an operational summary.
- Tech interview guide, sections: [How to prepare](https://github.com/GuidoPenta/galactic-tech-interview-guide#come-prepararsi-al-meglio-per-il-colloquio-tecnico) ·
  [Types of technical interview](https://github.com/GuidoPenta/galactic-tech-interview-guide#i-diversi-tipi-di-colloquio-tecnico) ·
  [Companies describe their process](https://github.com/GuidoPenta/galactic-tech-interview-guide#le-aziende-raccontano-i-loro-iter-di-colloquio-tecnico)
- Interview guide for developers: [README](https://github.com/GuidoPenta/galactic-interview-guide-for-developers/blob/main/README.md) (plain text, no anchors; cite by section number)

> **Language and completeness warning.** Both guides are written **in Italian** for the Italian market
> (salary is discussed as "RAL", gross annual salary). The developer guide announces 8 sections but, as of
> 2026-09-25, only sections 1–2 (why the guide exists, preparing the job search) are written; sections 3–8
> (soft interview, technical interview, real Welyk cases, negotiation, extra exercises and checklists,
> contributing) are **announced but empty**. Where this file says "not covered by the sources", do not fill
> the gap with invented "Guido rules": use general good practice and say it is general practice.
>
> **Source labels.** **[Guido]** = from Guido's guides (section cited; untagged content in a cited section is
> [Guido]). **[pack]** = this skill pack's own heuristic or general practice. **[Dataskew]** = Dataskew's
> guidance, not Guido's.

---

## 0. The mindset the guides set

- **Job hunting is a job** ("cercare lavoro è un lavoro"). Preparation starts long before interview day and
  is one of the main factors in the outcome (dev guide §2).
- The complaint that started the dev guide: candidates arrive **unprepared**: technical gaps, soft-skill gaps,
  or simply no strategy. Companies are often unclear too; the guide aims to close that gap (dev guide §1).
- **Every company, recruiter and process is different.** The guide is a base for self-analysis, not a
  universal answer (dev guide §1.2). Tell the user this when their process doesn't match the template.
- Audience: juniors on their first job, mids improving strategy, seniors/leads refining communication and
  negotiation (dev guide §1.1). [pack] Scale the depth of prep to the seniority.

## 1. Stage map (what the sources actually describe)

| Stage | Covered by | Where in this file |
|---|---|---|
| Screening / "soft" interview (HR) | Announced as dev guide §3, **not written yet** | §2 |
| Technical interview: general prep | Tech guide, "How to prepare" | §3 |
| Language-specific interview | Tech guide, type 1 | §4.1 |
| Framework-specific interview | Tech guide, type 2 | §4.2 |
| Pair programming / live coding | Tech guide, type 3 | §4.3 |
| System design | Tech guide, type 4 | §4.4 |
| Take-home project | Tech guide, type 5 | §4.5 |
| "Technical" interview with a non-technical interviewer | Tech guide, type 6 | §4.6 |
| Values/culture fit, HR validation, final → offer | Tech guide, Jointly testimony | §5 |
| Behavioural / STAR, follow-up, rejection | **Not covered by the sources** | §6 |
| Negotiation | Announced as dev guide §6, not written; see `galactic-negotiation` | — |

## 2. Screening / soft interview

- Not written in the source yet (dev guide §3 is an empty heading). What the sources do give for this stage:
  - Arrive with your **own targets clear**: role, seniority, stack, company type, work mode, salary range
    (dev guide §2.1; see `galactic-application/references/job-hunt-strategy.md`). (Likely screening topics;
    general practice.)
  - Have a **realistic salary range** grounded in market data (TechCompenso, Glassdoor, Levels.fyi, LinkedIn
    Salary: dev guide §2.2) before the call. Hand off strategy to `galactic-negotiation`.
  - Keep CV and LinkedIn up to date and coherent (dev guide §2.3).
  - Some companies put salary range and work mode on the table **in the very first call**, together with
    values (Jointly testimony). Be ready to discuss both at stage one.

## 3. Technical interview: general preparation (tech guide, "How to prepare", 5 steps)

1. **Map tools and skills required by the role.**
   - [ ] Re-read the job description and list what must be studied: data structures, algorithms, a specific
         language, BI tools, whatever the posting names.
   - [ ] Solid fundamentals first: they put you in a good position for most questions.
   - [ ] Write an outline of what to study/refresh, focused on the basic principles the role requires.
2. **Study.** Pick materials once you know what to work on:
   - [ ] Books (coding, but also management styles: useful for confident, complete answers).
   - [ ] Online courses (for practical application of technical skills).
   - [ ] Digital publications (broaden knowledge, keep up with trends you can bring into the interview).
   - [ ] **Communities: their power is "ENORMOUS"** (Guido's emphasis). Use them for prep advice, tools, and the
         most likely questions for the role. (Hand off to `galactic-communities`.)
3. **Practise.**
   - [ ] For take-homes and live coding, practise **thinking out loud**: it keeps you engaged on hard problems
         and interviewers need to see your thought process.
   - [ ] While practising scenarios, also review the **general competency and behavioural questions** likely
         to come up.
4. **Prepare questions to ask.**
   - [ ] Research the company and the job description and note every question that comes to mind.
   - [ ] Talking about your work, giving complete answers and arriving with questions makes an "ENORMOUS"
         difference to moving forward.
   - [ ] Custom: candidates keep **their questions for the end** of the interview. (Pick them with
         `galactic-reverse-interview`.)
5. **Prepare the ground (environment).**
   - [ ] Decide the material you need: specific tools, IDE, pen and paper, notepad.
   - [ ] Set up the workspace so you look ready and professional.
   - [ ] **If unsure what's needed, ask the company** whether specific tools will be used.

## 4. Technical interview types: how to prepare and behave

### 4.1 Language-specific interview
- Expect questions on the **nuances of that language**: it will be most of your job.
- Guide's example (JavaScript): async/await, currying, hoisting, binding.
- Prep: [ ] read typical interviews for that language · [ ] review the more **academic** concepts of the language.

### 4.2 Framework-specific interview
- Like the language interview, but on the framework the role needs. You may be asked to build a small app,
  **in live coding or just by talking through every step** you'd take.
- Know the framework's **newer features**. Guide's example (React): hooks, lazy loading, state, router.
- Prep: [ ] use the framework a lot · [ ] read the documentation carefully.
- **Always expect language questions too** (Guido's NB): JavaScript and/or TypeScript alongside React, PHP and
  not only Laravel. Never prep the framework alone.

### 4.3 Pair programming / live coding
- You solve a problem "live" with the interviewer. Examples from the guide:
  - given a test file, TDD the associated class;
  - write a K-means algorithm (don't worry about the maths);
  - find the origin of a bug in this code and fix it together;
  - refactor a piece of code that has a working test file.
- What they look for: **how you reason about problems and how you produce quality code**.
- Language: you can often choose, but **both you and the interviewer must know it**.
- How to succeed: **explain your reasoning out loud, keep trying solutions, keep moving forward.**
- When stuck (general practice, suggested by the guide's examples): keep talking, try the next approach, don't go silent. Practise TDD,
  debugging and refactoring against tests, not just algorithm puzzles.

### 4.4 System design
- Mostly for **backend** roles, and it **grows in importance with seniority**. There's a lot of literature.
- Guide's examples: "build PlowNYC: forget hardware, which systems do you need?"; "design NYC's Citi Bike".
- Typical format: the interviewer gives some screens to build and the core problem; **you design the schema and
  the endpoints**. It moves quickly to **scaling and infrastructure**: load balancers, leader-follower
  databases, database sharding.
- How to succeed: [ ] **ask lots of questions** · [ ] **discuss trade-offs between technologies** · [ ] **keep talking**.
- What they assess: familiarity with building a scalable system and understanding of trade-offs between tech choices.

### 4.5 Take-home project
- A bigger problem done at home, over **a few hours to a few days**. Guide's examples: host a URL-shortener
  service with expiring links; build a small web app that reads (or posts) data from an API they provide.
- What they want: **high-quality code over a longer time span**.
- Guido's advice: **keep it simple and don't overdo it**, or you risk losing the project's focus just to
  impress the interviewer. Scope creep is the failure mode to coach against.

### 4.6 The technical interview that isn't
You arrive fully prepared and the counterpart **is not technical**: the planned person isn't available, the
technical person knows another technology, or the "technical" interviewer is the boss. It doesn't matter:
adapt your presentation.
1. **Understand how the person reasons.** Waterfall background? Totally new to the topic? A salesperson?
   Knowing who you're facing is fundamental. Asking questions also **buys time** to plan your next steps.
2. **Restate the problem's boundaries, constraints and technologies.** It shows you're orderly and avoids wrong assumptions.
3. **Expose the solution logically**, e.g. in pseudo-code, listing pros and cons ("I choose language X because…,
   I use this algorithm because…").
4. **Then go to the code.**
- Why it works, on two levels: **logical-functional** (code works, choices are logical) and **relational**:
  the interviewer judges on **heuristics, not cold data**. Taking control of the reasoning flow and being able
  to expose your thinking is what conveys competence.
- [pack] Mock-interview use: occasionally play a non-technical interviewer and check the user applies steps 1–4.

## 5. Values, HR and final stages: a real process (Jointly testimony)

Testimony by Enrico Maria Cestari, CTO @ Jointly, in the tech guide. Use it as **one real example**, not a norm:
1. **First interview always with the CTO**, built on transparency: salary range and work mode are made clear;
   the CTO presents company values and checks the candidate understands what to expect. Goal: mutual
   understanding of **values fit**. Day-to-day ways of working with Product are discussed, and views on
   culture (agility, software engineering practices).
2. If there's fit: **one or more vertical technical steps with the most senior technical people**, also used
   to assess the candidate's **seniority relative to the team** they'd join.
3. **Last, HR**: validates the values perception and culture fit.
4. If both sides agree: **offer**.
- Prep implications: [ ] have a view on agile and engineering practices you can defend · [ ] expect
  seniority to be calibrated against the team, not in absolute terms · [ ] culture fit may be checked twice.
- The guide invites companies to contribute their process by PR; check the repo for new testimonies.

## 6. Not covered by the sources (use general practice, labelled as such)

- **Behavioural / STAR stories**: the sources only say to review general competency and behavioural questions
  (tech guide, step 3). STAR is not mentioned. The skill's STAR story bank is general practice, not Guido's rule.
- **"Tell me about yourself", "why us", "why are you leaving"**: not covered.
- **Follow-up / thank-you messages after interviews**: not covered. Don't present one as the guide's recommendation.
- **Handling rejection, asking for feedback**: not covered.
- **Final-round / onsite structure**: only the Jointly example (§5).
- **Negotiation**: dev guide §6 is announced but empty; use `galactic-negotiation`.
- For data roles, Dataskew publishes its own typical interview format and interview-day tips; see
  `resources-by-role.md` → Data engineering.

## 7. Day-before checklist (all items traceable to the sources)

- [ ] Job description re-read; outline of topics to refresh done (tech guide step 1).
- [ ] Language questions prepared even if the interview is "about the framework" (type 2 NB).
- [ ] Practised solving out loud at least once (step 3, type 3).
- [ ] For system design: list of clarifying questions and 2–3 trade-offs ready (type 4).
- [ ] For take-home: scope cut to the essentials (type 5).
- [ ] Plan B if the interviewer turns out non-technical: restate → pseudo-code with pros/cons → code (type 6).
- [ ] Questions for the end of the interview written down (step 4).
- [ ] Tools/IDE/paper ready; asked the company which tools they'll use if unclear (step 5).
- [ ] Own targets and salary range clear and backed by data (dev guide §2.1–2.2).

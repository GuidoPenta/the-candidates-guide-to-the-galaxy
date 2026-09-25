# Practice resources by role — curated list

Purpose: tell the skill which practice resources it may recommend per role family, and where the curated list is empty.

Source: https://github.com/GuidoPenta/galactic-tech-interview-guide (MIT, © 2024 Guido Penta),
https://github.com/GuidoPenta/galactic-interview-guide-for-developers (MIT, © 2025 Guido Penta),
https://github.com/GuidoPenta/galactic-tech-job-roles-guide (MIT, © 2023 Guido Penta) — full guides there, this is an operational summary.
Data roles: https://dataskew.io/ (by Adriano Sanges; site content "All rights reserved", resources linked, not copied).

> **Rules for the skill.**
> - The Galactic guides name very few concrete resources. Recommend **only** what's listed here, or a resource
>   you verify on the web in the current session (and say you found it, not the guide).
> - "No curated resource yet — contributions welcome" means exactly that: don't invent a list and attribute it
>   to the guides. You may still build a study plan from the posting's stack (see `interview-guide.md` §3).
> - Resources listed under Dataskew are Dataskew's own recommendations, not Guido's.

---

## Resource types every role can use (tech guide, "How to prepare", step 2)

The guide recommends **categories**, not titles:
- **Books**: on coding and also on management styles.
- **Online courses**: for practical application of technical skills.
- **Digital publications**: to broaden knowledge and track tech trends.
- **Communities**: "the power of communities is ENORMOUS": ask for prep advice, needed tools, likely
  questions for the role. See `galactic-communities`.
- **The framework's official documentation**: read carefully, together with heavy hands-on use (type 2).
- **Typical interviews for your language** ("read typical interviews in that language", type 1).

Link: https://github.com/GuidoPenta/galactic-tech-interview-guide#come-prepararsi-al-meglio-per-il-colloquio-tecnico

## Market and salary data (dev guide §2.2, all roles)

| Resource | What the guide says it's for |
|---|---|
| [TechCompenso](https://techcompenso.com/) | Italian platform, anonymous tech salary data by role, seniority and city |
| [Glassdoor](https://www.glassdoor.com/) | Salary ranges, company reviews, benefits, hiring-process info |
| [Levels.fyi](https://www.levels.fyi/) | International comparison of compensation and career levels, especially product and big tech |
| LinkedIn Salary | Indicative ranges by position and location |

## Profile material (dev guide §2.3, all roles)

- Galactic CV Guide for Developers: https://github.com/GuidoPenta/galactic-CV-guide-for-developers (see `galactic-cv`)
- Galactic LinkedIn Profile Guide for Developers (see `galactic-linkedin`)
- Portfolio: GitHub, tech blog, open-source contributions, side projects.

---

## Backend

- Interview formats to expect: language-specific, framework-specific, pair programming, **system design**
  ("mostly reserved for backend roles, increasingly important with seniority"), take-home.
- Topics the guide names for system design: schema and endpoint design, scaling, load balancers,
  leader-follower databases, database sharding.
- Framework NB: PHP is asked alongside Laravel, not just the framework.
- Curated resources: **No curated resource yet — contributions welcome.** (The guide notes system design has
  "a lot of literature" but names no title.)

## Frontend

- Guide's examples: JavaScript nuances (async/await, currying, hoisting, binding); React (hooks, lazy loading,
  state, router); building a small app live or by describing the steps. JS and/or TS asked together with React.
- Curated resource: **[The Concise TypeScript Book — Italian edition](https://gibbok.github.io/typescript-book/it-it/)**,
  free and open source, recommended in the tech guide for a structured TypeScript review. The guide links
  the Italian edition; the same project's default edition is at https://gibbok.github.io/typescript-book/
  (checked 2026-09-25, not linked by the guide itself).
- Otherwise: **the framework's official docs** (tech guide type 2).

## Fullstack

- Combine Backend and Frontend. The TypeScript book above applies to TS-based stacks.
- Curated resources beyond that: **No curated resource yet — contributions welcome.**

## Mobile

- **No curated resource yet — contributions welcome.** (The roles guide's "Mobile Developer" entry is also empty.)

## Data engineering

Dataskew (https://dataskew.io/) is the reference platform for this family. What it offers, as seen on the
site on 2026-09-25:
- **Free to use**: the terms say "Dataskew.io is free to use, and we intend to keep it that way". Free
  account; project submission needs sign-in. No paid tier found.
- **Roadmaps** on real stacks: Beginner Data Engineer (51 tasks: SQL, Python, PostgreSQL, Docker, Git,
  DuckDB, Airflow, dbt), Startup Stack (31 tasks: DuckDB, Polars, Metabase, serverless), Modern Data Stack
  (34 tasks: Docker, Terraform, Airflow, dlt, BigQuery, dbt, Spark, Kafka), plus Data Analyst and AI Engineer
  roadmaps. https://dataskew.io/roadmaps
- **Fundamentals**: SQL, Python for data engineering. https://dataskew.io/fundamentals
- **Hands-on projects, graded by a working (senior) data engineer**, not auto-graded; graded work goes on a
  **public portfolio** visible to hiring companies. Examples: local ETL with dlt + DuckDB + Jupyter (2–4 h),
  scheduled GitHub ETL with Polars, DuckDB + Metabase analytics platform, RAG / LLM agent / LLM evaluation
  projects. https://dataskew.io/projects
- **Interview Prep**: a question bank of real data-engineering interview questions (partitioning, OLTP vs
  OLAP, Kafka→Snowflake JSON pipeline design, SCD, reliable pipelines/WAP, Medallion, design patterns).
  Some have full answers, some only hints, some are questions only. https://dataskew.io/interview-prep
- **Jobs board** for data/AI roles in Italy and EU remote, links straight to the company's apply page;
  **Telegram community** https://t.me/dataskew_it for openings, help and advice.

Dataskew's own interview guidance (Beginner roadmap, "interview" step) — attribute to Dataskew:
- Typical format: phone screen 30 min (behavioural + basic technical) → technical screen 60 min (SQL + Python)
  → system design 60 min (design a data pipeline) → onsite/final 3–5 h (mix).
- SQL topics: JOINs (LEFT JOIN edge cases), **window functions (called the #1 SQL interview topic)**, CTEs,
  GROUP BY/HAVING, query optimisation (explain plans, indexes).
- Python topics: dicts/lists/sets, file I/O (CSV, JSON, Parquet), API calls and error handling, dedup/merge.
- System design: batch ETL, real-time pipeline, late-arriving data, data quality, scaling 1 GB → 1 TB.
- Plan: 2 SQL problems/day for 2–3 weeks; aim for 15–20 min per medium SQL problem; record yourself explaining projects.
- Resources it lists: LeetCode Database, HackerRank SQL, SQLZoo, StrataScratch, *Designing Data-Intensive
  Applications* (Kleppmann), DataTalks.Club.
- Day-of tips: think out loud, ask clarifying questions (volume, latency), start simple then optimise, discuss
  trade-offs, be honest about what you don't know. "The best interview preparation is building real projects."

## Data analysis / BI

- Dataskew's **Data Analyst roadmap** (free; 47 tasks: SQL, Excel, Power BI, Tableau, Python/pandas,
  statistics, A/B testing, dbt, GA4, portfolio + interview prep). https://dataskew.io/roadmaps
- The tech guide mentions BI tools as a possible study area for technical roles (step 1).

## Data science / ML / AI engineering

- Dataskew: **AI Engineer roadmap** (RAG, agents, evals, fine-tuning, production deployment) and AI
  engineering projects (RAG with retrieval evaluation, LLM agent with failure-mode evaluation, LLM eval
  pipeline). Its jobs board also lists ML/AI/data-science roles.
- Tech guide pair-programming example: "write a K-means algorithm (don't worry about the maths)".
- Beyond that: **No curated resource yet — contributions welcome.**

## DevOps / SRE / platform / cloud

- Note from the roles guide: **"DevOps" is a methodology, not a job title**. Read the posting's actual duties
  (see `galactic-application/references/job-roles.md`).
- **No curated resource yet — contributions welcome.** (Dataskew's Modern Data Stack roadmap covers Docker
  and Terraform, but in a data context only.)

## QA / testing

- Pair-programming formats in the tech guide are test-centric (TDD from a test file, refactor under a test
  suite), which is relevant practice.
- **No curated resource yet — contributions welcome.**

## Security

- **No curated resource yet — contributions welcome.**

## Engineering management / tech lead / architect

- Tech guide: books on **management styles** help give confident, complete answers (step 2).
- Dev guide §1.1: seniors and leads should focus on **communication, negotiation and process management**.
- Curated titles: **No curated resource yet — contributions welcome.**

## Other roles (game, blockchain, IoT, robotics, technical writing, UX/UI, product)

- **No curated resource yet — contributions welcome.**

---

## Soft skills

What the sources give:
- [ ] **Think out loud** during practice and in the interview: interviewers need your thought process (tech guide step 3, type 3).
- [ ] Review **general competency and behavioural questions** while practising (tech guide step 3).
- [ ] **Talk about your work**, give complete answers, bring questions: it makes an "ENORMOUS" difference (step 4).
- [ ] **Read the interviewer** and adapt: who are they, how do they reason; restate constraints; expose the
      solution with pros and cons (type 6). Interviewers judge on heuristics, not cold data.
- [ ] **Communities** for advice and likely questions (step 2).
- [ ] Values/culture fit is assessed explicitly in some processes (Jointly testimony).
- Curated soft-skill books/courses/STAR material: **No curated resource yet — contributions welcome.**
  (The dev guide's "soft interview" section and "extra resources: exercises and checklists" section are
  announced but not yet written; re-check the repo.)

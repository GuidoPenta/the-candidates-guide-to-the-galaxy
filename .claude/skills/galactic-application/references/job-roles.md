# Job roles in tech — mapping reference

Purpose: map a job posting to a real role, check seniority signals and flag mislabelled postings, using Guido Penta's roles guide.

Source: https://github.com/GuidoPenta/galactic-tech-job-roles-guide (MIT, © 2023 Guido Penta) — full guide there, this is an operational summary.
Role anchors: `https://github.com/GuidoPenta/galactic-tech-job-roles-guide#<role-slug>`, e.g. [#backend-developer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#backend-developer).

> **Language, age and coverage warning.** The guide is **in Italian**, aimed at the **Italian IT market**, last
> updated **November 2023**, and still a work in progress ("a blob of purely textual definitions"). Of ~70
> roles in its index, **only 21 have a real description** (plus a one-line DevOps note and a Software
> Developer cross-reference). The rest (including Frontend, Full Stack, Mobile,
> ML Engineer, SRE, Platform Engineer, QA, Tech Lead, Product Manager…) are **empty stubs**. For those, this
> file says "No definition in the guide yet" and the skill must decide from the posting's duties, labelling
> its reasoning as its own. It has no salary data and, apart from Software Engineer, no seniority levels.

---

## 0. Why the guide exists: how to use it on a posting

- In Italy, job titles are **"too often" confused, misinterpreted and misused in job postings**. The guide
  aims to bring clarity with clear definitions of roles and responsibilities.
- Procedure for the skill:
  1. [ ] Ignore the title at first. List the posting's **actual duties** (verbs + objects).
  2. [ ] Match duties to the "core duties" below. Pick the role whose core duties cover most of them.
  3. [ ] Compare with the title. If they differ, flag it: "Title says X, duties describe Y".
  4. [ ] Check seniority signals (§3) against the level the posting claims.
  5. [ ] If the best match is a stub role, say the guide has no definition and reason from the duties.

## 1. Rules the guide states outright

- **"The DevOps" doesn't exist. DevOps is a methodology, not a job title.**
  ([#devops-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#devops-engineer)).
  A "DevOps Engineer" posting must be read by duties: cloud engineering, platform, SRE, sysadmin, CI/CD
  work, or DevSecOps. Flag it every time and name what the duties actually describe.
- **Software Developer = see Software Engineer**: the guide treats them as the same entry.
- **Developer vs Programmer**: "Software Developer" is the more generic term for any role in software
  development; "Programmer" is more specific: someone who **mainly writes code**.
- **"Engineer" and the Italian law**: "engineer" usually translates to "ingegnere", and in some cases
  "ingegnere" is **reserved to people with an engineering degree**. In those cases "Software Engineer" might be
  rendered as "tecnico informatico" or "programmatore". Relevant when an Italian posting or CV uses "Ingegnere".

## 2. Roles with a definition in the guide

Format: **core duties** (what the role does) · **extra** (may also do) · **skills** (when the guide lists them).

### Software Engineer / Software Developer — [#software-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#software-engineer)
- Core: requirements analysis; design (architecture, features, UI); development with languages/frameworks; testing; maintenance.
- Seniority (the only role with levels in the guide):
  - **Junior**: short experience, **basic development tasks**.
  - **Middle**: more experience, **more complex development tasks**.
  - **Senior**: significant experience, **design and leadership** responsibilities.
- Senior extras: leading a dev team; technical consulting to clients/other teams; R&D on new technologies and methods.

### Backend Developer — [#backend-developer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#backend-developer)
- Core: server-side code, features not visible to the user; handling user requests (sign-up, purchase, file
  upload); database interaction; **building APIs**; performance optimisation (fast, reliable responses).
- Extra: collaboration with frontend devs; test and debug; documentation.
- Company-dependent: application **security**, **scalability**, **integration with legacy systems**.

### Data Engineer — [#data-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#data-engineer)
- Goal: data available, accessible, secure, high quality.
- Core: collection from internal/external sources; transformation of raw data; storage; **access tools and
  policies**; **data governance** (quality, security, compliance).
- Extra: ML/AI algorithms; dashboards and reporting; cross-team collaboration.
- Position: key to data science, makes data available to analysts and data scientists.
- (Present in the body but missing from the guide's index.)

### Big Data Engineer — [#big-data-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#big-data-engineer)
- Core: acquire (DBs, operating systems, sensors), process/clean, manage/distribute, analyse **large volumes**.
- Extra: coordination with data science/BI teams; security and compliance solutions; user training.
- Skills: data architecture, data engineering tools, data analysis, security.

### Big Data Architect — [#big-data-architect](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#big-data-architect)
- Core: **define the company's big-data strategy**; design the architecture; select technologies; build and
  run the infrastructure (servers, DBs, compute); data quality and security.
- Extra: train/lead people; align with IT and business leads; monitor and optimise performance.
- Skills: databases, distributed processing, analytics; maths/statistics; business; leadership/communication.

### Data Analyst — [#data-analyst](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#data-analyst)
- Core: collect (internal DBs, external sources, social feeds); clean; analyse with statistics/ML to find
  patterns and trends; **present results clearly to decision makers**.
- Extra: predictive models; dashboards and reports; training users.

### Data Scientist — [#data-scientist](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#data-scientist)
- Core: **define the research questions** for business problems; select/collect/integrate data; statistics
  and ML analysis; predictive models; communicate results to decision makers.
- Extra: algorithms and software; managing data-science projects; training users.
- Analyst vs Scientist (reading of the guide): the Scientist frames the question and builds models; the
  Analyst's core is cleaning, analysing and presenting.

### AI Engineer — [#ai-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#ai-engineer)
- Core: problem analysis and requirements; design/implement **ML algorithms and models**; code the software;
  test/validate; **deploy and maintain in production**.
- Extra: R&D, training, consulting; collaboration with data science, software engineers, PMs; stakeholder
  communication; **ethical responsibility**.
- Note: written in 2023, before today's LLM-application meaning of "AI Engineer". Postings may now mean
  RAG/agents/LLM integration work. Flag the difference instead of forcing the 2023 definition.

### Database Administrator (DBA) — [#database-administrator](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#database-administrator)
- Core: design/implement DBs with devs and business users; daily management (servers, **backups**,
  troubleshooting); DB security.
- Extra: performance tuning with devs; monitoring and reporting; training and support.

### Blockchain Engineer — [#blockchain-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#blockchain-engineer)
- Requires deep knowledge of distributed ledgers, cryptography, smart contracts.
- Core: design/develop, deploy on a blockchain network, maintain blockchain applications.
- Extra: training/consulting; R&D; project leadership when experienced.

### Cloud Architect — [#cloud-architect](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#cloud-architect)
- Core: **cloud strategy** and adoption process; evaluate cloud apps/hardware/software; design cloud
  systems; cloud privacy with security; **migration** guidance (mass app moves); best architectures;
  best practices; **select cloud vendors** and third-party services.
- Skills: strong written/verbal communication to present solutions and deal with management.

### Cloud Computing Engineer (Cloud Engineer) — [#cloud-computing-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#cloud-computing-engineer)
- Core: assess needs and design custom cloud solutions; implement/configure services (servers, storage, DBs,
  networks, software); manage and monitor (performance, security, availability); maintenance and troubleshooting.
- Extra: cloud app development; training; R&D; **cost management**; security; compliance; data; AI/ML on cloud;
  migration of legacy apps.

### Cloud Systems Engineer — [#cloud-systems-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#cloud-systems-engineer)
- Core: assess existing IT for **migration opportunities**; design/implement, manage/monitor, secure cloud systems and apps.
- Extra: train end users; work with dev and security teams; manage cloud costs.

### DevSecOps Engineer — [#devsecops-engineer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#devsecops-engineer)
- Combines development, operations and security across the whole software lifecycle.
- Core: security best practices in the dev process (**code vulnerability scanning**, security testing, risk
  management); integrate security into the DevOps process with devs and ops; monitor production for vulnerabilities.
- Extra: security training; **automated security tools and processes**; coordination with corporate security.

### Cyber Security Specialist — [#cyber-security-specialist](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#cyber-security-specialist)
- Core: design/implement security measures (firewall, antivirus, authentication, access control); continuous
  monitoring and threat analysis; **incident response**.
- Extra: staff training and awareness; consulting to clients and partners.

### Enterprise Architect — [#enterprise-architect](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#enterprise-architect)
- Aligns the organisation's IT strategy with business goals; analyses portfolio and solutions, tracks the IT market.
- Profile: strong communication; **7–10 years' proven experience** in one field (security, sysadmin or
  development); knowledge of major cloud providers; certifications help (e.g. an AWS Professional-level cert
  in a DevOps context); business and IT process understanding; leadership; degree optional but useful.
- Extra: assess tech strategy/apps/infrastructure for a team or client; advise on architecture (tech, data,
  security, integration); large-scale innovative solutions; strategies and roadmaps; centres of excellence.
- **Seniority signal**: the only role with an explicit years-of-experience figure. An "Enterprise Architect"
  posting open to juniors is mislabelled.

### Business Analyst — [#business-analyst](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#business-analyst)
- The **bridge between business needs and technical solutions**: turns requests into detailed requirements.
- Core: gather and analyse information; define requirements with stakeholders; assess impact of changes;
  design solutions with dev teams; documentation (specs, flowcharts, use cases); communication and
  coordination; change management; QA collaboration; post-implementation support.

### CTO — [#chief-technology-officer-cto](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#chief-technology-officer-cto)
- Core: **tech strategy** aligned with business strategy (emerging tech, requirements, plan); develop and ship
  the technology behind products/services/processes (managing engineering teams, overseeing projects,
  quality); manage tech infrastructure (hardware, software, network, security, vendors).
- Varies with company size/sector: R&D in a tech company, product engineering in manufacturing.

### CIO — [#chief-information-officer-cio](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#chief-information-officer-cio)
- Core: IT strategy with CEO and executives; information systems (servers, DBs, networks, apps); company
  data (security, compliance, analysis); IT people, budgets, resources.
- Extra: lead digital transformation; develop IT staff; represent the company in the IT sector.
- CTO vs CIO (reading of the guide): CTO is oriented to the technology **behind the product**; CIO to the
  company's **internal information systems**.

### CISO — [#chief-information-security-officer-ciso](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#chief-information-security-officer-ciso)
- Core: security strategy; lead a multidisciplinary security team; risk assessment and mitigation; staff
  training; incident management.
- Extra: regulatory compliance; cross-department security; vendor contracts vs security standards; security
  in digital transformation; coordination with authorities on incidents.

### Technical Writer — [#technical-writer](https://github.com/GuidoPenta/galactic-tech-job-roles-guide#technical-writer)
Two distinct types; check which one the posting wants:
- **Tutorial writer**: technical articles to help devs solve problems, explore technologies (e.g. ML),
  test frameworks, cover trending topics. Fits **freelance**, or employee **alongside another job (typically
  development)**. Duties: research; use AI prompts well (**not copy-pasting AI-generated text** into the
  article); write and verify working code examples; final editing. Skills: some of the language, Git basics,
  Markdown, English.
- **Product documentation writer**: customer docs and procedures; internal docs (processes, support
  troubleshooting, code docs). Employee or contractor. Duties: set a process with devs so **docs are ready before
  release**; test and know the product; docs **segmented by audience** (per user type in a SaaS); verification
  processes; editing; writing standards; translations. Skills: the doc tool, HTML basics, English.

## 3. Seniority signals from the guide

- Junior → basic tasks; Middle → complex tasks; Senior → **design + leadership** (Software Engineer entry).
  A "senior" posting with no design or leadership duties may really be middle; a "junior" posting asking for
  design ownership and team leadership is mislabelled.
- Senior extras across roles: leading teams, consulting other teams/clients, R&D, training others, project
  management (Blockchain, Software Engineer, Big Data Architect).
- Architect roles (Big Data, Cloud, Enterprise) carry **strategy, vendor selection and management
  communication**: these are senior by nature. Enterprise Architect: 7–10 years.
- C-level (CTO, CIO, CISO): strategy, budgets, people management, representing the company.

## 4. Mislabelling checklist (quick)

- [ ] Title contains "DevOps" → methodology, not role (§1). Name the real role from duties.
- [ ] "Data Scientist" whose duties are only cleaning + dashboards → closer to Data Analyst.
- [ ] "Data Engineer" with no pipelines/storage/governance duties, only reports → closer to Data Analyst.
- [ ] "Architect" with only implementation duties and no strategy/selection → closer to Engineer/Developer.
- [ ] "Backend" asking for UI work, or "Software Engineer" that's only coding → check Programmer vs Developer (§1).
- [ ] "AI Engineer": 2023 ML definition vs current LLM-application work; clarify which.
- [ ] "Technical Writer": tutorial writer vs product-docs writer.
- [ ] Seniority claim vs duties (§3).
- [ ] Italian posting using "Ingegnere": possible legal/degree meaning (§1).

## 5. Roles in the index with no definition yet

No definition in the guide yet (as of 2026-09-25; contributions welcome upstream): Developer Advocate,
Developer Relations (DevRel), Frontend Developer, Full Stack Engineer, Game Developer, Information Security
Architect, Information Systems Manager, IoT Engineer, IT Auditor, IT Business Analyst, IT Consultant, IT Manager,
IT Risk Analyst, IT Security Analyst, IT Trainer, IT Support Specialist, Machine Learning Engineer, Mobile
Developer, Network Administrator, Network Engineer, Network Infrastructure Specialist, Network Security Engineer,
Operations Analyst, Penetration Tester, Platform Engineer, Product Manager, Program Manager, Project Manager
Operation (PMO), QA Analyst, Robotics Engineer, Scrum Master, SEO Consultant, Security Specialist, Site Reliability
Engineer, Software Architect, Software Tester, Solutions Architect, Support Engineer, System Administrator,
Systems Analyst, Technical Lead, UX Designer, UI Designer, UX/UI Specialist, Web Designer.
Also listed in the index but with no heading in the body: Cloud/Software Architect, Cloud/Software Developer.

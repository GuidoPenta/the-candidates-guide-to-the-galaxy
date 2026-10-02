# ATS — how they really work

Purpose: give Claude an accurate, sourced picture of Applicant Tracking Systems (ATS) and of
"LinkedIn Easy Apply vs company site", so it can answer job seekers' questions and correct myths
without inventing new ones. General market view, not Italy-specific unless stated.

**Legend.** Every claim below is **[pack]**: general knowledge gathered by this pack, with an
inline source and access date. **[Guido]** = Guido's own view, in the "Guido's take" boxes.
Wording rules for Claude:
- **documented** = stated by a vendor, LinkedIn, a law or a study (link given).
- **varies** = differs by vendor, version and *how each company configured it*. Say so.
- **anecdotal / uncertain** = practitioner opinion or small/commercial survey. Say so.
- Never turn a vendor-specific fact into "all ATSs do X". Never quote a number not listed here.

> **What Guido's CV guide already says** ([Guido], see `cv-guide.md` §0 and skills section)
> - The "ATS-proof CV" does not exist.
> - Recruiters read all CVs; the ATS is a tool for repetitive tasks (CV database, filtering).
> - Keywords for the position help the CV surface.
> - Stars / progress bars may not be recognised by some ATSs; prefer text.

---

## 1. What it is

An ATS is the software a company (or agency) uses to run hiring: a candidate **database**, a
**pipeline** of stages per job, and the tools around it. [pack]

Typical functions (not every product has all of them; **varies**):
- **Database + search**: every application becomes a candidate record that recruiters can search
  and rediscover later (e.g. Lever documents database search and rediscovery —
  [Lever Help](https://help.lever.co/s/article/Using-advanced-search-and-rediscovery), acc. 2026-10-02). [pack]
- **Parsing**: extracts fields from the CV to pre-fill the profile. Greenhouse: it "auto-fills
  appropriate fields with information it detects" ([Greenhouse Support, Unsuccessful resume parse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse), acc. 2026-10-02).
  Lever lists name, contact details, companies, titles, schools, and dates used to compute years
  of experience ([Lever Help, Understanding Resume Parsing](https://help.lever.co/hc/en-us/articles/20087345054749-Understanding-Resume-Parsing), acc. 2026-10-02, via search snippet). [pack]
- **Application form + screening/knockout questions** (see §4). [pack]
- **Workflow**: stages, interview scheduling, scorecards/feedback, offer, email templates and
  candidate communication, reporting/source tracking (e.g. Greenhouse tags Apply Connect
  candidates with source "LinkedIn" — [Greenhouse Support](https://support.greenhouse.io/hc/en-us/articles/17073067102747-LinkedIn-Apply-Connect-integration), acc. 2026-10-02). [pack]
- **AI matching / ranking (some products, often optional add-ons)** — documented examples:
  - *Greenhouse Talent Matching*: labels candidates "Strong / Good / Partial / Limited Match"
    against recruiter-defined criteria; "does not automatically advance or reject candidates";
    "a decision-support tool, not a decision-making tool" ([Greenhouse FAQ](https://support.greenhouse.io/hc/en-us/articles/41131616864283-Talent-Matching-Data-Processing-FAQ), acc. 2026-10-02). [pack]
  - *Workday HiredScore*: grades A–D by match of the CV to the job's basic/preferred
    qualifications; recruiters can sort and filter by grade ([Workday docs, Candidate Grades](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/reference--candidate-grades.html), acc. 2026-10-02). [pack]
  - Whether a ranking is ever used to reject automatically depends on the company's setup —
    **varies**; vendors above describe ranking/prioritisation, not auto-rejection. [pack]

> **[Guido] — Guido's take**
> An ATS is simply where applications land and get managed. It is not a robot that decides: people configure
> it and people use it, well or badly. In my experience many recruiters have very little time per application,
> so they lean on filters and searches; that's the real risk, not "the machine". (At Welyk we read every
> application, but don't assume every company does.)

---

## 2. Parsing & formats

What vendors **document** (each statement is about *that* vendor only):

| Vendor / source | Formats that parse | Documented failure causes |
|---|---|---|
| Greenhouse ([support](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse), acc. 2026-10-02) | document files such as .docx or .pdf | file > 2.5 MB; CV uploaded as an image; graphics/photos/word art; spaced-out letters; "complex resumes with tables, headers, and footers"; name/contacts in header, footer or text box; columned layout |
| Lever ([help](https://help.lever.co/hc/en-us/articles/20087345054749-Understanding-Resume-Parsing), acc. 2026-10-02, via search snippet) | Word (.docx), PDF, RTF, WordPerfect, HTML, ODF | "cannot parse information from image files (like JPG or PNG)" |
| Textkernel, a parser vendor used inside ATSs ([docs](https://developer.textkernel.com/TKPlatform/master/file-formats), acc. 2026-10-02) | PDF, doc/docx, HTML, RTF, txt, odt, Pages | images (image-PDF, JPG, PNG, TIFF…) only **with an optional OCR add-on**, slower |
| Roche, an employer's candidate FAQ ([careers.roche.com](https://careers.roche.com/de/de/resume-parsing-faq), acc. 2026-10-02) | recommends .docx and .pdf; says .docx is read most accurately by ATSs | advises avoiding tables, text boxes, logos, images, columns, headers/footers, unusual headings and fonts |

Key points for Claude: [pack]
- **A failed parse is not a rejection.** Greenhouse: when parsing fails, the CV "has only been
  attached to the candidate" — fields stay empty, the file is still there for a human
  ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse)). The real cost: empty/wrong fields can make the profile
  harder to find in searches and filters. Roche asks candidates to check that parsed data landed
  in the right fields ([Roche FAQ](https://careers.roche.com/de/de/resume-parsing-faq)).
- **Images/PNG**: *some* parsers can't read them (Lever, Greenhouse), *some* can with OCR
  (Textkernel add-on). So: "an image CV may not be parsed by many systems", **not** "ATSs can't
  read PNG". **varies**.
- **PDF vs DOCX**: both are widely supported. A **text-based** PDF (text selectable) is what
  parsers read; a scanned PDF is an image. Roche prefers .docx; that is one employer's view, not
  a universal rule. **varies**.
- **Columns, tables, headers/footers, text boxes**: documented as *risk factors* (Greenhouse,
  Roche). Not documented as "always break". **varies** by parser and version.
- Parsers evolve (Teamtailor announced parser improvements —
  [Teamtailor product news](https://www.teamtailor.com/en/productnews/parse-candidates-faster-and-easier/), acc. 2026-10-02), so old blog advice may be outdated. [pack]
- **Uncertain**: there is no public, vendor-neutral benchmark of parse accuracy by layout. Don't
  give percentages.

> **[Guido] — Guido's take**
> Send a text PDF (not a photo or a scan) with a clean layout. A well-designed CV is fine, as my CV guide says,
> but keep contacts in the body of the page, not in the header. When a careers site pre-fills a form from your
> CV, check every field: that is the data the recruiter will search on.

---

## 3. Myths vs reality

**"The ATS automatically rejects 75% of CVs."** — **Unsubstantiated.** [pack]
- Traced to a ~2012 marketing claim by **Preptel**, a CV-optimisation service that closed in
  August 2013, with no published study; debunked by HR consultant Christine Assaf
  ([HiringThing blog](https://blog.hiringthing.com/applicant-tracking-systems-arent-excluding-job-applicants-people-are), acc. 2026-10-02). The Preptel primary material
  could not be retrieved — say "attributed to".
- Counter-evidence (small, commercial — say so): Enhancv interviewed **25 US recruiters**
  (Sep–Oct 2025); 23/25 said their ATS does not auto-reject on formatting/content; 2/25 used
  match-score thresholds; 44% had AI scoring, mostly used as guidance
  ([Enhancv](https://enhancv.com/blog/does-ats-reject-resumes/), acc. 2026-10-02). Enhancv sells a CV builder.

**"A robot reads you, not a human."** — **Mostly false, with nuance.** [pack]
- Vendors with AI ranking document that humans decide (Greenhouse, see §1).
- But automated *filters* are real and configured by people (§4). Harvard Business School &
  Accenture's *Hidden Workers* (2021; survey of 2,275 executives in US/UK/Germany) found
  employers use recruiting management systems to filter or rank candidates, and **88%**
  (high-skill) / **94%** (middle-skill) agreed qualified candidates get screened out for not
  matching exact criteria; examples include filtering on degrees and on 6-month employment
  gaps ([The Register summary](https://www.theregister.com/2021/09/08/harvard_jobs_report/); [HBS Working Knowledge](https://www.library.hbs.edu/working-knowledge/how-to-tap-the-talent-automated-hr-platforms-miss), both acc. 2026-10-02).
  Note: this measures employer *opinion*, US/UK/DE, 2021.
- Legal angle (US, ongoing, **allegations not findings**): *Mobley v. Workday* — on 16 May 2025
  a federal court preliminarily certified a nationwide age-discrimination collective action over
  Workday's AI screening ([Holland & Knight](https://www.hklaw.com/en/insights/publications/2025/05/federal-court-allows-collective-action-lawsuit-over-alleged), acc. 2026-10-02).

**"There's an ATS-proof / ATS-beating CV."** — **No such thing** ([Guido]; see box). Each ATS,
version and configuration differs (§2); "ATS score" checkers simulate one parser at best. [pack]

**"Keyword stuffing / white text tricks the ATS."** — **Backfires.** [pack]
Parsing strips formatting, so hidden text surfaces in the extracted text; Greenhouse estimated
~1% of CVs contain hidden text, ManpowerGroup ~10% of those it scans; recruiters quoted say they
usually eliminate such candidates ([Built In, Oct 2025](https://builtin.com/articles/hidden-ai-prompts-in-resume), acc. 2026-10-02 — journalism quoting vendors; anecdotal on outcomes).

**"Fancy design = automatic rejection."** — **Overstated.** Complex layouts are documented
*parse-risk* factors (§2), and a failed parse leaves the file attached for a human. The risk is
worse data in the profile, not an automatic "no". **varies**. [pack]

> **[Guido] — Guido's take**
> The "75% rejected by the ATS" is a legend. Recruiters read CVs; what cuts people out are filters and
> questions that *someone* configured, and the sheer volume of applications. So stop trying to "beat the
> ATS" and make the CV clear and relevant for the person who will read it.

---

## 4. Where filtering really happens

Real automation exists, and it is **configured by the company**: [pack]
- **Knockout / screening questions**: e.g. LinkedIn lets posters mark questions as
  "Must-have qualification" and optionally "automatically archive candidates who don't pass your
  screening questions and send an automatic rejection email"
  ([LinkedIn Help a519651](https://www.linkedin.com/help/linkedin/answer/a519651/add-screening-questions-to-your-job-post), acc. 2026-10-02). In the Enhancv sample, knockouts were used for
  eligibility (work authorisation, certifications, location) ([Enhancv](https://enhancv.com/blog/does-ats-reject-resumes/)).
- **Required fields** on the application form (an incomplete form may not submit at all). [pack]
- **Recruiter filters and searches** on parsed fields (location, years of experience, titles,
  skills). Bad parsing → you may not show up. Hidden Workers documents negative filters
  (degree, gaps) ([HBS WK](https://www.library.hbs.edu/working-knowledge/how-to-tap-the-talent-automated-hr-platforms-miss)). [pack]
- **AI ranking/grades** (Greenhouse Talent Matching, Workday HiredScore): sort and prioritise;
  with hundreds of applicants, low-ranked profiles may simply be read later or not at all —
  **inference**, not documented as auto-rejection. [pack]
- **Volume** is the biggest practical filter: LinkedIn reports US applicants per open role have
  doubled since spring 2022 ([LinkedIn News, 2026](https://news.linkedin.com/2026/LinkedIn-Research-Talent-2026), acc. 2026-10-02). [pack]

EU/Italy legal frame: [pack]
- **GDPR art. 22**: right not to be subject to a decision "based solely on automated
  processing" with legal or similarly significant effects (exceptions: contract necessity, law,
  explicit consent, with safeguards) ([gdpr-info.eu art. 22](https://gdpr-info.eu/art-22-gdpr/)). Recital 71 names "e-recruiting
  practices without any human intervention" as an example and lists human intervention,
  explanation and the right to contest as safeguards ([Recital 71](https://gdpr-info.eu/recitals/no-71/), acc. 2026-10-02).
- **EU AI Act**: Annex III point 4(a) classes as **high-risk** AI "intended to be used for the
  recruitment or selection of natural persons, in particular … to analyse and filter job
  applications, and to evaluate candidates" ([AI Act Annex III](https://artificialintelligenceact.eu/annex/3/), acc. 2026-10-02). The Digital Omnibus
  (Reg. (EU) 2026/1744, OJ 24 Jul 2026) moved Annex III obligations from 2 Aug 2026 to
  **2 Dec 2027** ([Mondaq](https://www.mondaq.com/eu-digital-omnibus-on-ai-enters-into-force/1825722); [Ogletree](https://ogletree.com/insights-resources/blog-posts/eu-nears-approval-of-agreement-to-delay-rules-for-ai-use-in-employment-decisions/), acc. 2026-10-02 — secondary
  sources; check EUR-Lex before stating as final). Don't give legal advice; point to the rights.

> **[Guido] — Guido's take**
> Take the questions in the application form seriously: a wrong answer to an eligibility question (location,
> work permit, availability) can end the application before anyone opens the CV.

---

## 5. LinkedIn Easy Apply vs company site

How each reaches the employer (**documented**): [pack]
- A LinkedIn poster chooses **one** collection method, fixed after posting: receive applicants on
  LinkedIn, or "route candidates to an external website … or your company's applicant tracking
  system" ([LinkedIn Help a517570](https://www.linkedin.com/help/linkedin/answer/a517570/applicant-options-for-your-job-post?lang=en), acc. 2026-10-02).
- **Easy Apply, no integration**: candidate gives email, phone, CV (optional on Recruiter posts);
  the poster reviews applicants inside LinkedIn ([LinkedIn Help a414058](https://www.linkedin.com/help/recruiter/answer/a414058/application-flow-for-members-applying-for-your-job-posting?lang=en), acc. 2026-10-02). Candidate
  gets "viewed" / "resume downloaded" notifications, which "doesn't guarantee" a reply
  ([LinkedIn Help a508716](https://www.linkedin.com/help/linkedin/answer/a508716), acc. 2026-10-02).
- **Easy Apply with an ATS integration (Apply Connect)**: the candidate applies on LinkedIn and
  the application lands in the company's ATS (e.g. Greenhouse creates the profile, source
  "LinkedIn") ([Greenhouse Support](https://support.greenhouse.io/hc/en-us/articles/17073067102747-LinkedIn-Apply-Connect-integration); also Lever, Bullhorn —
  [Bullhorn KB](https://kb.bullhorn.com/ats/Content/BHATS/Topics/LinkedInApplyConnectOverview.htm), acc. 2026-10-02). So "Easy Apply never reaches the ATS" is false for these setups.
- **"Apply on company website"**: redirect to the URL the poster set (careers site/ATS). Then
  "LinkedIn doesn't keep a record of who applied" ([LinkedIn Help a414058](https://www.linkedin.com/help/recruiter/answer/a414058/application-flow-for-members-applying-for-your-job-posting?lang=en)). Hence the
  applicant count shown for off-site jobs cannot be completed applications; that it reflects Apply
  clicks is widely reported but **not** confirmed in LinkedIn Help found (ads reporting tracks
  "Job Apply Clicks" — [LinkedIn Help a414844](https://www.linkedin.com/help/linkedin/answer/a414844)). [pack]

Pros / cons (be honest about evidence): [pack]
- Easy Apply = fewer fields, faster → lower effort for everyone, so plausibly more volume per
  job; overall volume growth is documented (§4), Easy-Apply-specific volume/quality data from a
  primary source was **not found**. Claims like "Easy Apply converts at 0.5–2%" circulate on
  blogs without methodology — don't repeat them.
- Company site = usually more fields and screening questions, and the data sits in the ATS where
  the recruiter works. That it gets "taken more seriously" is **anecdotal** (recruiter opinion).
- When it's the **same ATS behind both** (Apply Connect), the channel matters less than the
  content and the screening answers. When Easy Apply is not integrated, applicants live in
  LinkedIn and some recruiters may check them less — **anecdotal**.
- Practical rule: if the posting offers "Apply on company website", that's where the employer
  wants applications; if only Easy Apply exists, use it — it is the employer's chosen channel.

> **[Guido] — Guido's take**
> If the company has an ATS, applying from LinkedIn or from its site changes little: either way you end up in
> the ATS. If it doesn't have one, the channel decides which "container" you land in: Easy Apply applications
> stay in LinkedIn, while the site may feed a sheet, a Notion or Airtable database or an inbox, and whoever
> screens may look at one before the other. Second reason: LinkedIn sometimes shows postings that are old,
> already closed or republished by aggregators and agencies. Applying from the company site confirms the role
> is still open and that you're applying to the company directly, not to an intermediary.

---

## 6. Practical tips

| Tip | Status |
|---|---|
| Use the posting's own words for skills/technologies you **really** have (helps search and AI matching on parsed text) | documented mechanism: matching on CV text vs job requirements ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/41131616864283-Talent-Matching-Data-Processing-FAQ), [Workday](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/reference--candidate-grades.html)); also [Guido] |
| Answer screening questions carefully and truthfully; they can auto-archive/reject | documented ([LinkedIn a519651](https://www.linkedin.com/help/linkedin/answer/a519651/add-screening-questions-to-your-job-post)) |
| Send a text-based PDF or a .docx; never a photo/scan of the CV | documented ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse), [Lever](https://help.lever.co/hc/en-us/articles/20087345054749-Understanding-Resume-Parsing)) |
| Keep the file under ~2.5 MB (compress photos) | documented for Greenhouse only |
| Put name and contacts in the body, not in header/footer/text box | documented ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse)) |
| Prefer a single-column layout; avoid tables for core content | documented as risk ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse), [Roche](https://careers.roche.com/de/de/resume-parsing-faq)); impact varies |
| Standard section headings (Experience, Education, Skills) | employer advice ([Roche](https://careers.roche.com/de/de/resume-parsing-faq)) / common practice |
| Consistent dates (month/year, start–end) for every role | common practice; Lever uses parsed dates for years of experience ([Lever](https://help.lever.co/hc/en-us/articles/20087345054749-Understanding-Resume-Parsing)) |
| Skills as text, not stars/bars | [Guido]; consistent with "graphics" as parse risk ([Greenhouse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse)) |
| After uploading on a careers site, check and fix the auto-filled fields | documented ([Roche](https://careers.roche.com/de/de/resume-parsing-faq)) / common practice |
| No hidden text, no keyword lists without context | evidence of backfire ([Built In](https://builtin.com/articles/hidden-ai-prompts-in-resume)); anecdotal on outcomes |
| Apply early on high-volume roles | anecdotal (52% of 25 recruiters, [Enhancv](https://enhancv.com/blog/does-ats-reject-resumes/)) |

> **[Guido] — Guido's take**
> Use the posting's keywords, but only for things you've really done (my CV guide, §1 and §7). Tailor the CV
> to the role, answer the form questions carefully, and remember that a human will read it.

---

## Not verified / open points

- Preptel's original 2012 material (only secondary accounts found).
- Workable, Recruitee, SmartRecruiters, Personio, iCIMS, inRecruiting (Zucchetti): no primary
  parsing docs retrieved — don't state their behaviour.
- No primary data on Easy Apply volume or quality vs company-site applications.
- Exact meaning of LinkedIn's applicant count on off-site jobs.
- AI Act Omnibus details from secondary sources; confirm on EUR-Lex.

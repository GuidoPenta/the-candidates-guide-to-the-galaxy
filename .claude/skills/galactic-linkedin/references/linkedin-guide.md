# Galactic LinkedIn Profile Guide — Operational Reference

Purpose: turn Guido Penta's LinkedIn guide for developers into checklists Claude can apply to a profile the user pastes (text or PDF export).

Source: https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers (© Guido Penta). The full guide lives there; this file is an operational summary.
Canonical (Italian) README: https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md
English translation: https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md
License: MIT (Copyright (c) 2023 Guido Penta). Keep the attribution when you reuse this material.

**Source labels.**
- **[Guido]**: a rule or opinion from Guido's guide, with its § (links: EN translation, IT canonical). Quote it as "your guide says…".
- **[pack]**: added by this skill (checks, templates, formulas, general advice). Not Guido's. Present it as Claude's own suggestion.
- Examples in the guide (Patryk's headline, the senior dev's About) are **inspiration**, not rules.

---

## How to use this reference [pack]

- Claude cannot log in to LinkedIn. It works only on what the user pastes: profile text, a "Save to PDF" export, or screenshots.
- A PDF export does not show the photo, the banner or the Open-to-Work setting. Check which skills the export shows, and whether they appear tied to experiences; **ask** about the rest. Do not guess.
- Go through the sections in the order below. For each one, report: what is there, what is missing, and a concrete rewrite (not generic advice).
- Guido's goal is simple: **get found**. The profile should be attractive, but above all **keyword-friendly** [Guido, intro]. If the user is not job hunting, the same rules still help them position the profile.
- Tone: Guido is a recruiter, not a techie, and writes with warmth and irony. Keep feedback direct, human and a little playful. Never be preachy.
- **Scope limit.** The guide does not cover: profile viewers, organic post views, hashtags, creator mode, the algorithm in depth, links in posts and comments, custom URL, Featured, privacy settings, or the profile language. If the user asks about these, say they are **outside Guido's guide** and label any advice as general [pack], not his.

---

## 0. Core principle: everything is a keyword ([§1 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#1-general-info) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#1-indicazioni-generali))

Recruiters search LinkedIn in two ways [Guido, §1]:
1. **Boolean strings.**
2. **Keywords + filters in LinkedIn Recruiter**, the paid license with many optimized search filters.

So **everything written on the profile is searchable** ("TUTTO ciò che è scritto sul tuo profilo è utile a farti trovare", §1). Apply this lens to every section.

Checklist:
- [ ] [Guido, §1] The user's main stack (languages, frameworks, tools, methodologies) appears **in words** across the profile. Every section is searchable.
- [ ] [Guido, §8] Skills: remove tech the user no longer wants to use professionally.
- [ ] [Guido, §5] "Content is king": a well-filled profile beats a bare one. Every filled field adds keywords.

---

## 1. General behaviour on the platform ([§1 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#1-general-info) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#1-indicazioni-generali))

### Replying to recruiters [Guido, §1]
- Many recruiters don't know dev jargon and **still confuse Java with JavaScript**. Guido asks devs to be **understanding and empathetic** anyway. There is a person working on the other side who deserves respect.
- **Always try to reply** to the messages you receive.
- Not looking right now? Prepare a **preset reply text** and send it. It costs a few seconds, and the recruiter will appreciate it.

Template written by this skill [pack], not from Guido's guide (adapt to the user's voice):
> Hi <Name>, thanks for reaching out and for thinking of me. I'm not looking for a new role right now, but I'm happy to stay in touch. Feel free to check back in <timeframe>, especially for <roles/stack the user cares about>. Have a great day!

### Open to Work [Guido, §1]
- Guido expects readers to think the green **#OpenToWork** frame isn't great, and to fear their current employer will "catch them out" if they turn it on.
- His answer: signal availability **to recruiters only**. Path: *Open to* button under the profile photo → *Finding a new job* → scroll to "choose who can see you're open" → **Recruiters only**. Recruiters using LinkedIn Recruiter then see an "open to work" note on the profile, and the public does not.
- Claude cannot see this setting. **Ask** the user which mode they use and mention "Recruiters only" if they worry about discretion.

### Activity and posting [Guido, §1]
- The advice that circulates online, which Guido reports but does not impose: **3–4 posts per week and at least 2 comments per day** keep the profile "algorithm-friendly".
- Guido's own position: **you don't have to post** if you have nothing interesting to say. LinkedIn's value is valuable content. He posts about **once a week**, **comments a lot**, and keeps relationships alive. **Private messages also "trigger" the algorithm.**
- Find **your own tone of voice**. "Not communicating is also communicating."

Checklist:
- [ ] [Guido, §1] Does the user have a preset reply for recruiters when not looking? If not, offer a draft.
- [ ] [Guido, §1] Is the Open-to-Work visibility a conscious choice (public frame vs. recruiters only)?
- [ ] [pack] Is there an activity rhythm that fits the user (commenting and messaging count, not only posting)?

---

## 2. Profile photo and cover (banner) ([§2 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#2-profile--and-cover-photo) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#2-foto-profilo-e-foto-copertina))

[Guido, §2] **Photo: FUNDAMENTAL on LinkedIn**, more than on the CV. Guido cites a study: profiles with a professional photo get **20x profile views**.
- DO: a professional photo.
- DON'T: grainy photos, 20-year-old passport photos, beach photos.
- No suitable photo? An **avatar or illustration is fine**, but it must look professional (not "done with Paint").

[Guido, §2] **Cover image: not essential in Guido's opinion**, but he would use it to give the profile a **personal touch** and "convey something": a piece of code, a famous quote, a meme.

Checklist (ask the user, because a PDF export does not include images):
- [ ] [Guido, §2] Is there a photo? Is it professional (quality, recent, suitable context)?
- [ ] [Guido, §2] If avatar or illustration: is it professional-looking?
- [ ] [Guido, §2] Is the banner used to say something about the person (code, quote, meme), not left as the default?

---

## 3. Headline ([§3 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#3-the-headline) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#3-la-headline))

[Guido, §3] The headline is the text right under the photo. After the photo and cover, it deserves the **utmost attention**:
1. At a glance, it must communicate "chi sei, cosa fai (ed eventualmente, cosa cerchi)": who you are, what you do and, possibly, what you're looking for.
2. Every technology in it is a **keyword**. Someone searching for "TypeScript + React" lands on profiles whose headline contains them.

Guido's example (inspiration, not a rule) is Patryk's headline: a very active dev with a well-kept profile. Why Guido says it works:
- a quick overview of the **stack he uses**, FE and BE;
- **one extra cue** about his passion for open source.
Its shape is roughly `<Role> | <passion cue> | Frontend: <tech…> | Backend: <tech…> | <tools…>`, with emoji as separators.

Headline formulas written by this skill [pack], inspired by the example in §3. Keep the stack as explicit keywords:
- `<Role> | <Passion/cause> | Frontend: <A, B, C> | Backend: <D, E> | <Infra/Tools>: <F, G>`
- `<Seniority> <Role> @ <Company> | <Core stack A, B, C> | <What you're looking for / focus>`
- `<Role> | <Primary language/framework> · <secondary> · <tools> | <Differentiator: OSS, mentoring, community…>`

Checklist:
- [ ] [Guido, §3] It is not just the job title. Make the most of it ("Sfruttala AL MASSIMO").
- [ ] [Guido, §3] It says who the user is and what they do, with the concrete stack as searchable keywords; optionally what they're looking for.
- [ ] [pack] Options: like Patryk's example, it can group the stack by area and add a passion cue.
- [ ] [pack] Check: does the headline stack show up in the Skills section and recent experience? Point out gaps; the user decides.

---

## 4. About ([§4 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#4-about-me-section) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#4-sezione-informazioni))

[Guido, §4] Like the CV "About me", but here it gives an **in-depth overview**:
- work experience;
- languages, technologies and frameworks known and used;
- **future goals**;
- day-to-day activities;
- and, deliberately, "not very useful" info that completes the picture: **hobbies, free time, books you're reading, people you follow, side projects**.

Guido's example (inspiration, not a rule) is a senior dev's About. He calls it extremely detailed and says it contains all the information a recruiter needs: a short self-description and approach to work, an **exhaustive list** of technologies, languages, frameworks, software and methodologies ("SONO TUTTE KEYWORD!"), plus team management, running technical interviews and Agile habits. "Prendi spunto!" The example organizes its list roughly like this:
- "Design and implementation of software using:" → languages and frameworks
- "driven by:" → TDD, BDD, DDD
- "with:" → IDEs and tools
- "keeping in mind the Agile Manifesto:" → Kanban/Scrum plus tools
- "following the DevOps philosophy with:" → CI/CD, containers, cloud

Template written by this skill [pack], not from Guido's guide. Claude can fill it with the user's data:
```
<1–3 sentences: who I am, how I approach work, what I'm focused on now.>

What I've worked with so far:
→ Building software with: <languages & frameworks>
→ Driven by: <practices: TDD / BDD / DDD / clean code…>
→ Using: <IDEs, databases, tools>
→ Working in: <Agile/Scrum/Kanban + tools>
→ Shipping with: <CI/CD, containers, cloud>
→ Beyond code: <mentoring, tech interviews, team facilitation…>

What I'm looking for next: <goal / role / domain>.
Outside work: <hobbies, books, side projects, communities>.
```

Checklist:
- [ ] [Guido, §4] It exists and gives an in-depth overview, not a one-liner.
- [ ] [Guido, §4] It describes the person and their approach, not only a list.
- [ ] [Guido, §4] It lists technologies, methodologies and tools. The §4 example shows an exhaustive, organized version worth taking a cue from ("Prendi spunto!").
- [ ] [Guido, §4 example] It mentions responsibilities beyond code, if true (team, interviews, Agile).
- [ ] [Guido, §4] It states future goals.
- [ ] [Guido, §4] It includes a personal touch (hobbies, side projects, books).

---

## 5. Experience — "one of the most important sections, if not THE most important" ([§5 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#5-professional-experiences) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#5-le-esperienze-professionali))

[Guido, §5]
- **Use the Description field** of every role. Describe briefly:
  - what you do at the company;
  - duties and **daily tasks**;
  - **technologies**;
  - the company's **industry/sector**.
  All of it is keywords.
- **Hook skills to each position.** LinkedIn lets you tie skills to an experience. This shows a professional "history" consistent with what you do now or did before.
- **Link the right company page.** Guido often sees typos in the company name. Then LinkedIn shows no logo, and a recruiter cannot check the company's industry, size and so on. Select the correct company.
- **Content is king**: a well-edited profile full of information beats a bare one. "The effort is noticed."

Checklist (per role):
- [ ] [Guido, §5] The Description is not empty. It covers role, tasks, tech and the company's sector.
- [ ] [Guido, §5] Skills are tied to the role (ask the user, because a PDF export may not show it).
- [ ] [Guido, §5] The company is linked to its real page (ask, or flag a suspicious spelling). No logo usually means it is not linked.
- [ ] [pack, derived from "Content is king", §5] Older roles are filled in too, not only the current one.

---

## 6. Education ([§6 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#6-training-experiences) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#6-la-formazione))

[Guido, §6] It is often overlooked, but **LinkedIn Recruiter filters read it**: specific degree, university, field of study. Fill it in thoroughly:
- [ ] Faculty or university name.
- [ ] Field of study.
- [ ] **Final grade.**
- [ ] **Names of exams** relevant to the career path.
- [ ] **IT Academy / Bootcamp** listed if the user attends or attended one. It shows them as a student there and adds keywords for the technologies studied.

---

## 7. Licenses and certifications ([§7 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#7-licenses-and-certifications) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#7-licenze-e-certificazioni))

[Guido, §7] One of the sections Guido reads with the most interest.
- Caveat in his own words: he is not a techie and can't judge the real "technical value" of one certification over another ("non sono un tecnico… non riesco a carpire il reale 'valore tecnico' di una certificazione"). He values them as a sign of **self-training**.
- Some companies **require** certifications to apply or to be promoted. He mentions Six Sigma Green Belt for PMs, and AWS/Azure/Google Cloud certifications.
- Even when not required, certifications show a drive to grow. Guido treats that as a plus and a **great conversation starter** in interviews.
- Put **language certificates** here too (see §9).

Checklist:
- [ ] [Guido, §7] Real certifications, courses and licenses are listed, including optional or self-driven ones.
- [ ] [pack] Cloud and vendor certifications that match target roles are visible.

---

## 8. Skills — "SUPER SUPER important", together with Experience ([§8 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#8-skills) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#8-competenze))

[Guido, §8] Guido sees EXTREMELY often that devs neglect this section. It weighs heavily on whether the user appears in recruiters' searches ("alimenta in maniera decisamente importante").

Rules [Guido, §8]:
- **Keep it updated. Remove** technologies the user no longer uses, or knows but no longer wants to use professionally. Otherwise they will get offers for stacks they don't want.
- **Sort by strength**: strongest skills at the top, weakest at the bottom.
- **Top 3**: LinkedIn highlights three skills. Pick the three where the user feels strongest and move them up.
- **Tie skills to experiences** (see §5).
- **Ask colleagues, friends and connections for endorsements.** Guido admits it's a pure vanity metric, but the "wow effect" of many endorsements works, so do it.

Checklist:
- [ ] [Guido, §8] No outdated or unwanted tech is listed.
- [ ] [Guido, §8] Order reflects real strength. The top 3 are the three where the user feels strongest.
- [ ] [pack] Check: do the stack items in the headline and About also appear as Skills? Point out gaps; the user decides.
- [ ] [Guido, §8] Skills are linked to the roles where they were used.
- [ ] [Guido, §8] Suggest who could endorse the key skills.

---

## 9. Languages ([§9 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#9-languages) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#9-lingue))

[Guido, §9]
- List the languages the user knows beyond the mother tongue (Guido writes for an Italian market, so "beyond Italian"). Guido sometimes runs selections where English is compulsory (international team, foreign clients, expansion abroad), and this section helps him check that requirement.
- Put language certificates under **Licenses and certifications**.

Checklist:
- [ ] [Guido, §9] Languages beyond the mother tongue are listed.
- [ ] [pack] English is present if the user targets international roles.
- [ ] [Guido, §9] Any language certificate appears under Certifications.

---

## 10. Recommendations ([§10 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#10-references) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#10-referenze))

[Guido, §10] Guido calls them "a very powerful weapon that very few people really take advantage of".
- Everyone has a colleague, manager, former boss, collaborator or external consultant to ask ("collega, manager, ex-capo, collaboratore, consulente esterno"). It costs a few minutes and strongly boosts the profile and personal branding.
- His anecdote: a dev's profile did not convince him at first glance. Then he saw a recommendation from a senior manager he knew well. It made him reach out, and the interview confirmed what the recommendation said. **Without it, he would probably never have contacted that person.**

Checklist:
- [ ] [Guido, §10] Does the profile have received recommendations? None yet: worth asking ("un'arma potentissima che davvero in pochissimi sfruttano").
- [ ] [Guido, §10] Identify 2–3 people to ask: colleague, manager, former boss, collaborator, external consultant.
- [ ] [pack] Offer to draft the request message. Sending it is the user's action.

Template written by this skill [pack], not from Guido's guide:
> Hi <Name>, I really enjoyed working with you on <project/team> at <Company>. I'm updating my LinkedIn profile: would you be willing to write a short recommendation about <specific thing: e.g. how I handled X / my work on Y>? Happy to return the favour!

---

## 11. Publications ([§11 EN](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#11-publications) · [IT](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/README.md#11-pubblicazioni))

[Guido, §11]
- A "respectable" section that enriches the profile. Research- and innovation-oriented companies appreciate it most.
- "If you have publications, do not hesitate to post them!"
- The companion CV guide (§10) adds useful detail for each entry: title, date, authors, venue or journal, DOI.

Checklist:
- [ ] [Guido, §11] Papers, articles or talks are listed, if any exist.

---

## 12. Review output format for Claude [pack]

When reviewing a pasted profile, produce:
1. **Keyword map**: the user's target stack or roles, checked against where each keyword appears (Headline / About / Experience / Skills). Flag gaps.
2. **Section-by-section verdict** following §2–§11 above: present / weak / missing, each with a concrete rewrite. Say which points are Guido's rules and which are Claude's suggestions.
3. **Questions for what the export can't show**: photo, banner, Open-to-Work mode, skills the export doesn't show, skills tied to roles, company pages linked.
4. **Top 3 fixes** ranked by impact on being found. Usually headline, Skills and experience descriptions.
5. Remind the user that Claude writes drafts only. The user updates LinkedIn and sends any message themselves.

---

## 13. Consistency with CV [pack]

Cross-check added by this skill [pack], not a rule from Guido's guides. Claude compares CV and LinkedIn and points out mismatches; the user decides. The LinkedIn guide does refer to the CV guide as its companion: https://github.com/GuidoPenta/galactic-CV-guide-for-developers (Italian `index.md` canonical; English: `docs/english.md`).

Check:
- [ ] **Roles, companies, dates**: check that titles, employers and dates match, and that the career progression (e.g. Dev → Senior → Team Lead, CV §5) reads the same way.
- [ ] **Stack and order**: both guides put the strongest skills first (CV §7, LinkedIn §8). The CV order can change per target role, so just check there's no obvious contradiction. The CV guide warns that ATSs may not read stars or progress bars (CV §7).
- [ ] **Keywords**: check that the technologies in the CV experience bullets also show up in the LinkedIn experience descriptions. The CV can be tailored per job; point out anything that looks contradictory.
- [ ] **About**: different jobs. The CV About summarizes experience, technologies, work and personal goals, optionally side projects and hobbies (CV §4). The LinkedIn About is the in-depth version (LinkedIn §4). Check that goals and focus don't clash.
- [ ] **Education**: check degree, grade and institution. LinkedIn can add exam names (LinkedIn §6). Bootcamp and its technologies go on both (CV §6, LinkedIn §6); the CV guide also lists the thesis title (CV §6).
- [ ] **Certifications and courses**: check the lists; point out anything on one side only.
- [ ] **Languages**: check languages and levels. Certificates go on both (CV §11, LinkedIn §9).
- [ ] **Publications**: check the entries.
- [ ] **Photo**: on the CV it's the user's choice (CV §2); on LinkedIn it's fundamental (LinkedIn §2).
- [ ] **Links**: the CV should include a **clickable LinkedIn URL**, plus GitHub, and a portfolio if the user has one (CV §3).
- [ ] **CV language**: Guido's rule (clarified by him on 2026-09-25; the published CV guide §1 still says "se in italiano invialo in italiano"): English ad → English CV; Italian ad → Italian or English, both fine. The CV guide also recommends having two versions. The LinkedIn guide says nothing about profile language; any advice on it is [pack].
- [ ] **Soft skills and hobbies**: the CV guide asks for "real" soft skills, not the usual clichés (CV §8), and a hobbies section (CV §11). Check that the LinkedIn About doesn't contradict them.

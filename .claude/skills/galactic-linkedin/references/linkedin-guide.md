# Galactic LinkedIn Profile Guide — Operational Reference

Purpose: turn Guido Penta's LinkedIn guide for developers into checklists Claude can apply to a profile the user pastes (text or PDF export).

Source: https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers (© Guido Penta). The full guide lives there; this file is an operational summary.
English page: https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md
License: MIT (Copyright (c) 2023 Guido Penta). Keep the attribution when you reuse this material.

---

## How to use this reference

- Claude cannot log in to LinkedIn. It works only on what the user pastes: profile text, a "Save to PDF" export, or screenshots.
- A PDF export does not show the photo, the banner, the Open-to-Work setting, the order of pinned skills or which skills are tied to which experience. **Ask** about these. Do not guess.
- Go through the sections in the order below. For each one, report: what is there, what is missing, and a concrete rewrite (not generic advice).
- Guido's goal is simple: **get found**. The profile should be attractive, but above all **keyword-friendly**. If the user is not job hunting, the same rules still help them position the profile.
- Tone: Guido is a recruiter, not a techie, and writes with warmth and irony. Keep feedback direct, human and a little playful. Never be preachy.
- **Scope limit.** The guide leaves some topics out on purpose: profile viewers, organic post views, hashtags, creator mode, the algorithm in depth, links in posts and comments. It also has no dedicated section on custom URL, Featured or privacy settings. If the user asks about these, say they are **outside Guido's guide** and label any advice you give as general, not his.

---

## 0. Core principle: everything is a keyword ([§1](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#1-general-info))

Recruiters search LinkedIn in two ways:
1. **Boolean strings.**
2. **Keywords + filters in LinkedIn Recruiter**, the paid license with many optimized search filters.

So **EVERYTHING written on the profile is searchable** and decides whether the user shows up in targeted searches. Apply this lens to every section.

Checklist:
- [ ] The user's main stack (languages, frameworks, tools, methodologies) appears **in words**, spelled the canonical way (e.g. "TypeScript", not only "TS"), in the headline, the About, the experience descriptions **and** Skills.
- [ ] Technologies the user does NOT want to be contacted for are not advertised (see Skills).
- [ ] No section is left empty "because it doesn't matter". Every filled field adds keywords.

---

## 1. General behaviour on the platform ([§1](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#1-general-info))

### Replying to recruiters
- Many recruiters don't know dev jargon and **still confuse Java with JavaScript**. Guido asks devs to be **understanding and empathetic** anyway. There is a person working on the other side who deserves respect.
- **Always try to reply** to the messages you receive.
- Not looking right now? Prepare a **preset reply text** and send it. It costs a few seconds, and the recruiter will appreciate it.

Template Claude can offer (adapt to the user's voice):
> Hi <Name>, thanks for reaching out and for thinking of me. I'm not looking for a new role right now, but I'm happy to stay in touch. Feel free to check back in <timeframe>, especially for <roles/stack the user cares about>. Have a great day!

### Open to Work
- Guido's view: people underrate the green **#OpenToWork** frame and fear their current employer will "catch them out".
- The alternative: signal availability **to recruiters only**. Path: *Open to* button under the profile photo → *Finding a new job* → scroll to "choose who can see you're open" → **Recruiters only**. Recruiters using LinkedIn Recruiter then see an "open to work" note on the profile, and the public does not.
- Claude cannot see this setting. **Ask** the user which mode they use and suggest "Recruiters only" if they worry about discretion.

### Activity and posting
- The advice that circulates online, which Guido reports but does not impose: **3–4 posts per week and at least 2 comments per day** keep the profile "algorithm-friendly".
- Guido's own position: **you don't have to post** if you have nothing interesting to say. LinkedIn's value is valuable content. He posts about **once a week**, **comments a lot**, and keeps relationships alive. **Private messages also "trigger" the algorithm.**
- Help the user find **their own tone of voice**. "Not communicating is also communicating."

Checklist:
- [ ] Does the user have a preset reply for recruiters? If not, draft one.
- [ ] Is the Open-to-Work visibility a conscious choice (public frame vs. recruiters only)?
- [ ] Is there a realistic activity rhythm that fits the user (commenting and messaging count, not only posting)?

---

## 2. Profile photo and cover (banner) ([§2](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#2-profile--and-cover-photo))

**Photo: FUNDAMENTAL on LinkedIn**, more than on the CV. Guido cites a study: profiles with a professional photo get **20x profile views**.
- DO: a professional photo.
- DON'T: grainy photos, 20-year-old passport photos, beach photos.
- No suitable photo? An **avatar or illustration is fine**, but it must look professional (not "done with Paint").

**Cover image: not essential in Guido's opinion**, but use it to give the profile a **personal touch** and "convey something": a piece of code, a famous quote, a meme.

Checklist (ask the user, because a PDF export does not include images):
- [ ] Is there a photo? Is it professional (quality, recent, suitable context)?
- [ ] If avatar or illustration: is it professional-looking?
- [ ] Is the banner used to say something about the person (code, quote, meme, tech identity), not left as the default?

---

## 3. Headline ([§3](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#3-the-headline))

The headline is the text right under the photo. After the photo and cover, it deserves the **utmost attention**. Two reasons:
1. At a glance, it communicates **who you are, what you do and, possibly, what you're looking for**.
2. Every technology in it is a **keyword**. Someone searching for "TypeScript + React" lands on profiles whose headline contains them.

Guido's reference example is a developer's headline: very active, well-maintained profile. Its structure:
`<Role> | <passion/extra cue, e.g. Open Source> | Frontend: <tech, tech, tech…> | Backend: <tech, tech…> | Server: <tools…>`
- It uses emoji as visual separators between blocks.
- It lists the **whole stack by area** (FE / BE / infra).
- It adds **one human or passion cue** (open source).

Headline formulas Claude can propose. All are derived from that example, so keep the stack as explicit keywords:
- `<Role> | <Passion/cause> | Frontend: <A, B, C> | Backend: <D, E> | <Infra/Tools>: <F, G>`
- `<Seniority> <Role> @ <Company> | <Core stack A, B, C> | <What you're looking for / focus>`
- `<Role> | <Primary language/framework> · <secondary> · <tools> | <Differentiator: OSS, mentoring, community…>`

Checklist:
- [ ] The headline is NOT just "<Job title> at <Company>" (LinkedIn's default). Make the most of it.
- [ ] It names the role **and** the concrete stack as searchable keywords.
- [ ] It groups tech by area when the user is full-stack.
- [ ] It includes one cue about passions or focus, and optionally what the user is looking for.
- [ ] Its stack matches the Skills section and the recent experience.

---

## 4. About ([§4](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#4-about-me-section))

Like the CV "About me", but here it gives an **in-depth overview**:
- work experience;
- languages, technologies and frameworks known and used;
- **future goals**;
- day-to-day activities;
- and, deliberately, "not very useful" info that completes the picture: **hobbies, free time, books you're reading, people you follow, side projects**.

Guido's reference example is a senior dev's About. He calls it extremely detailed and says it contains "all the information a recruiter needs". Its structure:
1. **Short self-description and approach to work**: e.g. "I like to solve problems…", methodologies as tools, current focus.
2. **Exhaustive tech list**, organized hierarchically with arrows or bullets:
   - "Design and implementation of software using:" → languages and frameworks
   - "driven by:" → Test / Behavior / Domain (TDD, BDD, DDD)
   - "with:" → IDEs and tools
   - "keeping in mind the Agile Manifesto:" → Kanban/Scrum plus tools (Jira, Trello…)
   - "following the DevOps philosophy with:" → CI/CD, containers, cloud
3. **Extra signals**: team coaching and facilitation, **running technical interviews**, Agile habits.

Guido's lesson: every item in that list is a **keyword**.

About template Claude can fill with the user's data:
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
- [ ] It exists and is not a one-liner.
- [ ] It describes the person and their approach, not only a list.
- [ ] It contains an exhaustive, organized list of technologies, methodologies and tools, all spelled as keywords.
- [ ] It mentions responsibilities beyond code, if true (team lead, mentoring, interviews, Agile).
- [ ] It states future goals or what the user is looking for.
- [ ] It includes a personal touch (hobbies, side projects, books).

---

## 5. Experience — "by far one of the most important sections, if not THE most important" ([§5](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#5-professional-experiences))

- **Use the Description field** of every role. Describe briefly:
  - what you do at the company;
  - duties and **daily tasks**;
  - **technologies**;
  - the company's **industry/sector**.
  All of it is keywords.
- **Hook skills to each position.** LinkedIn lets you tie skills to an experience. This shows a professional "history" consistent with what you do now.
- **Link the right company page.** Guido often sees typos in the company name. Then LinkedIn shows no logo, and a recruiter cannot click through to read about the company's industry, size and so on. Select the correct company from the list.
- **Content is king**: a well-edited profile full of information beats a bare one. "The effort is noticed."

Checklist (per role):
- [ ] The Description is not empty. It covers role, tasks, tech and the company's sector.
- [ ] Skills are tied to the role (ask the user, because a PDF export may not show it).
- [ ] The company is linked to its real page (ask, or flag a suspicious spelling). If there is no logo in the user's view, it is probably not linked.
- [ ] Older roles are filled in too, not only the current one.

---

## 6. Education ([§6](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#6-training-experiences))

It is often overlooked, but **LinkedIn Recruiter filters read it**: specific degree, university, field of study. Fill it in thoroughly:
- [ ] Faculty or university name (linked correctly).
- [ ] Field of study.
- [ ] **Final grade.**
- [ ] **Names of exams** relevant to the career path.
- [ ] **IT Academy / Bootcamp** listed if the user attends or attended one. It shows them as a student there and adds keywords for the technologies studied.

---

## 7. Licenses and certifications ([§7](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#7-licenses-and-certifications))

This is one of the sections Guido reads with the most interest.
- Some companies **require** certifications to apply or to be promoted. He mentions Six Sigma Green Belt for PMs, and AWS/Azure/Google Cloud certifications.
- Even when they are not required, certifications show an **approach to self-training** and a drive to grow. Guido treats that as a plus and a **great conversation starter** in interviews.
- Put **language certificates** here too (see §9).

Checklist:
- [ ] All real certifications, courses and licenses are listed, including optional or self-driven ones.
- [ ] Cloud and vendor certifications that match target roles are visible.

---

## 8. Skills — "SUPER SUPER important", together with Experience ([§8](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#8-skills))

Guido sees EXTREMELY often that devs neglect this section. It is the section that most directly decides whether the user appears in recruiters' searches.

Rules:
- **Keep it updated. Remove** technologies the user no longer uses, or knows but no longer wants to use professionally. Otherwise they will get offers for stacks they don't want.
- **Sort by strength**: strongest skills at the top, weakest at the bottom.
- **Top 3**: LinkedIn highlights three skills. Move the three strongest there.
- **Tie skills to experiences** (see §5).
- **Ask colleagues, friends and connections for endorsements.** Guido admits it's a pure vanity metric, but the "wow effect" of many endorsements works, so do it.

Checklist:
- [ ] No outdated or unwanted tech is listed.
- [ ] Order reflects real strength. The top 3 are the user's best **and** most wanted skills.
- [ ] Every stack item in the headline and About also appears as a Skill.
- [ ] Skills are linked to the roles where they were used.
- [ ] Suggest who could endorse the key skills.

---

## 9. Languages ([§9](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#9-languages))

- List every language beyond the mother tongue. Guido writes for an Italian market, so "beyond Italian" there. Many selections make **English compulsory** (international team, foreign clients, expansion abroad), and recruiters check this section to verify it.
- Put language certificates under **Licenses and certifications**.

Checklist:
- [ ] All languages are listed with a realistic proficiency level.
- [ ] English is present if the user targets international roles.
- [ ] Any language certificate appears under Certifications.

---

## 10. Recommendations ([§10](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#10-references))

Guido calls them "a very powerful weapon that very few people really take advantage of".
- Everyone has a colleague, manager, former boss, collaborator or external consultant to ask. It costs a few minutes and strongly boosts the profile and personal branding.
- His anecdote: a dev's profile did not appeal to him at first glance. Then he saw a recommendation from a senior manager he knew and trusted. It made him reach out, and the interview confirmed what the recommendation said. **Without it, he would never have contacted that person.**

Checklist:
- [ ] Does the profile have received recommendations? Zero is a gap to fix.
- [ ] Identify 2–3 people to ask, ideally senior or well-connected (managers, leads, clients).
- [ ] Offer to draft the request message. Sending it is the user's action.

Request template:
> Hi <Name>, I really enjoyed working with you on <project/team> at <Company>. I'm updating my LinkedIn profile: would you be willing to write a short recommendation about <specific thing: e.g. how I handled X / my work on Y>? Happy to return the favour!

---

## 11. Publications ([§11](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers/blob/main/english.md#11-publications))

- A "respectable" section that enriches the profile. Research- and innovation-oriented companies appreciate it most.
- "If you have publications, do not hesitate to post them!"
- The companion CV guide adds useful detail for each entry: title, date, authors, venue or journal, DOI.

Checklist:
- [ ] Papers, articles, conference talks or technical blog posts are listed, if any exist.

---

## 12. Review output format for Claude

When reviewing a pasted profile, produce:
1. **Keyword map**: the user's target stack or roles, checked against where each keyword appears (Headline / About / Experience / Skills). Flag gaps.
2. **Section-by-section verdict** following §2–§11 above: present / weak / missing, each with a concrete rewrite.
3. **Questions for what the export can't show**: photo, banner, Open-to-Work mode, top-3 skills, skills tied to roles, company pages linked.
4. **Top 3 fixes** ranked by impact on being found. Usually headline, Skills and experience descriptions.
5. Remind the user that Claude writes drafts only. The user updates LinkedIn and sends any message themselves.

---

## 13. Consistency with CV

Guido wrote the LinkedIn guide as a companion to his CV guide: https://github.com/GuidoPenta/galactic-CV-guide-for-developers (English: `docs/english.md`). The two must tell **the same story**. Recruiters open the LinkedIn link from the CV and compare. Check:

- [ ] **Roles, companies, dates**: titles, employers and start/end dates are identical on both. The career progression (e.g. Dev → Senior → Team Lead) reads the same way.
- [ ] **Stack and order**: the CV's tech skills are listed strongest or daily-use first. LinkedIn's Skills order and top 3 must reflect the same priority. The CV guide warns that ATSs may not read stars or progress bars. On LinkedIn, the order itself is the signal.
- [ ] **Keywords**: the same technologies appear in the CV experience bullets and the LinkedIn experience descriptions. The CV can be tailored per job, but LinkedIn must not contradict it.
- [ ] **About**: the CV "About me" (current title, stack, team responsibilities, what you're looking for, hobbies) should be a condensed version of the LinkedIn About. Same goals, same focus.
- [ ] **Education**: same degree, grade and institution. The LinkedIn version can hold more detail (exams, bootcamp tech).
- [ ] **Certifications and courses**: the same list on both. LinkedIn may be more complete.
- [ ] **Languages**: same languages and levels. Certificates on both.
- [ ] **Publications**: the same entries.
- [ ] **Photo**: if the CV has one, it follows the same professional rules and should ideally be the same or a similar photo. The CV guide leaves including a photo up to you. On LinkedIn, Guido calls it fundamental.
- [ ] **Links**: the CV must include a **clickable LinkedIn URL** (plus GitHub and portfolio), as the CV guide requires.
- [ ] **Language of the profile vs. target market**: the CV guide says an English ad needs an English CV (an Italian ad accepts either) and to keep two CV versions (IT and EN). Make sure the LinkedIn profile, or its secondary-language version, fits the market the user targets.
- [ ] **Soft skills and hobbies**: the CV guide asks for "real" soft skills (not the usual clichés) and a hobbies section. LinkedIn's About should carry the same personality, with no contradictions.

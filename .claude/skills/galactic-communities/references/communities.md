# Communities, remote job sources, conferences and mentorship (Italy-focused)

> **Snapshot dated 2026-09-25.** This file is a curated copy, not the source of truth.
> The canonical lists live upstream and change often. **If web access is available, fetch the
> upstream list before recommending anything**, and prefer it over this snapshot when they differ.
>
> | List | Canonical upstream | Raw file to fetch |
> |---|---|---|
> | Italian tech communities | https://github.com/GuidoPenta/awesome-italian-tech-communities (site: https://guidopenta.github.io/awesome-italian-tech-communities/) — this repo *is* the upstream, not a fork | https://raw.githubusercontent.com/GuidoPenta/awesome-italian-tech-communities/main/README.md |
> | Remote-friendly companies | https://github.com/italiaremote/awesome-italia-remote (web view: https://italiaremote.com/companies). `GuidoPenta/awesome-italia-remote` is a fork | README (generated): https://raw.githubusercontent.com/italiaremote/awesome-italia-remote/main/README.md — one JSON per company in `data/` |
> | Italian tech conferences | https://github.com/techconfit/techconfit.github.io (site: https://techconfit.github.io). `GuidoPenta/tech-conferences-italy` is a fork | one Markdown file per event in `_conferences/` (front matter: `name`, `website`, `location`, `date_start`, `date_end`) |
> | Welyk job board | https://github.com/GuidoPenta/welyk-job-board (site: https://guidopenta.github.io/welyk-job-board/) | https://raw.githubusercontent.com/GuidoPenta/welyk-job-board/main/README.md |
>
> Verification legend: **verified** = checked on the official site or repo on 2026-09-25;
> **unverified** = appears only in a secondary list and was not opened. Invite links
> (`t.me/+...`, `discord.gg/...`) can expire: if one fails, look for a fresh link on the
> community's own site or socials, never on random aggregators.
>
> **Source labels.** **[Guido]** = from Guido's lists (awesome-italian-tech-communities, welyk-job-board).
> **[pack]** = this skill pack's own note or general practice. **[Dataskew]** = from Dataskew's own site.
> Third-party lists (Awesome Italia Remote, techconfit) are cited by name.
>
> **Dataskew: don't fetch dataskew.io automatically.** Its terms forbid automated access (scrapers, scripted
> requests). Link it and describe it from this file; the user visits it.

---

## How Claude should use this file

1. Read the user's profile (role, stack, seniority, city, remote preference, language) from the workspace.
2. Filter the entries below by tags. Recommend **5–8 entries at most**, each with *why it fits this user*
   and *one concrete first action* (e.g. "introduce yourself in the #presentazioni topic with stack + city + what you're looking for").
3. Always consider the **Featured** section first: those are the most job-search-relevant places for an Italian tech audience.
4. Most communities are **Italian-speaking**. Tell non-Italian speakers when a place is Italian-only.
5. Never join, post or send messages on the user's behalf. Give links and draft an intro message the user can post themselves.

### Tag scheme

Each entry carries tags in backticks. Combine them to filter.

| Prefix | Values | Meaning |
|---|---|---|
| `role:` | `dev`, `frontend`, `backend`, `mobile`, `devops`, `cloud`, `sysadmin`, `data`, `ai`, `security`, `leadership` (CTO/EM/lead), `product`, `design`, `qa`, `hr`, `any` | who gets the most out of it |
| `stack:` | `python`, `go`, `rust`, `js`, `ts`, `react`, `vue`, `angular`, `flutter`, `dotnet`, `blazor`, `php`, `laravel`, `symfony`, `java`, `kotlin`, `android`, `swift`, `ruby`, `nim`, `kubernetes`, `rabbitmq`, `yocto`, `linux`, `aws`, `azure`, `gcp` | technology focus |
| `city:` | `milano`, `roma`, `torino`, `firenze`, `bologna`, `venezia`/`veneto`, `treviso`, `marche`, `online` | physical base (for meetups) |
| `work:` | `remote`, `jobs`, `career`, `salary`, `mentorship`, `learning`, `networking`, `opensource`, `events` | what it is useful for in a job search |
| `format:` | `telegram`, `discord`, `slack`, `matrix`, `meetup`, `podcast`, `youtube`, `twitch`, `instagram`, `site`, `newsletter`, `jobboard` | channel |
| `lang:` | `it`, `en` | main language |
| `level:` | `junior`, `mid`, `senior`, `any` | seniority fit (only when obvious) |

---

## Featured

### La Locanda del Tech
- **What it is (verified):** Italian community around a live-streaming show about working in tech: careers,
  money and RAL (salary) transparency, professional growth, recruiting, personal branding, memes.
  Hosted by **Guido Penta** (tech recruiter, welyk.tech) according to Italia Open Source's community page.
  Has its own open-source Telegram bot (`La-Locanda-Del-Tech/locanda-bot`, TypeScript + grammY).
- **Who it's for:** developers and tech workers in Italy at any level who want to talk openly about
  salaries, job offers, interviews and career moves. Italian-speaking.
- **Links (verified):**
  - Telegram group: https://t.me/+mqQJQ9BqKOViMmVk (same invite link in the awesome list, the bot repo and Italia Open Source)
  - Twitch: https://www.twitch.tv/lalocandadeltech
  - YouTube: https://www.youtube.com/@lalocandadeltech
  - Podcast (Spotify): https://open.spotify.com/show/15LgWGdHeYb2NifJ5TTec7
  - TikTok: https://www.tiktok.com/@la.locanda.tech
  - GitHub org: https://github.com/La-Locanda-Del-Tech
  - Listing: https://italiaopensource.com/communities/la-locanda-del-tech
- **How to join:** open the Telegram invite link and join the group; follow Twitch for the live shows.
  No dedicated website found (unverified whether one exists).
- **Tags:** `role:any` `work:career` `work:salary` `work:jobs` `work:networking` `format:telegram` `format:twitch` `format:youtube` `format:podcast` `lang:it` `level:any`

### Full Remote (fullremote.it)
- **What it is (verified):** independent Italian project that curates **genuinely full-remote** job offers
  in tech and digital, reviewed by hand rather than scraped. Created and run by **Francesco Napoletano**
  (developer). It is explicitly *not* a recruitment agency: it does not collect CVs or manage applications;
  candidates apply directly on the company's page. Free for job seekers (no paywall).
  TrackZilla (see galactic-tracker) was born as an idea in its Telegram chat.
- **Who it's for:** Italian tech workers who want full-remote roles: software engineering (frontend, backend,
  fullstack), product, data, design.
- **Links (verified):**
  - Site + job board: https://www.fullremote.it/
  - Telegram **group** (discussion): https://t.me/fullremotechat — peers discuss companies, CVs,
    technical interviews, application processes, red flags in job ads
  - Telegram **channel** (job posts): https://t.me/fullremoteit
  - Group info and rules: https://www.fullremote.it/gruppo-telegram
  - Instagram: https://www.instagram.com/fullremote.it/ · Bluesky: https://bsky.app/profile/fullremote.it
- **Newsletter (verified on site, figures may change):** free weekly newsletter with curated offers,
  sent on Wednesdays at 9:00, over 11,800 subscribers at the time of the check. Subscribe from the homepage.
- **How to join:** subscribe to the newsletter, follow the channel for offers, join the group for discussion.
  Group rules: respect, stay on topic, no unauthorised promotion or job posts (companies go through the
  official channel), immediate bans for spam or discrimination.
- **Tags:** `role:dev` `role:product` `role:data` `role:design` `work:remote` `work:jobs` `work:career` `format:jobboard` `format:newsletter` `format:telegram` `lang:it` `level:any`

### Dataskew (dataskew.io)
- **What it is (verified):** learning platform and community for **aspiring data engineers**,
  self-described as "the home of the Italian data community". Roadmaps (e.g. Modern Data Stack,
  Startup Stack), hands-on projects, fundamentals (SQL, Python, Data Modeling, Data Quality & Testing,
  Data Warehousing, NoSQL, Docker), topics such as Kafka, Spark,
  dbt, Airflow and cloud platforms. Public project portfolios reviewed by working engineers, talent
  profiles, and a curated **jobs board** for data and AI roles in Italy and EU-remote, plus a jobs
  market report.
- **Who it's for:** people moving into or growing in data engineering, from beginner to advanced.
- **Links:**
  - Site: https://dataskew.io/ (verified) · Roadmaps: https://dataskew.io/roadmaps/ · Jobs market report: https://dataskew.io/jobs/market-report/
  - Telegram (linked from the site, verified): https://t.me/dataskew_it
  - Telegram invite in the awesome list ("Dataskew.io - Data Engineering Learning community"): https://t.me/+sJZ1e0UAw1U4NWRk (unverified; may be the same group via an older invite)
- **How to join:** free account at https://dataskew.io/sign-up/ . Free to use (terms). Created by Adriano Sanges (/about).
- **Tags:** `role:data` `role:ai` `stack:python` `work:learning` `work:jobs` `work:remote` `format:site` `format:jobboard` `format:telegram` `lang:it` `level:junior` `level:mid`

### Welyk job board
- **What it is (verified):** the list of positions that **Guido Penta** (tech recruiter, welyk.tech,
  formerly forloop.tech, per the repo description "welyk.tech (former forloop.tech)") is currently
  managing for client companies. Each role shows RAL range, contract / work mode and company. Also lists
  closed searches with their salary (data points from Welyk's searches, not a market survey; e.g. frontend
  35-50k, senior backend 50k, data 45-50k).
- **Who it's for:** developers and tech profiles in Italy, often full-remote roles.
- **Links (verified):**
  - Board: https://github.com/GuidoPenta/welyk-job-board · https://guidopenta.github.io/welyk-job-board/
  - Spontaneous application / register as a candidate: https://recruiting.welyk.tech/jobs/5813648-candidatura-spontanea
  - Individual roles live on https://recruiting.welyk.tech/jobs/...
- **How to use:** read the board, apply through the role's link, or register with the spontaneous
  application. The repo was last updated 2025-09-08, so **always re-fetch the README**: roles in the
  snapshot may be closed.
- **Tags:** `role:dev` `role:backend` `role:frontend` `role:leadership` `work:jobs` `work:salary` `work:remote` `format:jobboard` `lang:it` `level:any`

## Communities (from awesome-italian-tech-communities)

All entries below are Italian-language unless stated. Links are as listed upstream (unverified individually).

### Career, jobs, salary, general developer talk

| Community | Link | Tags |
|---|---|---|
| La Locanda del Tech | see Featured | `role:any` `work:career` `work:salary` `format:telegram` |
| Carriere e Burocrazia nell'IT | https://t.me/twccarriera | `role:any` `work:career` `work:salary` `format:telegram` |
| HR feat. ICT (by Lavoro Digitale Italia) | https://t.me/+IxwjMC4ytMU4YjRk | `role:hr` `role:any` `work:jobs` `work:career` `format:telegram` |
| Il salotto dei programmatori (by Lorenzo Casponi) | https://t.me/salottoprogrammatori | `role:dev` `work:networking` `format:telegram` |
| DevelopersLife | https://t.me/developerslifechannel · https://www.instagram.com/developerslifechannel/ | `role:dev` `work:networking` `format:telegram` `format:instagram` |
| i Programmatori | https://t.me/iprogrammatori | `role:dev` `work:networking` `format:telegram` |
| Programmazione Italia | https://t.me/programmazioneitalia | `role:dev` `format:telegram` |
| Programmatori Italiani | https://t.me/developers0101 | `role:dev` `format:telegram` |
| ItalianCoders | https://t.me/italiancoders_community · Discord: https://s.italiancoders.it/discord | `role:dev` `work:networking` `format:telegram` `format:discord` |
| Italian Coders Group (Discord) | https://top.gg/servers/500396398324350989/join | `role:dev` `format:discord` |
| DevHub Italia / Informatica (Discord) | https://discord.gg/e4KbstNqtk | `role:dev` `level:junior` `format:discord` |
| Fullstackish! (TomorrowDevs) | https://t.me/tomorrowdevs · YouTube: https://youtube.com/tomorrowdevs · Instagram: https://www.instagram.com/tomorrowdevs/ | `role:dev` `work:learning` `level:junior` `format:telegram` `format:youtube` |
| We are Dev (by Fabio Biondi) | https://t.me/we_are_devs | `role:frontend` `stack:js` `stack:react` `stack:angular` `format:telegram` |
| Arkemis Community | https://t.me/+RkKbRhGLAA9MHXzf · Discord: https://discord.gg/zAjmZYHXp7 | `role:dev` `format:telegram` `format:discord` |
| Superhero Valley | https://t.me/+zIcgNjPpYpIzNmU0 · Discord: https://discord.com/invite/uPRmhHwMem | `role:dev` `work:networking` `format:telegram` `format:discord` |
| DevDreams | Discord: https://discord.gg/QdXC7SuA65 · Twitch: https://www.twitch.tv/devup_program · YouTube: https://www.youtube.com/@dev.dreams | `role:dev` `work:learning` `format:discord` `format:twitch` |
| Gitbar Podcast community (by Mauro Murru) | https://t.me/gitbar | `role:dev` `work:networking` `format:telegram` |
| Ripsters (mr. RIP) | https://mr.rip/discord | `role:dev` `format:discord` |

### Leadership, CTO, engineering management

| Community | Link | Tags |
|---|---|---|
| CTO Mastermind | Telegram: https://t.me/ctomastermind/ · Slack: https://www.ctomastermind.it/community/ · Podcast: https://www.ctopodcast.it/ · TV: https://www.ctomastermind.tv/ · Instagram: https://www.instagram.com/ctomastermind/ | `role:leadership` `level:senior` `work:networking` `format:telegram` `format:slack` `format:podcast` |

### Data, AI

| Community | Link | Tags |
|---|---|---|
| Dataskew | see Featured | `role:data` |
| Data Engineering Italia | https://t.me/data_engineering_italia | `role:data` `format:telegram` |
| Algoritmi - Datapizza (podcast) | https://open.spotify.com/show/6TMBvIx2tWVA8AEPDU027j | `role:ai` `role:data` `format:podcast` |
| Piero Savastano (YouTube) | https://www.youtube.com/@PieroSavastano | `role:ai` `work:learning` `format:youtube` |

### DevOps, cloud, sysadmin, infrastructure

| Community | Link | Tags |
|---|---|---|
| DevOps Italia | https://t.me/devopsitalia | `role:devops` `format:telegram` |
| DevOps Italy | https://t.me/devopsitaly | `role:devops` `format:telegram` |
| Kubernetes-IT | https://t.me/kubernetes_it | `role:devops` `stack:kubernetes` `format:telegram` |
| Kubernetes Milano (meetup) | https://www.meetup.com/kubernetes-milano/ | `role:devops` `stack:kubernetes` `city:milano` `format:meetup` |
| CloudChampions | Telegram: https://t.me/cloudchampions/ · Podcast/TV: https://www.cloudchampions.tech/cloudtv/2691/Cloud-Champions · Video: https://www.cloudchampions.tech/video/ · YouTube: https://www.youtube.com/CloudChampions · Instagram: https://www.instagram.com/thecloudchamps/ | `role:cloud` `stack:azure` `format:telegram` `format:podcast` `format:youtube` |
| Cloud Ops Italia | https://cloudopsitalia.it | `role:cloud` `role:devops` `format:site` |
| Sistemistica Italia | https://t.me/sistemistica_italia | `role:sysadmin` `stack:linux` `format:telegram` |
| RabbitMQ Ita | https://t.me/RabbitMQ_ita | `role:backend` `stack:rabbitmq` `format:telegram` |
| Continuous Delivery (podcast) | https://www.spreaker.com/show/continuous-delivery | `role:devops` `format:podcast` |
| MorroLinux (YouTube) | https://www.youtube.com/@morrolinux | `role:sysadmin` `stack:linux` `format:youtube` |
| I use Yocto btw | Matrix: https://matrix.to/#/#iuseyoctobtw:matrix.org · Podcast: https://linktr.ee/iuseyoctobtw | `role:dev` `stack:yocto` `stack:linux` `format:matrix` `format:podcast` |

### Security

| Community | Link | Tags |
|---|---|---|
| SecurityCert | Discord: https://discord.gg/KWzx6FCucF · YouTube: https://www.youtube.com/@securitycert · Twitch: https://www.twitch.tv/securitycert · Podcast: https://open.spotify.com/show/5Je5mhSrFMLXupKbaGnCqG | `role:security` `work:learning` `format:discord` `format:youtube` `format:twitch` `format:podcast` |

### Language and stack communities

| Community | Link | Tags |
|---|---|---|
| Python Italia | https://t.me/pythonita | `stack:python` `format:telegram` |
| PyMI - Python Milano | https://www.meetup.com/it-IT/python-milano/ | `stack:python` `city:milano` `format:meetup` |
| Intervista Pythonista (podcast) | https://intervistapythonista.com/ | `stack:python` `format:podcast` |
| Go Italia #1 | https://t.me/golangita | `stack:go` `format:telegram` |
| Go Italia #2 | https://t.me/golang_italia | `stack:go` `format:telegram` |
| Gophers Italy (Slack) | https://gophers.slack.com | `stack:go` `format:slack` |
| Golang Milano | Telegram: https://t.me/+C1dv468eOAliODQ0 · Meetup: https://www.meetup.com/Golang-Milano/ | `stack:go` `city:milano` `format:telegram` `format:meetup` |
| Golang Roma | Telegram: https://t.me/golangroma · Meetup: https://www.meetup.com/it-IT/golangroma/ | `stack:go` `city:roma` `format:telegram` `format:meetup` |
| Golang Torino | Telegram: https://t.me/golangtorino · Meetup: https://www.meetup.com/golang-torino/ | `stack:go` `city:torino` `format:telegram` `format:meetup` |
| Rust Italia #1 | https://t.me/rustlang_it | `stack:rust` `format:telegram` |
| Rust Italia #2 | https://t.me/rust_italia | `stack:rust` `format:telegram` |
| Nim Italia | https://t.me/nimitalia | `stack:nim` `format:telegram` |
| Italia JS (Discord) | https://discord.gg/CrHrweEaUg | `role:frontend` `stack:js` `stack:ts` `format:discord` |
| Roma.js | https://romajs.org · Discord: https://discord.gg/qTD4jfh9Dw | `stack:js` `city:roma` `format:meetup` `format:discord` |
| Milano Frontend | https://www.meetup.com/it-IT/milano-front-end/ | `role:frontend` `city:milano` `format:meetup` |
| React JS Milano | https://www.meetup.com/it-IT/react-js-milano/ | `stack:react` `city:milano` `format:meetup` |
| The Concise TypeScript Book (Italian, free) | https://gibbok.github.io/typescript-book/it-it/ | `stack:ts` `work:learning` `format:site` |
| Flutter Italia Developers | https://t.me/flutteritdevs | `role:mobile` `stack:flutter` `format:telegram` |
| UGIdotNET | Telegram: https://t.me/ugidotnet · YouTube: https://www.youtube.com/ugidotnet · Instagram: https://www.instagram.com/ugidotnet/ | `stack:dotnet` `format:telegram` `format:youtube` |
| Blazor Developer Italiani | https://t.me/+peIr3tJOKNBmNTQ8 | `stack:dotnet` `stack:blazor` `format:telegram` |
| XeDotNet | https://www.xedotnet.org/ | `stack:dotnet` `city:veneto` `format:meetup` |
| .NET in pillole (podcast) | https://www.spreaker.com/show/net-in-pillole | `stack:dotnet` `format:podcast` |
| Andrea Dottor (YouTube) | https://www.youtube.com/@AndreaDottor | `stack:dotnet` `format:youtube` |
| GrUSP (PHP and web conferences org) | Slack: https://slack.grusp.org/ · YouTube: https://www.youtube.com/GrUSP · Instagram: https://www.instagram.com/GrUSP_/ | `stack:php` `stack:js` `work:events` `format:slack` `format:youtube` |

### City and regional meetups

| Community | Link | Tags |
|---|---|---|
| DevMarche | https://dev.marche.it/ · Telegram: https://t.me/+j-h3ljrMZV8zZmVk | `role:dev` `city:marche` `format:meetup` `format:telegram` |
| Marca User Group | https://marcausergroup.it/ | `role:dev` `city:treviso` `format:meetup` |
| Firenze.dev | https://firenze.dev/ · Discord: https://discord.com/invite/DJ5gpQtqMH | `role:dev` `city:firenze` `format:meetup` `format:discord` |
| Coding Bunker Milano | https://www.meetup.com/it-IT/coding-bunker/ | `role:dev` `city:milano` `format:meetup` |
| Open Source Saturday Milano | https://www.meetup.com/it-IT/open-source-saturday-milano/ | `work:opensource` `city:milano` `format:meetup` |
| (see also Golang Milano/Roma/Torino, PyMI, Roma.js, Milano Frontend, React JS Milano, Kubernetes Milano, XeDotNet above) | | |

### Open source

| Community | Link | Tags |
|---|---|---|
| Italia Open Source (directory of communities) | https://italiaopensource.com/ | `work:opensource` `work:networking` `format:site` |
| Schrödinger Hat | Telegram: https://t.me/hatters25 · Discord: https://discord.gg/RTXr8A3eFn · Site/podcast: https://www.schrodinger-hat.it/ · YouTube: https://www.youtube.com/c/Schr%C3%B6dingerHat | `work:opensource` `role:dev` `format:telegram` `format:discord` `format:podcast` |
| Open Source Support (by Patryk Rzucidło / PtkDev) | Telegram: https://t.me/ptkdev_support_italian · Discord: http://discord.ptkdev.io/ | `work:opensource` `format:telegram` `format:discord` |

### Podcasts (general tech and culture)

| Podcast | Link | Tags |
|---|---|---|
| Gitbar | https://www.gitbar.it/ | `role:dev` `format:podcast` |
| La Gilda dei DEVulgatori (playlist) | https://open.spotify.com/playlist/1sJvhXyU3Tux4F2cMIxb44 | `role:dev` `format:podcast` |
| Pensieri in codice | https://pensieriincodice.it/ | `role:dev` `format:podcast` |
| PointerPodcast | https://pointerpodcast.it/ | `role:dev` `format:podcast` |
| Storie di Developers | https://open.spotify.com/show/5rDJu3qScB9YR5yZtgjm62 | `role:dev` `work:career` `format:podcast` |
| Pillole di bit | https://www.pilloledib.it/ | `role:any` `format:podcast` |
| Il podcast di Marco's Box | https://podcasters.spotify.com/pod/show/marcosbox | `role:any` `format:podcast` |
| DataKnightmare: l'algoritmico è politico | https://dataknightmare.eu/ | `role:data` `role:ai` `format:podcast` |
| Ciao, Internet! (Matteo Flora) | https://open.spotify.com/show/5q7jh01YLFtru7iqUlj6lu | `role:any` `format:podcast` |
| (also: La Locanda del Tech, CTO Podcast, Cloud Champions, .NET in pillole, Continuous Delivery, SecurityCert, Algoritmi - Datapizza, Intervista Pythonista, I use Yocto btw, Schrödinger Hat — see sections above) | | |

### YouTube and Twitch creators (learning)

| Channel | Link | Tags |
|---|---|---|
| Fabio Biondi (frontend) | YouTube: https://www.youtube.com/c/FabioBiondi · Twitch: https://www.twitch.tv/fabio_biondi | `role:frontend` `stack:angular` `stack:react` `format:youtube` `format:twitch` |
| NonCompila | YouTube: https://www.youtube.com/@noncompila · Twitch: https://www.twitch.tv/noncompila | `role:dev` `format:youtube` `format:twitch` |
| Improving Code | https://www.youtube.com/@ImprovingCode | `role:dev` `format:youtube` |
| DevDay | YouTube: https://www.youtube.com/c/DevDay · Instagram: https://www.instagram.com/devday_it/ | `role:dev` `work:events` `format:youtube` |
| DevMy | https://www.youtube.com/@Devmy | `role:dev` `format:youtube` |
| EmmeCiLab (CS and maths) | https://www.youtube.com/@emmecilab | `work:learning` `format:youtube` |
| fcamuso | https://www.youtube.com/@fcamuso | `work:learning` `level:junior` `format:youtube` |
| sensorario | https://www.youtube.com/@sensorario | `role:dev` `format:youtube` |
| The Communities Bay | https://www.youtube.com/@thecmmbay | `work:networking` `format:youtube` |
| TheRedCode | https://theredcode.it/ · Instagram: https://www.instagram.com/theredcode_it/ | `role:dev` `format:site` |
| Giuseppe Funicello | https://www.youtube.com/@giuppidev | `role:dev` `format:youtube` |
| Christian Varisco | https://www.youtube.com/@christianvarisco | `role:dev` `format:youtube` |
| Edoardo Dusi | https://www.youtube.com/@edodusi | `role:dev` `format:youtube` |
| DevLeonardo | https://www.youtube.com/c/devleonardo | `role:dev` `format:youtube` |
| Andrea Pollini | https://www.youtube.com/@ProfAndreaPollini | `work:learning` `format:youtube` |
| La Brigata dei Geek Estinti | https://www.youtube.com/channel/UC5yquqmAAdbB9bPkUISRimA | `role:any` `format:youtube` |
| Tommaso Allevi | https://www.youtube.com/@tommasoallevi4223 | `role:dev` `format:youtube` |

### Event portals

| Portal | Link | Tags |
|---|---|---|
| Eventi Tech (all tech events in Italy) | https://eventitech.it/ | `work:events` `format:site` |
| dev.events (Europe and online) | https://dev.events/EU | `work:events` `format:site` `lang:en` |

---

## Remote job sources

| Source | What | Link | Tags |
|---|---|---|---|
| **Awesome Italia Remote** | 348 remote-friendly or full-remote companies that hire Italian talent (on 2026-09-25), based in Italy or abroad with operations in Italy. Maintained by Alessandro Marino and Edoardo Costantini | https://italiaremote.com/companies · https://github.com/italiaremote/awesome-italia-remote | `work:remote` `work:jobs` `lang:en` |
| **fullremote.it** | curated full-remote offers, newsletter, Telegram | see Featured | `work:remote` `work:jobs` `lang:it` |
| **Dataskew jobs** | data and AI roles, Italy + EU remote | see Featured | `role:data` `work:remote` |
| **Welyk job board** | roles managed by Guido Penta, with RAL | see Featured | `work:jobs` `work:salary` |

### How Awesome Italia Remote is structured (useful for filtering)

- Grouped by **remote policy**, then by **category**:
  - Remote policy: **Full** (no physical offices), **Hybrid** (remote only some days), **Optional** (you choose, may occasionally be asked on site).
  - Categories: *Software and Cloud*, *Marketing and Writing*, *HR*, *Design and UX*, *Cybersecurity*.
- Each row: Name, Career Page, **Company Type** (Product, Consulting, B2B), **Hiring Policy**, **Stack**.
- Hiring policy is decisive for Italian candidates:
  - **Direct** — "Company is hiring directly with a legal entity in Italy".
  - **Contract** — hires contractors; a **Partita IVA** (VAT number) is required.
  - **Intermediary** — hires through a payroll intermediary / EOR in Italy.
- Machine-readable source: one JSON per company in `data/` with fields
  `name`, `url`, `career_page_url`, `type`, `categories` (e.g. `cloud_software`), `remote_policy`,
  `hiring_policies[]`, `tags[]` (stack). The README is generated from it ("do not edit manually").
- **Filtering recipe:** match `tags[]` to the user's stack, `remote_policy` to their preference,
  and warn when the only option is `Contract` (they need a Partita IVA and should compare net pay,
  see galactic-negotiation).

---

## Conferences

Canonical list: https://techconfit.github.io (repo `techconfit/techconfit.github.io`, CC0; Guido's fork
points to https://techconf.it). The upstream repo was last updated in **February 2025**, so dates are
old: use it to discover **recurring series**, then check each series' own website for the next edition.
For current dates also use https://eventitech.it/ and https://dev.events/EU.

Recurring series (city of the latest edition in the list):

| Series | Latest listed | City | Website | Tags |
|---|---|---|---|---|
| Codemotion | Milan 2024 (also Rome, online, Workshop Fest) | Milano | listed: https://conferences.codemotion.com/milan2024/it/home/ | `role:dev` `work:jobs` `work:networking` `city:milano` |
| GDG DevFest (many cities) | 2024-2025 | Milano, Modena, Pisa, Bari, Catania, Napoli, Pescara, Trento, Venezia, Alps, Basilicata, Campobasso | e.g. https://devfestmilano.it/ · https://devfest.modena.it/ · https://devfest.gdgpisa.it | `role:dev` `stack:android` `stack:gcp` `work:networking` |
| PyCon Italia | 2025 | Bologna | https://pycon.it (2025: https://2025.pycon.it) | `stack:python` `city:bologna` |
| JsDay | 2025 | Bologna | https://jsday.it/ | `stack:js` `city:bologna` |
| phpday | 2025 | Verona | https://phpday.it/ | `stack:php` `city:veneto` |
| laravelday | 2024 | Verona | https://2024.laravelday.it/ | `stack:laravel` `city:veneto` |
| sfday (Symfony) | 2024 | Online | https://www.grusp.org/ | `stack:symfony` `city:online` |
| CssDay | 2025 | Faenza | https://www.cssday.it/ | `role:frontend` |
| uxday | 2024 | Faenza | https://2024.uxday.it/ | `role:design` |
| dxday (developer experience) | 2024 | Bologna | https://2024.dxday.it/ | `role:dev` `city:bologna` |
| containerday | 2024 | Bologna | https://2024.containerday.it/ | `role:devops` `city:bologna` |
| devsecopsday | 2024 | Bologna | listed URL: https://2023.devsecopsday.it/ (stale, check GrUSP) | `role:security` `role:devops` |
| Kubernetes Community Days Italy | 2024 | Bologna | https://community.cncf.io/ (KCD Italy) | `stack:kubernetes` |
| Pragma Conference (iOS/Swift) | 2024 | Bologna | https://www.pragmaconference.com/ | `stack:swift` `role:mobile` |
| Product Management Day | 2024 | Bologna | https://www.productmanagementday.com/ | `role:product` |
| Droidcon Italy | 2024 | Milano | https://it.droidcon.com/ | `stack:android` `stack:kotlin` `city:milano` |
| GoLab | 2024 | Firenze | https://golab.io/ | `stack:go` `city:firenze` |
| RustLab | 2024 | Firenze | https://rustlab.it/ | `stack:rust` `city:firenze` |
| Open Source Day | 2025 | Firenze | https://2025.osday.dev | `work:opensource` `city:firenze` |
| RomHack | 2025 | Roma | https://romhack.io/ | `role:security` `city:roma` |
| Also in the list (older editions) | angularday, reactjsday, vueday, reactnativeday, nodejsday, webday, rubyday, qtday, Swift Heroes, Flutter Heroes, Voxxed Days Milano, HackInBo, CyberTech Europe, Incontro DevOps Italia, WordCamp Italia, Linux Day, Delphi Day / ITDevCon, BlazorConf, Azure Day, CloudConf, Coderful, Come to Code, Merge-IT, accessibility days, agile days | various | see upstream `_conferences/` | |

**Job-search angle (general practice):** conferences are the best place for warm intros. Check the sponsor
list (sponsors are usually hiring), attend the community / job-board area, and prepare a 20-second intro.
Many GrUSP events (jsday, phpday, cssday, uxday, dxday, containerday, devsecopsday, laravelday, sfday) share
the same organiser: https://www.grusp.org/ .

---

## Mentorship

### Mentorship-like places
- **Welyk / Guido Penta** — spontaneous application (see Featured).
- **Full Remote Telegram group** — peer CV review and interview debriefs (see Featured).
- **Dataskew** — portfolio projects reviewed by working data engineers (see Featured).
- **CTO Mastermind** — for aspiring tech leads and CTOs (see Leadership).

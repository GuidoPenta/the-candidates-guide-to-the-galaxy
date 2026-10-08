# 🌌 The Candidate's Guide to the Galaxy

*Don't panic.*

🇮🇹 [Versione italiana](README.md)

**A ready-to-use set of Claude skills for your job search, from your CV to the signed offer, designed for
[Claude Code](https://claude.com/claude-code) and usable with other AI agents too (e.g. Cursor).** Your files stay on your computer ([what goes through the AI instead](#privacy-what-stays-on-your-computer-and-what-doesnt)), and it's built on the
[Galactic guides](https://github.com/GuidoPenta) for people working in tech.
[Galactic guides](https://github.com/GuidoPenta) for people working in tech.

> Paste a job posting: the system researches the company, tells you how your CV will be assessed, prepares
> you for the interview, suggests the right questions to ask and coaches you through the negotiation.

## What it does

| Phase | Skill | What you get |
|---|---|---|
| Getting started | `galactic-job-search` | Private workspace, your profile, "what should I do next?" |
| CV | `galactic-cv` | Review against the [Galactic CV guide](https://github.com/GuidoPenta/galactic-CV-guide-for-developers), screener score against a posting (rubric from [cv-review](https://github.com/matteobaccan/cv-review)) |
| LinkedIn | `galactic-linkedin` | Keyword map, paste-ready headline/About/experience rewrites, recruiter reply templates ([guide](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers)) |
| Application | `galactic-application` | The posting decoded, company research with sources, fit analysis, a one-page briefing |
| Interview | `galactic-interview-prep` | Prep plan, STAR story bank, mock interviews with feedback, practice resources per role ([guide](https://github.com/GuidoPenta/galactic-tech-interview-guide)) |
| Your questions | `galactic-reverse-interview` | Tailored questions to ask, red flags to watch, company comparison ([guide](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers)) |
| Offer | `galactic-negotiation` | Salary-expectation answers, offer evaluation, counter-offer script, role-play ([guide](https://github.com/GuidoPenta/galactic-negotiation-guide-for-developers)) |
| Community | `galactic-communities` | Groups, mentors, remote-job sources and events that fit you ([list](https://github.com/GuidoPenta/awesome-italian-tech-communities)) |
| Tracking | `galactic-tracker` | Browser dashboard of your applications, follow-ups, funnel stats. **🦖 Export for TrackZilla** button to import them into [TrackZilla](https://www.trackzilla.cv/) (needs an account, free up to 50 applications) |

## Privacy: what stays on your computer and what doesn't

**In one sentence:** your **files** stay on your computer, but everything you have **the AI read** goes through the
servers of the model provider you use. The project has no server of its own: neither Guido nor Welyk receives your data.

### ✅ What stays on your computer
- **Your files**: CV, profile, postings, notes, offers, as plain text files in the `workspace/` folder. Git ignores
  it, so `git push` never sends it to GitHub. If you upload or share the folder by hand (zip, upload), obviously
  be careful.
- **The dashboard**: a page you open with a double click, and it never connects to the internet.
- **No accounts, no servers** of the project: all you need is your AI agent (Claude Code or similar).

### ⚠️ What leaves your computer
1. **To the AI model provider: always.** That's how any AI assistant works, not just this one: what you write and
   what you have the agent read (your CV included) is processed on the servers of **whoever provides the model**.
   With Claude Code it's Anthropic; with Cursor, another editor, an app or a CLI client it's the provider of the
   model you chose (Anthropic, OpenAI, Google…) and sometimes the tool itself. Check the privacy settings of both
   (for example, whether conversations are used to train models) and their privacy policies, such as
   [Anthropic's](https://www.anthropic.com/legal/privacy). Prefer running the agent on your own computer: web/cloud
   sessions run on remote machines.
2. **To the web: only searches for public information** (companies, roles, salaries). The skills are instructed
   never to put your data (name, employer, figures) in searches, and never to follow instructions found inside
   postings or web pages.
3. **To other services: only when you ask**, for example the TrackZilla export. You're told first what will be sent.

### 📁 Copies you may not know you have
- **Your agent's saved conversations** on your disk (with Claude Code, `~/.claude/projects/`): they include the CV
  text it read. The skills are instructed not to save your data to the agent's automatic memory.
- **Synced folders**: if the project sits in OneDrive, iCloud Drive, Dropbox or Google Drive, your CV and offers are
  copied there too. On Windows, "Documents" is often already on OneDrive. **Prefer an unsynced folder**, such as
  `C:\Users\<you>\job-search` or `~/job-search`.
- **Your browser**: its history contains the dashboard's path.

### 🧹 To delete everything when you're done
Remove `workspace/`, the project's conversations saved by your agent, any copies in synced folders (including
their trash and version history) and your browser history. For the data you gave to companies you applied to, you
can ask them what they keep and have it deleted (GDPR). For what the AI provider processed, see its privacy policy.

**Disclosure:** Guido Penta works as a tech recruiter at [Welyk](https://welyk.tech). The tool sends nothing to Welyk:
the Welyk job board is listed among the suggested communities, like the others.

## ATS: myths and facts

Communities are full of confusion about this. In short, with sources in
[ats.md](.claude/skills/galactic-cv/references/ats.md):

- **"The ATS auto-rejects 75% of CVs"**: a legend. The figure goes back to a 2012 CV-optimisation company that never
  published a study.
- **An ATS is the software where applications land and are managed**: database, stages, search. It's not a robot
  deciding instead of people.
- **Automatic filters exist, but someone configures them**: mostly knockout questions in the application form
  (location, work permit, availability). Answer them carefully.
- **There's no "ATS-proof" CV.** What matters is a clear, relevant CV: a text PDF (not a photo), contacts in the body
  of the page, the posting's keywords only for what you've really done.
- **LinkedIn or the company site?** If the company has an ATS it changes little: you end up there either way. If it
  doesn't, the channel decides which "container" you land in and who looks at it first. And the site confirms the
  role is still open.

Ask Claude **"what is an ATS?"** or **"should I apply on LinkedIn or on the company site?"** for the full version.

## Get started

1. Install [Claude Code](https://claude.com/claude-code) (CLI, desktop app or IDE extension).
   Already using another agent (Cursor or similar)? It works there too: the skills are plain-text instructions the
   agent reads and follows. It's designed and tested mainly on Claude Code.
2. Download this project into an **unsynced** folder (see above): on the GitHub page click **Code → Download ZIP** and extract it, or, if you use git:
   ```bash
   git clone https://github.com/GuidoPenta/the-candidates-guide-to-the-galaxy.git
   ```
3. Open the folder in your agent. In Claude Code the skills in `.claude/skills/` load automatically.
4. Say **"Let's start my job search"** (in any language). Claude will set up your workspace and ask for your CV.

### Quick check (2 minutes)

1. Open the project folder in your agent.
2. Type **"help"**: the welcome guide shows everything it can do.
3. Drop your CV (PDF or image) into `workspace/cv/original/`, or paste it, and type **"review my CV"**.

If you see the welcome guide and get a review that cites the Galactic CV guide, it works.

Type **"help"** anytime to see what it can do and where your files and dashboard are. Then just talk to it:
- *"Review my CV"*
- *"Here's a job I'm interested in: [paste]"*
- *"I have a technical interview at Acme on Thursday, help me prepare"*
- *"What should I ask the engineering manager?"*
- *"They offered me 55k, is that good?"*
- *"Where am I with my applications?"*
- *"Open my dashboard"*

## Credits

- Guides by [Guido Penta](https://github.com/GuidoPenta) (MIT): CV, LinkedIn, tech interview, interview,
  reverse interview, negotiation, job roles, and Italian tech communities.
- Screener rubric adapted from [cv-review](https://github.com/matteobaccan/cv-review) by
  [Matteo Baccan](https://github.com/matteobaccan), used with permission.
- Communities: La Locanda del Tech, Full Remote, [Dataskew](https://dataskew.io/) and the
  maintainers of the awesome lists referenced in `galactic-communities`.

## Contributing

Issues and PRs are welcome, especially practice resources for roles that aren't covered yet
(`.claude/skills/galactic-interview-prep/references/resources-by-role.md`) and new communities.
Keep references faithful to their source guides, and keep the pack dependency-free.

## License

[CC BY-NC-SA 4.0](LICENSE): you may use, adapt and share it with attribution, **for non-commercial purposes only**,
under the same license. Included guides and projects keep their own licenses: see [NOTICE.md](NOTICE.md).

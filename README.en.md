# 🌌 Galactic Job Search

🇮🇹 [Versione italiana](README.md)

**An all-in-one job search coach for [Claude Code](https://claude.com/claude-code), from your CV to the signed offer.**
It runs locally, your data stays on your machine, and it's built on the
[Galactic guides](https://github.com/GuidoPenta) for developers.

> Paste a job posting, and it researches the company, tells you how a recruiter will score your CV, prepares
> you for the interview, gives you smart questions to ask, and coaches you through the negotiation.

## What it does

| Phase | Skill | What you get |
|---|---|---|
| Start | `galactic-job-search` | Private workspace, your profile, "what should I do next?" |
| CV | `galactic-cv` | Review against the [Galactic CV guide](https://github.com/GuidoPenta/galactic-CV-guide-for-developers), screener score against a posting (rubric from [cv-review](https://github.com/matteobaccan/cv-review)), honest rewrites |
| LinkedIn | `galactic-linkedin` | Keyword map, paste-ready headline/About/experience rewrites, recruiter reply templates ([guide](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers)) |
| Application | `galactic-application` | The posting decoded, company research with sources, fit analysis, a one-page briefing |
| Interview | `galactic-interview-prep` | Prep plan, STAR story bank, mock interviews with feedback, practice resources per role ([guide](https://github.com/GuidoPenta/galactic-tech-interview-guide)) |
| Your questions | `galactic-reverse-interview` | Tailored questions to ask, red flags to watch, company comparison ([guide](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers)) |
| Offer | `galactic-negotiation` | Salary-expectation answers, offer evaluation, counter-offer script, role-play ([guide](https://github.com/GuidoPenta/galactic-negotiation-guide-for-developers)) |
| Community | `galactic-communities` | Groups, mentors, remote-job sources and events that fit you ([list](https://github.com/GuidoPenta/awesome-italian-tech-communities)) |
| Tracking | `galactic-tracker` | Local pipeline, follow-ups, funnel stats, export to CSV or [TrackZilla](https://www.trackzilla.cv/) |

## Privacy first

- Everything you share (CV, postings, notes, offers) is stored as plain Markdown in `workspace/`. Git ignores it,
  so `git push` never sends it to GitHub. If you upload or share the folder by hand (zip, upload), it travels too.
- No accounts, no servers, no scripts, no dependencies. The dashboard is a page you open with a double click, and
  it never connects to the internet.
- The web is used only to research **public** information about companies, roles and salaries. The skills are
  instructed never to put your data (name, employer, figures) in searches, and never to follow instructions found
  inside postings or web pages.

### Where your data actually ends up

1. **`workspace/`**, in the project folder.
2. **Anthropic**: Claude is a cloud model, so what you write or have it read is processed on Anthropic's servers.
   On Free/Pro/Max plans, check the option in Settings → Privacy about using conversations to train models, and read
   the [privacy policy](https://www.anthropic.com/legal/privacy) for retention. Use Claude Code on your own computer:
   web/cloud sessions run on remote machines.
3. **Claude Code's saved conversations** on your disk (`~/.claude/projects/`). They include the CV text Claude
   read. The skills are instructed not to save your data to Claude's automatic memory.
4. **Synced folders**: if the project sits in OneDrive, iCloud Drive, Dropbox or Google Drive, your CV and offers are
   copied there too. On Windows, "Documents" is often already on OneDrive. **Prefer an unsynced folder**, such as
   `C:\Users\<you>\job-search` or `~/job-search`.
5. **Your browser**: its history contains the dashboard's path.
6. **External services only when you ask**, for example the TrackZilla export. Claude tells you first what it will send.

To delete everything when you're done: remove `workspace/`, the project's conversations in `~/.claude/projects/`,
any copies in synced folders (including their trash and version history) and your browser history. For the data
you gave to companies you applied to, you can ask them what they keep and have it deleted (GDPR).

**Disclosure:** Guido Penta works as a tech recruiter at [Welyk](https://welyk.tech). The Welyk job board is suggested
only when it fits, and applying there means sharing your CV with Welyk.

## Get started

1. Install [Claude Code](https://claude.com/claude-code) (CLI, desktop app or IDE extension).
2. Download this project into an **unsynced** folder (see above): on the GitHub page click **Code → Download ZIP** and extract it, or, if you use git:
   ```bash
   git clone https://github.com/GuidoPenta/Guida-galattica-job-search.git
   ```
3. Open the folder in Claude Code. The skills in `.claude/skills/` load automatically.
4. Say **"Let's start my job search"** (in any language). Claude will set up your workspace and ask for your CV.

Then just talk to it:
- *"Review my CV"*
- *"Here's a job I'm interested in: [paste]"*
- *"I have a technical interview at Acme on Thursday, help me prepare"*
- *"What should I ask the engineering manager?"*
- *"They offered me 55k, is that good?"*
- *"Where am I with my applications?"*

## Credits

- Guides by [Guido Penta](https://github.com/GuidoPenta) (MIT): CV, LinkedIn, tech interview, interview,
  reverse interview, negotiation, job roles, and Italian tech communities.
- Screener rubric adapted from [cv-review](https://github.com/matteobaccan/cv-review) by
  [Matteo Baccan](https://github.com/matteobaccan), used with permission.
- Communities: La Locanda del Tech, Full Remote, [Dataskew](https://dataskew.io/), coffeechat and the
  maintainers of the awesome lists referenced in `galactic-communities`.

## Contributing

Issues and PRs are welcome, especially practice resources for roles that aren't covered yet
(`.claude/skills/galactic-interview-prep/references/resources-by-role.md`) and new communities.
Keep references faithful to their source guides, and keep the pack dependency-free.

## License

[MIT](LICENSE)

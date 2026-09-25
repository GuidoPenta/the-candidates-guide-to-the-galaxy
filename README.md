# 🌌 Galactic Job Search

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

- Everything you share (CV, postings, notes, offers) is stored as plain Markdown in `workspace/`, which is **git-ignored**.
- No accounts, no servers, no scripts, no dependencies.
- The web is used only to research **public** information about companies, roles and salaries. The skills are
  instructed never to put your personal data in searches.
- Heads-up: Claude itself is a cloud model, so what you share in the conversation is processed by Anthropic under
  your plan's terms. "Local" here means your files and history stay on your disk and are not uploaded to any
  other service.

## Get started

1. Install [Claude Code](https://claude.com/claude-code) (CLI, desktop app or IDE extension).
2. Clone this repo and open the folder in Claude Code:
   ```bash
   git clone https://github.com/GuidoPenta/galactic-job-search.git
   ```
   The skills in `.claude/skills/` load automatically.
3. Say **"Let's start my job search"** (in any language). Claude will set up your workspace and ask for your CV.

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

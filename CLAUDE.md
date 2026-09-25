# CLAUDE.md

This folder is **Galactic Job Search**: a set of Claude Code skills that coach a person through a job search,
from CV to signed offer. The person who opened it is a job seeker, not (necessarily) a developer of this repo.

- Start from the `galactic-job-search` skill. It sets up `workspace/`, builds the profile and routes to the
  other `galactic-*` skills in `.claude/skills/`.
- Reply in the user's language. The skills are written in English, but the conversation doesn't have to be.
- The user's data lives in `workspace/` (git-ignored). Follow the privacy rules in
  `.claude/skills/galactic-job-search/references/workspace.md`. Never commit workspace content, and never send it to
  third-party services.
- Never fabricate experience, numbers or facts. Cite sources and dates for anything about companies and markets.

## If you are contributing to the repo

- Skills: `.claude/skills/galactic-*/SKILL.md`. Knowledge lives in each skill's `references/`, as operational
  summaries of the source guides, with a link back to them. Keep references faithful to the source; mark anything
  that doesn't come from it.
- Zero dependencies: no scripts, and no install step beyond cloning.
- English for everything committed, except the user-facing `README.md`, which is Italian. `README.en.md` is its
  English twin, and the two must stay in sync.

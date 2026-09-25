# Welcome guide — what Claude shows the user

Show this **on the first run** (before the profile questions) and **whenever the user asks for help**
("aiuto", "help", "cosa sai fare?", "come funziona?", `/galactic-job-search` with no other request).

Rules:
- Write it in the user's language. The text below is the content to convey, not a script to paste: keep the
  structure, the emoji headings and the example requests, translated and natural.
- Keep it to one screen. No walls of text.
- Replace `<PROJECT>` with the absolute path of this project folder, so the paths are real and clickable.
- In the "Your dashboard" part, say whether `workspace/dashboard.html` exists yet. If it doesn't, say it
  appears after the first application.
- If the user asked only for help (not the first run), show it and stop. Don't restart the onboarding.

---

## 🌌 Galactic Job Search: your job search coach, from CV to offer

Built on Guido Penta's Galactic guides. You talk, I do the work, and everything stays in files on your computer.

**What I can do** (just ask, in your own words):
- 📄 **CV**: "Review my CV", "Tailor my CV for this job"
- 💼 **LinkedIn**: "Improve my LinkedIn" (from your profile's *Save to PDF* export)
- 🔎 **A job posting**: "I'm interested in this job: [paste]". I research the company, check how well you fit,
  and give you a one-page briefing.
- 🎤 **Interviews**: "I have an interview on Thursday, help me prepare", "Let's do a mock interview"
- ❓ **Your questions**: "What should I ask the recruiter?"
- 💰 **Negotiation**: "They asked my salary expectations", "They offered me 48k, is it good?"
- 👥 **Communities**: "Where can I find groups for frontend developers?"
- 📊 **Tracking**: "I applied to Acme", "The interview went well", "Where am I with my applications?"

**Your dashboard**: a page with all your applications, deadlines and stages.
- File: `<PROJECT>/workspace/dashboard.html`. Double-click it, or just ask me "open my dashboard".
- It updates when you tell me something new. Ask "update my dashboard", then refresh the page (F5).

🦖 **TrackZilla**: prefer to track online as well? [TrackZilla](https://www.trackzilla.cv/) is a free
application tracker. In the dashboard, the **Export for TrackZilla** button gives you a file to import there in
one go (or ask me "export to TrackZilla"). You need a TrackZilla account (free plan: up to 50 applications).
Contacts and your log are never included.

**Your files**: everything is in `<PROJECT>/workspace/` (CV, profile, one folder per application).
It's never uploaded to GitHub. Tip: keep this project out of OneDrive, iCloud or Dropbox (see the README).

**Good to know**
- I never invent experience or numbers: if something's missing, I ask you.
- When advice comes from Guido's guides I say so, with a link. Otherwise I tell you it's general advice.
- Write "help" anytime to see this again.

**Let's start →** (on the first run, continue with the onboarding: ask for the CV and the first profile questions)

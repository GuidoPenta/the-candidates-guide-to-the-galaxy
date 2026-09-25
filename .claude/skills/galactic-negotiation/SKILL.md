---
name: galactic-negotiation
description: Prepares the user to negotiate, following Guido Penta's Galactic negotiation guide. Handles the "what are your salary expectations?" question early on, evaluates an offer's total compensation, builds the market data and alternatives (BATNA), writes the counter-offer script, rehearses with a role-play recruiter, and compares multiple offers. Use when the user says "they asked my salary expectations", "I got an offer", "is this offer good?", "how do I negotiate", "should I accept", "counter-offer", "RAL", "two offers".
---

# Galactic Negotiation

Knowledge: `references/negotiation-guide.md`, from
[galactic-negotiation-guide-for-developers](https://github.com/GuidoPenta/galactic-negotiation-guide-for-developers).
Workspace layout: `.claude/skills/galactic-job-search/references/workspace.md`.

You are not a lawyer, tax advisor or licensed financial advisor. For contract clauses, tax differences
(e.g. employee vs contractor/P.IVA) or equity taxation, give the guide's general framing and recommend a
professional (labour consultant, accountant) for the specifics.

## Early stage: money comes up at first contact
The guide is explicit on two points. The user talks money at the first contact and gives a range
themselves, which anchors the negotiation and filters out processes that won't pay. They **never share
their current salary** or a payslip: it's legitimate to decline. Prepare the range and the paste-ready phrasing
before the screening call, from `profile.md` targets and market data (below), and write it into the
application's `prep.md`. `compensation.current` in the profile is for the user's own reasoning. Never put it
in a message to a company.

## Offer stage → `workspace/applications/<app>/offer.md`
1. **Capture the offer** exactly: base (RAL/gross annual), variable, bonus, equity, benefits, remote/hybrid,
   hours, on-call, contract type, notice, probation, start date, and anything verbal still missing in writing.
2. **Market data**: search public salary sources on the web for role × seniority × location or remote. Cite
   each source with its date and sample caveats. Don't present one number as "the market": give a range.
3. **Alternatives (BATNA)**: read the other active processes from the tracker and the user's current
   situation. Leverage comes from real alternatives only; never suggest bluffing about offers that don't exist.
   (The guide doesn't cover BATNA or multiple offers. Present this as general practice.)
4. **Total comparison** against `profile.md` target and walk-away, and must-haves (use
   `galactic-reverse-interview` answers).
5. **Plan**: what to ask for, in what order, the anchor, the fallback trades (e.g. extra budget, remote days,
   start date), and when to stop. Follow the guide.
6. **Script**: paste-ready phrasing for the call or email, in the language of the negotiation.
7. **Role-play**: offer to play the recruiter or hiring manager, including pushback ("that's our max", "we need an answer
   by Friday"). Give feedback after.

## Multiple offers
Build a side-by-side table from each `offer.md`: total comp, must-haves, growth, risk, gut feeling (ask the
user). Help them decide; don't decide for them.

## After
Log the outcome with `galactic-tracker`: `accepted`, or `withdrawn` for the declined ones. Get everything in
writing before resigning from the current job, if the guide says so.

---
title: "Running a Pre-Mortem"
difficulty: easy
time: "25 minutes"
tags: ["planning", "risk", "visualization"]
prerequisites:
  - "Claude Code is already open"
  - "A real upcoming initiative you are about to commit to (a launch, a hire, a quarterly plan, a vendor selection, a program kickoff)"
  - "10 minutes of honest thinking. The pre-mortem only works if you are willing to imagine it failing."
  - "A web browser for the visual artifact"
learn:
  - "How to run a structured pre-mortem on any initiative in 25 minutes"
  - "How to use Claude as a devil's advocate that is not politically incentivized to be nice"
  - "How to build an interactive HTML risk radar that visualizes failure modes, likelihoods, and mitigations"
  - "How to define early warning signals you will actually notice in time"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 11
---

## What You Are Building

A completed pre-mortem for a real initiative plus an interactive HTML risk radar. Each failure mode shows up as a dot on the radar sized by likelihood and colored by severity. Click a dot and you see the root causes, the mitigation, and the early warning signal for that failure mode.

You are not learning to code. Claude plays devil's advocate, you answer honestly, and the radar is the artifact that makes risk legible.

By the end you will have:

- A pre-mortem document for a real initiative with top 3 failure modes, root causes, mitigations, and early warning signals
- An interactive HTML risk radar file you can share with your team
- Calendar reminders at 30 and 90 days to revisit the pre-mortem

> **At work, this comes up when you're...**
>
> - about to kick off a launch and everyone is already in "we got this" mode
> - about to extend an offer to a candidate you like, and nobody on the panel wants to be the skeptic
> - committing to a quarterly plan that looks a little too clean
> - signing a vendor contract because the pilot went well and momentum is carrying the decision
> - spinning up a new program and realizing nobody has asked "what would make this fail?"

## Why This Matters

Pre-mortems are one of the highest-leverage planning moves available. They reliably surface risks that post-mortems only find after the damage is done. Most teams skip them because they feel negative, they take real time, and the most senior person in the room is often the least incentivized to hear "this could fail."

Claude solves both. It is fast, so the time cost collapses. And it is not politically incentivized to be nice. It will happily tell you your plan has three obvious holes while your team is still nodding along in the meeting. That is not cruelty. That is what a good devil's advocate looks like.

The risk radar is the artifact that makes the output legible. When you can point at a red dot and say "this is the failure mode we are watching," your team takes it seriously in a way a bullet list never achieves.

---

## Name the initiative in one sentence

> **Hint:** _If you cannot describe it in one sentence, the pre-mortem will be fuzzy. Sharpen the target first._

Write one sentence with the initiative, the timeframe, and what success looks like.

- "We are launching the new customer portal by end of Q3, success means 40% of active customers signed in at least once by Q4."
- "We are hiring a head of operations in 6 weeks, success means they ship a new onboarding process in their first 90 days."

If you only have "we are launching a thing," pause and sharpen before proceeding.

> **You're there when:** you have one sentence naming the initiative, the timeframe, and what success looks like.

---

## Ask Claude to imagine the failure

> **Hint:** _You want Claude in devil's advocate mode, not cheerleader mode. Say so explicitly._

Paste this prompt. Swap the brackets.

```
I want to run a pre-mortem on an upcoming initiative: [paste your one sentence].

Your job is to be a sharp devil's advocate. Do not be nice. Do not soften answers. Assume it is 6 months from now and this initiative has failed spectacularly. The failure is obvious, public, and everyone is asking how we missed it.

Work through this in four steps, one at a time. Wait for me to respond before moving to the next.

Step 1: Ask 4-6 sharp questions about the plan, assumptions, team, timeline, and dependencies. Questions a skeptical board member would ask.

Step 2: Based on my answers, name the top 3 most likely failure modes. For each, write 2-3 sentences describing the failure in concrete terms ("by month 4, only 8% of customers had signed in and the team is blaming the email campaign").

Step 3: For each failure mode, identify the 2-3 root causes. The actual thing underneath, not the surface symptom.

Step 4: For each root cause, give me one concrete mitigation I could put in place now, and one early warning signal I could watch for.

Also rate each failure mode's likelihood (low, medium, high) and severity (low, medium, high) so I can compare them.
```

Claude will start asking questions. Answer honestly, not aspirationally.

> **You're there when:** you have 3 specific failure modes, each with root causes, mitigations, and signals.

---

## Push back on anything generic

> **Hint:** _"Execution risk" is not a failure mode. A specific scenario with people, dates, and a concrete outcome is._

Read the failure modes. Each should feel specific to your initiative, not a generic category.

If any feel vague, push back:

```
"Team alignment" is too generic. Name the specific alignment problem you see based on what I told you. Who disagrees with whom about what?
```

```
You softened the second failure mode. Say it more sharply. What does the worst version look like?
```

For mitigations:

```
"Improve communication" is not a mitigation. Give me one specific action: a meeting cadence, a shared doc, a named owner, or a decision rule.
```

Keep pushing until each failure mode reads like a short story you could almost believe happened, and each mitigation is something you could start on today.

> **You're there when:** every failure mode is a specific, believable scenario and every mitigation is concrete and startable this week.

---

## Generate the interactive HTML risk radar

> **Hint:** _The radar makes risk legible. A chart of dots is more memorable than a bullet list of fears._

Paste this:

```
Now build me a single self-contained HTML file called risk-radar.html that visualizes this pre-mortem as an interactive risk radar. Requirements:

- A 2D chart with Likelihood on the x-axis (low to high) and Severity on the y-axis (low to high), divided into four quadrants
- Each failure mode appears as a dot, sized by likelihood, colored by severity (red = high, amber = medium, yellow = low)
- Dots in the high-likelihood / high-severity quadrant are visually loudest (the ones to watch)
- Hovering a dot shows a tooltip with the failure mode name and a one-line description
- Clicking a dot opens a detail panel with: full failure scenario, root causes, mitigation, early warning signal, owner
- Below the radar: a table with all failure modes, mitigations, signals, and owner columns. Sortable.
- Header: initiative name, date, and the one-sentence success criteria
- Footer: "Revisit dates" with two calendar links (30 days from today, 90 days from today) that generate .ics files on click

Use only inline CSS and vanilla JavaScript. Soft modern styling.
```

Open `risk-radar.html` in your browser. Click the dots. Hover. Explore.

> **You're there when:** the radar renders, you can click a dot and see its details, and the revisit calendar links work.

---

## Set the revisits

> **Hint:** _A pre-mortem you do not revisit is planning theater. The 30 and 90 day checks are where the value compounds._

Click the "Revisit in 30 days" link in the HTML footer. It should download an .ics calendar file. Add it to your calendar. Do the same for the 90-day revisit.

When each reminder fires, open `risk-radar.html` again. For each failure mode, ask:

- Is the mitigation in place?
- Has the early warning signal shown up?
- Do we need to move this dot on the radar (lower or higher likelihood based on new evidence)?

The revisit is where the pre-mortem becomes a steering tool, not a document.

> **You're done when:** both calendar reminders are set and the risk radar is saved somewhere you can revisit.

---

## What You Just Did

You just did the single highest-leverage planning move most teams skip:

1. **Framed** an initiative specifically enough to fail at.
2. **Delegated** the devil's advocate role to Claude so the critique did not depend on political courage.
3. **Iterated** until every failure mode was specific and every mitigation was concrete.
4. **Visualized** the risk landscape so your team can see it at a glance, not decode a bullet list.
5. **Scheduled** the revisits so the pre-mortem actually earns its keep.

Do this before every non-trivial commitment. Every launch. Every hire. Every quarterly plan. Most disasters you have seen at work were predictable. The radar is how you see them coming.

## What Not to Do

1. **Do not run a pre-mortem on a fuzzy target.** Sharpen the one-sentence goal first.
2. **Do not let Claude be polite.** If the failure modes feel gentle, push back until they sting.
3. **Do not accept generic failure modes.** Specific scenarios only.
4. **Do not accept costless mitigations.** If it does not require a real action or conversation, it is not mitigating anything.
5. **Do not file the radar and forget it.** The 30 and 90 day revisits are the whole game.

## Next Steps

When you have run a pre-mortem on a real initiative and put the mitigations in place:

- **Decision Journal** (easy) — Pair pre-mortems with decision journals so you can calibrate whether your predictions held up.
- **Planning with Claude** (easy) — Use the pre-mortem to update an existing plan's kanban with new mitigations.
- **Build Your First Skill** (easy) — Package this whole sequence into a `/pre-mortem` skill so you can run it in 10 minutes next time.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work

---
title: "Planning with Claude"
difficulty: easy
time: "25 minutes"
tags: ["planning", "decomposition", "kanban"]
prerequisites:
  - "Claude Code is already open"
  - "A real initiative you need to plan (a project, a launch, a hire, a program, a rollout)"
  - "A web browser for the visual kanban artifact"
learn:
  - "How to turn a vague goal into an actual plan you can share with your team"
  - "How to decompose, sequence, stress-test, and assign owners"
  - "How to generate an interactive HTML kanban board from the plan"
  - "How to push back on a plan and tighten it until you would ship it today"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 8
---

## What You Are Building

A plan for something you actually need to do, plus an interactive HTML kanban board that visualizes the plan with columns (Decompose, Sequence, Assign, Execute) and cards for every step. You open the kanban in your browser. You can click cards to expand them, filter by owner, and track which steps are ready to start.

You are not learning to code. You describe the initiative, Claude walks you through decomposition, sequencing, stress-testing, and assignment, and Claude generates an HTML kanban you can share with your team.

By the end you will have:

- A real plan with discrete steps, dependencies, risks surfaced, and owners named
- An interactive HTML kanban board file on your computer
- A reusable skill that turns any vague goal into a sharable plan in 15 minutes

> **At work, this comes up when you're...**
>
> - staring at a blank doc on Monday morning with a goal but no plan
> - about to kick off a program, a launch, a hiring process, or a conference
> - halfway through something messy and realizing you never actually planned it
> - writing a quarterly plan and wanting to make sure you are not missing the obvious
> - handing a project to someone and realizing you cannot explain the sequence yourself

## Why This Matters

Most plans fail because they were never really plans. They were wishlists: a goal, a few tasks, a vibe. Real plans have four moves: Decompose. Sequence. Stress-test. Assign. Every good plan follows this shape, even if nobody names it.

Claude is a good planning partner because it does not get tired of asking you questions. Where a teammate might say "sure, looks fine" to be polite, Claude keeps asking what could go wrong until you have a real answer.

The kanban board is the artifact that makes the plan shareable. When you hand someone a Google Doc, it reads like a wall of text. When you hand them a kanban where each card names an owner, a status, and a dependency, they can start working immediately.

---

## Name the goal in one sentence

> **Hint:** _The goal is not the plan. The goal is what the plan is trying to achieve. Keep it short._

Write your goal in one sentence. Examples:

- "Launch the new mentorship program to 30 participants by end of Q3."
- "Hire a senior operations lead in 60 days."
- "Run a cross-team conference for 200 people this fall."

If your goal does not fit in one sentence, it is probably actually two goals. Pick the most important one.

> **You're there when:** you have a one-sentence goal.

---

## Ask Claude to decompose it

> **Hint:** _Decomposition is not a to-do list. It is the real chunks of work that need to happen. Claude will ask clarifying questions first. That is good._

Paste this prompt:

```
Help me decompose this goal into discrete steps.

Goal: [paste your goal]

Ask me clarifying questions first if anything is unclear. Then give me 5 to 10 real chunks of work, each in plain language. Do not give me a to-do list. Give me the real shape of the work.
```

Claude will ask 2-3 questions. Answer them. You will get a decomposition back.

Read it. Push back on anything missing or mis-shaped:

```
Your decomposition is missing the legal review step. Also, the "stakeholder alignment" step is really three smaller steps. Rework.
```

> **You're there when:** you have 5-10 chunks of work that together add up to the goal.

---

## Sequence and stress-test

> **Hint:** _Sequencing is not alphabetizing. It is figuring out which pieces depend on which others. Stress-testing surfaces what you are assuming but have not verified._

Paste this:

```
Now sequence these steps. Which depend on others? Which can happen in parallel? Mark each step with its dependencies.

Then stress-test the plan: what could go wrong? What am I missing? What assumptions might not hold? What is the single most likely failure mode?
```

Claude will produce a sequenced list with parallel flags, and a short list of risks. Read it.

If a risk is real, update the plan:

```
You are right that I am assuming director buy-in. Add an explicit first step: get director alignment before anything else.
```

Two or three rounds of stress-testing is usually enough. When Claude starts repeating itself, you are done.

> **You're there when:** the sequence reflects real dependencies and at least one surfaced risk has been folded into the plan.

---

## Assign owners

> **Hint:** _Every step needs one owner. "The team" is not an owner. "Me" is an owner. "Sarah" is an owner._

Paste:

```
For each step, propose an owner. Assume I have a team of [describe your team] and I can pull in [other groups if needed].

One owner per step. No shared ownership. If two people share ownership, nobody owns it.
```

Claude will propose names or roles. Adjust based on your real team.

> **You're there when:** every step has exactly one owner named.

---

## Generate the interactive HTML kanban

> **Hint:** _This is where the plan becomes shareable. A kanban in your browser is worth ten paragraphs of plan in a Google Doc._

Paste this:

```
Now build me a single self-contained HTML file called kanban.html that visualizes the plan as an interactive kanban board. Requirements:

- Four columns: Decompose (all steps), Sequence (ordered), Assign (with owners), Execute (ready to start)
- Each step is a card with: title, one-sentence description, owner, dependencies, estimated time if known
- Cards should be visually distinct based on status (not started, ready, in progress, blocked) with soft colors
- Include a filter bar at the top: filter by owner, filter by status
- Clicking a card expands it to show full details
- Include a "Risks and assumptions" sidebar with anything we surfaced in the stress test
- Clean modern styling: good typography, generous whitespace, soft palette

Use only inline CSS and vanilla JavaScript so the file is standalone.
```

Claude will write the file. Open `kanban.html` in your browser.

You should see a real kanban board. Cards. Columns. Filters. Click the filter to show only your own steps. Click a card to expand it.

> **You're there when:** the kanban renders in your browser, filters work, and cards expand on click.

---

## The share test

> **Hint:** _A plan is done when you would confidently share it with your team today. Not "someday." Today._

Read the kanban as if you were about to send it to your team. Ask:

- Does every card make sense to someone who was not in this conversation?
- Is the sequence clear from the columns and dependencies?
- Would my team know what to do on Monday morning?
- Is every step ownable by the person named?

If yes to all four, you are done. Save the kanban somewhere durable and share the link.

If no, push back on the weakest card:

```
The "stakeholder alignment" card is too vague. Rewrite it with three concrete touchpoints: which stakeholders, in what order, by when.
```

> **You're done when:** you would send this kanban to your team right now without any additional polish.

---

## What You Just Did

You just did the four moves that separate a plan from a wishlist:

1. **Decomposed** a goal into real chunks of work.
2. **Sequenced** them with real dependencies.
3. **Stress-tested** until at least one risk was named and mitigated.
4. **Assigned** one owner per step.

Plus you produced a visual kanban your team can actually use, not a text plan they will skim once.

## What Not to Do

1. **Do not skip the stress-test.** It feels optional and is the most valuable step.
2. **Do not accept "the team" as an owner.** Every step needs one name.
3. **Do not ship the first draft.** Plans get better in rounds.
4. **Do not plan alone when you could plan with stakeholders.** Claude is a great first-pass partner but a real stakeholder review is the final filter.
5. **Do not treat the kanban as fixed.** The plan is a starting state. It will change as work unfolds.

## Next Steps

Once you have run this pattern on two or three real initiatives:

- **Running a Pre-Mortem** (easy) — Pair planning with risk surfacing on your highest-stakes commitments.
- **Build Your First Skill** (easy) — Turn your favorite planning prompt into a reusable `/plan` skill.
- **Build a Custom Agent** (medium) — Package planning + stress-testing + owner assignment into a "project planner" specialist.

## Reference

- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn this workflow into a reusable skill

---
title: "Planning with Claude"
difficulty: easy
time: "20 minutes"
tags: ["planning", "foundational", "decomposition"]
prerequisites:
  - "Claude Code is already open"
  - "A real initiative you need to plan (a project, a launch, a hire, a program, a rollout)"
  - "No coding experience needed. You will describe, Claude will structure."
learn:
  - "How to turn a vague goal into a plan you can share with your team"
  - "How to decompose, sequence, stress-test, and assign owners"
  - "How to push back on a plan and make it tighter every round"
  - "When a plan is actually done (hint: not when it feels good)"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/overview"
order: 5
---

## What You Are Building

A plan for something you are actually trying to do, not a made-up example. By the end of this lab you will have an actionable plan with steps, dependencies, risks, and owners, built with Claude in about 20 minutes.

The pattern is four moves: Decompose. Sequence. Stress-test. Assign. Every good plan you have ever seen follows this shape, even if nobody called it out. Claude can walk you through it in one session.

> **At work, this comes up when you're...**
>
> - staring at a blank doc on Monday morning with a goal but no plan
> - about to kick off a program, a launch, a hiring process, or a conference
> - halfway through something messy and realizing you never actually planned it
> - writing a quarterly plan and want to make sure you are not missing the obvious
> - handing a project to someone and realizing you cannot explain the sequence yourself

## Why This Matters

Most plans fail because they were never really plans. They were wishlists: a goal, a few tasks, a vibe. Decomposition + sequence + stress-test + assignment is what turns a wishlist into something you can execute.

Claude is a good planning partner because it does not get tired of asking you questions. Where a teammate might say "sure, looks fine" to be polite, Claude will keep asking what could go wrong until you have a real answer.

---

## Name the goal in one sentence

> **Hint:** _The goal is not the plan. The goal is the thing the plan is trying to achieve. Keep it short._

Write your goal in one sentence. Examples:

- "Launch the new mentorship program to 30 participants by end of Q3."
- "Hire a senior operations lead in 60 days."
- "Run a cross-team conference for 200 people this fall."
- "Roll out the updated client intake process across all three teams by June 15."

If your goal does not fit in one sentence yet, it is probably actually two goals. Pick the most important one.

> **You're there when:** you have a one-sentence goal.

---

## Ask Claude to decompose it

> **Hint:** _Decomposition is not a to-do list. It is the real chunks of work that will need to happen. Expect Claude to ask you clarifying questions before it decomposes. That is good._

In your Claude Code window, paste this prompt:

```
Help me decompose this goal into discrete steps.

Goal: [paste your goal]

Ask me clarifying questions first if anything is unclear. Then give me 5 to 10 real chunks of work that will need to happen, each in plain language. Do not give me a to-do list. Give me the real shape of the work.
```

Claude will probably ask you 2 or 3 questions. Answer them. Then it will return a decomposition.

Read it. If something is obviously missing or does not match what you meant by the goal, tell Claude:

```
Your decomposition is missing [X]. Also the step about [Y] is really three smaller steps. Can you rework it?
```

Iterate until the decomposition feels right.

> **You're there when:** you have 5 to 10 chunks of work that together add up to the goal.

---

## Ask Claude to sequence the work

> **Hint:** _Sequencing is not alphabetizing. It is figuring out which pieces depend on which others, and what has to happen before what._

Paste this prompt:

```
Now sequence these steps. Which of them depend on others? Which can happen in parallel? What has to be done first? Lay them out in the order they need to happen, and mark anything that can happen at the same time.
```

Claude will produce a sequence, probably with notes like "these two can happen in parallel" or "this step depends on that step being complete."

Read it. Push back on anything that feels off. Common pushbacks:

```
Step 3 does not actually depend on Step 2. They can run in parallel.
```

```
We cannot start Step 5 until Step 4 is not just done but approved by the director. Add that as a dependency.
```

> **You're there when:** the sequence reflects the actual order things need to happen.

---

## Stress-test the plan

> **Hint:** _This is the step most people skip. It is also the step that saves you the most pain later. Do not skip it._

Paste this prompt:

```
Walk me through what could go wrong with this plan. What am I missing? What assumptions am I making that might not hold? What is the single most likely failure mode?
```

Claude will surface risks and assumptions. Some of them will be obvious (you already knew). Some will not be. Pay attention to the ones that make you uncomfortable.

If Claude flags something real, update the plan:

```
You are right that I am assuming buy-in from the director. Add an explicit step at the top: get director alignment before anything else.
```

Two or three rounds of stress-testing is usually enough. When Claude starts repeating itself, you are done.

> **You're there when:** you have surfaced at least one real risk or missing assumption and updated the plan to account for it.

---

## Assign owners

> **Hint:** _Every step needs one owner. "The team" is not an owner. "Me" is an owner. "Sarah" is an owner._

Paste this prompt:

```
For each step, who needs to own it? If I do not know, help me figure out who should. Assume I have a team of [describe your team] and I can pull in [other groups].
```

Claude will propose owners. If you have a real team in mind, paste their names. If you are figuring it out on the fly, Claude's proposals will at least name the kind of person needed.

One owner per step. No exceptions. If two people share ownership, nobody owns it.

> **You're there when:** every step has exactly one owner named.

---

## The share test

> **Hint:** _A plan is done when you would confidently share it with the team today. Not "someday." Today._

Read the plan as if you were about to send it to your team. Ask yourself:

- Does every step make sense to someone who was not in this conversation?
- Is the sequence clear?
- Would my team know what to do on Monday morning?
- Is every step ownable by the person I named?

If yes to all four: you are done. Save the plan somewhere you can share it.

If no: go back to the step that is weakest and push back on it one more time. Keep iterating.

> **You're done when:** you would send this plan to your team right now without any additional polish.

---

## What You Just Did

You just did the four moves that separate a plan from a wishlist: decompose, sequence, stress-test, assign. You used Claude as a patient collaborator that does not get tired of the hard questions. And you came out with something shareable in 20 minutes.

This pattern works on almost any planning problem you will face. Hiring, launches, conferences, rollouts, program redesigns, quarterly plans, team reorgs. The shape is the same. The details change.

## What Not to Do

1. **Do not skip the stress-test.** It feels optional and it is the most valuable step. Do it every time.
2. **Do not accept "the team" as an owner.** Every step needs one name.
3. **Do not try to nail the first draft.** Plans get better in rounds. Expect two or three passes.
4. **Do not plan alone when you could plan with stakeholders.** Claude is a great first-pass partner but a real stakeholder review is still the final filter.
5. **Do not treat the plan as fixed.** The plan is a starting state. It will change as the work unfolds. That is normal.

## Next Steps

Once you have used this pattern on two or three real initiatives:

- **Build Your First Skill** (easy) — Turn your favorite planning prompt into a reusable `/plan` skill so you can kick this off in one keystroke.
- **Use Plan Mode** (easy) — For tasks Claude will execute, turn on plan mode so you review Claude's approach before it acts.
- **Claude as a Thought Partner** (easy) — When you are not ready to plan yet because the decision itself is still unclear.

## Reference

- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn this workflow into a reusable skill

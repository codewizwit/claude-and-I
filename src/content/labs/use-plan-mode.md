---
title: "Use Plan Mode"
difficulty: easy
time: "20 minutes"
tags: ["plan-mode", "foundational", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A real task you want Claude to help with (something you care about getting right)"
  - "A web browser for the visual artifact"
learn:
  - "What plan mode is and when to turn it on"
  - "How to read a plan Claude proposes before any work happens"
  - "How to push back on a plan to make it match what you actually want"
  - "How to generate an HTML plan review sheet that tracks approved plans and pushback history"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/interactive-mode"
  - "https://docs.anthropic.com/en/docs/claude-code/common-workflows"
order: 4
---

## What You Are Building

A new habit plus an interactive HTML plan review sheet that logs every plan Claude proposes, your pushback, and the final approved plan. Over time it becomes a record of your working style: which kinds of plans you approve on first pass, which need two rounds, which you routinely redirect. That record is gold for teaching teammates what "review before execute" looks like.

Plan mode is Claude saying "let me think first, then act, but only with your approval." Nothing changes until you say go.

By the end you will have:

- The habit of turning plan mode on before anything important
- An HTML plan review sheet file that logs your plan reviews
- A calibrated sense of when Claude needs plan mode and when it does not

> **At work, this comes up when you're...**
>
> - about to run something that affects real documents or systems
> - working on something high-stakes where a mistake costs you time or trust
> - handing Claude a complex task with multiple steps
> - new to Claude Code and still building instinct for what to trust

## Why This Matters

Most people learn Claude Code by jumping in. That works for small safe tasks. It does not work when you are touching something important.

Plan mode slows Claude down to your speed. It reads the situation, proposes a plan in plain English, and waits. You read the plan like a colleague's proposal. You catch the mismatch before any work happens.

The review sheet is the upgrade. Instead of forgetting your plan reviews after the fact, you build a record of patterns: "Claude always misreads this kind of request" or "I routinely redirect on scope." That metacognition makes you a better agent manager.

---

## Pick a task worth thinking about

> **Hint:** _Plan mode is most useful when the task has more than one step, touches something important, or you do not fully trust your first instinct._

Good candidates:

- Drafting a message to a stakeholder
- Reorganizing notes or a document that matters
- Researching a topic where you do not know where to start
- Preparing materials for a meeting
- Making a recommendation you will defend

> **You're there when:** you have a one-sentence task description.

---

## Turn on plan mode

> **Hint:** _Plan mode is a keyboard shortcut. Shift + Tab twice._

Press **Shift + Tab** twice in your Claude Code window. First press switches to auto-accept. Second press switches to plan mode. The indicator at the bottom reads **plan mode on**.

Claude will now read, think, and propose, but will not make changes until you approve.

> **You're there when:** the indicator shows "plan mode on."

---

## Describe the task and wait for the plan

Paste your task description:

```
I want to [describe the task naturally]. Help me put this together.
```

Claude may ask clarifying questions. Answer them. When Claude has enough, it will propose a plan:

```
Here is my plan:
1. Read your notes
2. Identify strongest arguments for and against
3. Draft in three sections: context, assessment, recommendation
4. Match tone to something for a director
5. Show you the draft and wait before making changes

Ready to proceed?
```

Do not approve yet. Read it.

> **You're there when:** Claude has shown a plan and is waiting.

---

## Read the plan like a colleague's proposal

> **Hint:** _You are reviewing, not reading. Ask the questions you would ask if a teammate handed you a one-pager._

Check:

- **Does the approach match what I want?** If the plan treats this as a research task but I need a decision memo, say so.
- **Is anything missing?** A specific source, a format, a constraint.
- **Is anything wrong?** Assumptions that do not hold.
- **Is the scope right?** Bigger or smaller than needed.

Most plans will not be perfect on the first pass. That is the point.

> **You're there when:** you have noticed at least one thing you would tweak.

---

## Push back in plain English

Examples:

```
The plan is good but missing a step. I also want you to compare this against what we got from Vendor Y last year.
```

```
The tone should be less formal. Same facts, but how I actually talk.
```

```
Skip the assessment section. I just need context and recommendation.
```

Two or three rounds before the plan is right. Normal and expected.

When the plan is what you want, approve it.

> **You're there when:** you have pushed back at least once and Claude has revised.

---

## Generate the HTML plan review sheet

Paste this:

```
Now build me a single self-contained HTML file called plan-review.html. Requirements:

- Header: "Plan Reviews" with my name
- A list of plan review entries, most recent first
- Each entry shows:
  - Date and task title
  - Claude's original plan (collapsed by default)
  - My pushback comments (each round shown)
  - The final approved plan
  - Number of rounds until approved
  - A "Lessons" note field I can fill in
- Seed the file with today's review as the first entry
- A stats panel at the top: total plans reviewed, average rounds to approval, most common pushback type (I will tag each plan with one: scope/tone/missing-step/wrong-assumption/other)
- Entries persist via localStorage so the record grows every time I add one
- Clean modern styling, soft palette

Inline CSS and vanilla JavaScript only.
```

Open `plan-review.html`. You should see today's review as the first card.

> **You're there when:** the sheet renders and shows your first plan review.

---

## Use plan mode three more times this week

> **Hint:** _Plan mode is a muscle. You build it by using it on small and medium tasks until it feels automatic._

Try plan mode on:

1. Something small and safe, to get used to the flow
2. Something medium, where getting it wrong would be annoying but recoverable
3. Something high-stakes, where plan mode does real risk-reduction

After each, add the review to your HTML sheet.

> **You're done when:** you have three plan reviews logged and can name when to use plan mode vs when to skip it.

---

## What You Just Did

You just built the habit of reviewing before any work happens:

1. **Caught mistakes** before they happened.
2. **Taught Claude** your standards through feedback.
3. **Built trust** in your own judgment about when Claude needs supervision.
4. **Logged the pattern** so you can see your own review style over time.

## What Not to Do

1. **Do not skip plan mode on anything that matters.** Seconds to review vs minutes to fix.
2. **Do not approve a plan to be polite.** If something is off, say so.
3. **Do not expect the first plan to be right.**
4. **Do not leave plan mode on for every trivial task.** Learn when to turn it off.
5. **Do not treat pushback as failure.** Pushback is the learning loop.

## Next Steps

Once plan mode feels natural:

- **Planning with Claude** (easy) — Apply plan mode thinking to full project planning.
- **Claude as a Thought Partner** (easy) — Use Claude to help you think before you plan.
- **Build Your First Skill** (easy) — Turn a planning pattern into a reusable `/plan` skill.

## Reference

- [Interactive mode (official docs)](https://docs.anthropic.com/en/docs/claude-code/interactive-mode)
- [Common workflows (official docs)](https://docs.anthropic.com/en/docs/claude-code/common-workflows)

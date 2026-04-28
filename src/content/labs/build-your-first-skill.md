---
title: "Build Your First Skill"
difficulty: easy
time: "25 minutes"
tags: ["skills", "foundational", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A task you do at work at least once a week that follows a pattern"
  - "A web browser for the visual artifact"
learn:
  - "How to ask Claude to build a reusable tool for you, in plain English"
  - "How to read and refine what Claude produces so it fits your voice"
  - "How to generate an HTML skill card that visualizes what your skill does at a glance"
  - "How to push back and iterate until you trust a teammate to use it without you"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 1
---

## What You Are Building

A reusable tool (called a "skill") installed in your Claude Code environment, plus an HTML skill card that visualizes what the skill does, when it fires, and how to call it. You open the card in your browser and it reads like a trading card for a capability on your team. Share it with teammates, pin it to a Slack channel, or keep it for future-you.

You are not learning to code. You describe the task, Claude builds the skill file, and Claude generates the HTML card.

By the end you will have:

- A working skill installed at `~/.claude/skills/<name>/SKILL.md`
- An HTML skill card visualizing the skill
- The habit of treating recurring tasks as tools, not prompts

> **At work, this comes up when you're...**
>
> - doing the same kind of writing over and over (status updates, recaps, outreach emails)
> - running repeated analysis patterns across different inputs
> - onboarding someone new and wishing you could hand them your playbook
> - retyping the same kind of prompt to Claude multiple times a week
> - noticing a recurring task that would be nice to call in one line

## Why This Matters

Most people use Claude one prompt at a time. That works but it does not compound. A skill turns a good prompt into a permanent capability. Build it once with Claude, invoke it forever. Share with a team and everyone benefits without repeating your work.

You are also doing your first real act of "agent management." You are deciding what to hand off, how to describe it, and what "done" looks like. The skill is just the artifact. The thinking is the real prize.

---

## Name the task

> **Hint:** _Look at your sent folder or your calendar. The repeated shapes are skill candidates._

Good candidates:

- Writing a weekly status update
- Turning meeting notes into action items
- Drafting an outreach email
- Summarizing an article, PR, or long document
- Researching a company before a call

> **You're there when:** you have one sentence describing the task.

---

## Ask Claude to build it with you

> **Hint:** _Do not try to describe everything upfront. Let Claude's questions pull the details out of you._

Paste this:

```
I want to build my first Claude Code skill. The task I want to automate is: [one sentence].

Ask me 3-5 clarifying questions one at a time. After my answers, draft the skill and explain each part in plain English. Then install it for me at ~/.claude/skills/<name>/SKILL.md.
```

Answer as Claude asks. The questions pull out details you did not know you needed to specify.

> **You're there when:** Claude has asked its questions, you have answered, and the skill is installed.

---

## Read what Claude made

> **Hint:** _You are not being tested on syntax. Just recognize the two parts that matter._

Claude will show you something like this:

```yaml
---
name: weekly-status
description: Draft my weekly status update in my voice. Use every Friday before 4pm or when I mention a weekly check-in.
---

# Weekly Status Update

Draft in my voice based on what I tell you.

## What to include
- Wins: 2-4 concrete things
- Blockers: anything I am stuck on
- Next week: 2-3 priorities

## Voice
- Direct, no filler
- First person, active voice
- Each bullet under 20 words

## Do not
- Do not use emojis
- Do not invent wins I did not mention
```

Two lines matter most:

- **`name`** becomes how you invoke the skill. `/weekly-status`.
- **`description`** is the most important line in the file. Claude reads every skill's description to decide when to activate. Vague descriptions sit unused. Specific ones fire at the right moment.

If your description is vague:

```
Rewrite the description so it names the task and the trigger. Be specific.
```

> **You're there when:** you can point to name and description and explain what each does.

---

## Test the first draft

Paste:

```
/weekly-status [your real week in rough bullets]
```

Read the output. Would you send this?

First version is rarely perfect. Push back:

```
The tone is too formal. Make it sound how I actually talk in Slack.
```

```
You invented a win I did not mention. Tighten the skill so it never adds content I did not provide.
```

Each round teaches Claude what "good" means for you.

> **You're there when:** the output is close to something you would ship.

---

## Test it 3 times on different inputs

> **Hint:** _One good output is not a working skill. Three consistent outputs is._

Try three different inputs:

- A busy week with lots of progress
- A light week where nothing moved (skills often break here by inventing things)
- A messy week where something went sideways

Ask: _Would I trust a teammate to use this without me standing next to them?_

If no, push back and refine.

> **You're there when:** three different inputs all produce outputs you would trust a teammate with.

---

## Generate the HTML skill card

Paste this:

```
Build me a single self-contained HTML file called skill-card.html that visualizes my new skill. It should look like a trading card. Include:

- Skill name as a large header
- Tagline: the description rewritten as one punchy sentence
- "When I fire" section: 3-4 example trigger situations
- "What I produce" section: a short description of the output
- "How to invoke me" section: the /skill-name syntax and one example call
- "Do not" section: the boundaries
- A small "View full SKILL.md" link at the bottom that expands to show the full file contents
- Clean modern styling: good typography, generous whitespace, soft colors

Use only inline CSS and vanilla JavaScript. Save to my working directory.
```

Open `skill-card.html` in your browser. You should see a clean card that tells anyone exactly what this skill does.

> **You're done when:** the card renders and you would be comfortable sharing it with a teammate.

---

## What You Just Did

You just did the four moves at the core of AI at work:

1. **Decomposed** a recurring task into something specific enough to hand off.
2. **Delegated** the build to Claude in plain English.
3. **Iterated** with feedback until the output was right.
4. **Validated** with real inputs until the skill was reliable.
5. **Visualized** the skill as a shareable HTML card.

## What Not to Do

1. **Do not accept a vague description.** Sharpen until the trigger is explicit.
2. **Do not put everything in one skill.** If it starts doing three unrelated things, split it.
3. **Do not forget the "Do not" section.** Boundaries make output predictable.
4. **Do not ship after one good run.** Three inputs.
5. **Do not share a skill before you would trust a teammate to use it without you.**

## Next Steps

When you have used your skill for a week or two:

- **Use Plan Mode** (easy) — Build the habit of reviewing before Claude acts.
- **Claude as a Thought Partner** (easy) — Flip the relationship. Use Claude to probe your thinking.
- **Build a Custom Agent** (medium) — Package skills into a specialist agent.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview
- [Good Prompting](/docs/good-prompting) — patterns that work

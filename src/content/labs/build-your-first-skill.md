---
title: "Build Your First Skill"
difficulty: easy
time: "20 minutes"
tags: ["skills", "foundational", "staff"]
prerequisites:
  - "Claude Code is already open (if you are not sure how, your team lead or IT can help in 2 minutes)"
  - "A task you do at work at least once a week that follows a pattern"
  - "No coding experience needed. You are going to have a conversation with Claude. Claude does the work."
learn:
  - "How to ask Claude to build a tool for you, in plain English"
  - "How to read and refine what Claude produces so it fits your voice"
  - "How to push back and iterate when the first version is not quite right"
  - "How to test a skill until you would trust a teammate to use it without you there"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 1
---

## What You Are Building

By the end of this lab you will have a reusable tool (called a "skill") installed in your own Claude Code environment. You will not write any code. You will have a short conversation with Claude, describe a task you do often, and Claude will build the tool with you.

This is the whole point of Claude Code. You are not learning to configure software. You are learning to delegate intelligently. The tool you walk away with is real, and the muscle memory is what matters most.

> **At work, this comes up when you're...**
>
> - writing the same kind of thing over and over (status updates, meeting recaps, outreach emails)
> - running the same kind of analysis across different inputs (summaries, research, reformatting)
> - onboarding someone new and wishing you could hand them your playbook
> - retyping the same kind of prompt to Claude multiple times a week

## Why This Matters

Most people use Claude one prompt at a time. That works, but it does not compound. A skill turns a good prompt into a permanent capability. Build it once (with Claude's help), and it is available every time you need it. Share it with your team and everyone benefits without repeating your work.

You are also doing your first real act of "agent management." You are deciding what to hand off to Claude, how to describe it, and what "done" looks like. The skill is just the artifact. The thinking is the real prize.

---

## Name the task

> **Hint:** _What is something I do at least once a week that follows the same pattern?_ If nothing jumps out, look at your sent folder or your calendar. The repeated shapes are skill candidates.

Good candidates:

- Writing a weekly status update
- Turning meeting notes into action items
- Drafting an outreach email
- Summarizing an article, PR, or long document
- Researching a company or person before a call
- Reformatting information into a consistent template

You do not need to be precise yet. One sentence is enough. Claude will help you sharpen it.

> **You're there when:** you have one sentence describing the task.

---

## Ask Claude to build it with you

> **Hint:** _Do not try to describe everything upfront. Let Claude's questions pull the details out of you._

In your Claude Code window, paste this prompt. Swap the part in brackets for your task.

```
I want to build my first Claude Code skill. The task I want to automate is: [describe your task in one sentence].

Ask me 3 to 5 clarifying questions one at a time. After my answers, draft the skill for me and explain each part of it in plain English so I understand what you made. Then install it for me so I can use it right away.
```

Send it. Claude will start asking you questions.

That is the whole move. You do not need to know any syntax. Claude's questions will pull out the details that matter: what voice you want, what format you expect, what to include and what to leave out.

**Why this prompt works:**

- **"Ask me questions one at a time"** keeps the conversation in your control. You answer as you think, not all at once.
- **"Explain each part in plain English"** is the learning move. You get the tool AND the understanding of why it is shaped that way.
- **"Install it for me"** means Claude handles the setup. You never touch a file or a folder.

> **You're there when:** Claude has asked its questions, you have answered them, and the skill is installed.

---

## Read what Claude made

> **Hint:** _You are not being quizzed on syntax. You are making sure you understand the shape of what you just built, so you can tweak it later._

Claude will show you something that looks like this, and it will explain it line by line.

```yaml
---
name: weekly-status
description: Draft my weekly status update in my voice. Use every Friday before 4pm or when I mention a weekly check-in.
---

# Weekly Status Update

Draft a weekly status update in my voice based on what I tell you about my week.

## What to include
- Wins: 2-4 concrete things that moved forward this week
- Blockers: anything I am stuck on, named clearly
- Next week: 2-3 priorities for the week ahead

## Voice
- Direct, no filler phrases
- First person, active voice
- Each bullet under 20 words

## Do not
- Do not use emojis
- Do not invent wins I did not mention
```

### The two things worth understanding

You do not need to memorize the syntax. You only need to recognize two parts:

**1. The `name` line** becomes how you call the skill. `name: weekly-status` means you can type `/weekly-status` to invoke it.

**2. The `description` line** is the most important line in the whole skill. Claude reads every skill's description and uses it to decide when to activate. If the description is vague, the skill sits unused. If it is specific, Claude pulls it in at exactly the right moment.

Everything below the `---` lines is the actual instructions. Think of it like onboarding a new teammate. Tell them what to do, what voice to use, what format, and what to avoid.

### Good vs bad descriptions

If anything needs refining, it is usually the description. Here is what good and bad look like:

| Bad                                                              | Why It Fails                                 |
| ---------------------------------------------------------------- | -------------------------------------------- |
| `description: weekly status`                                     | Too short. Does not say when to use it.      |
| `description: This skill helps you write things faster with AI.` | Generic. Could apply to anything.            |
| `description: Writes stuff`                                      | Tells Claude nothing about when to activate. |

| Good                                                                                                                                                   | Why It Works                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------- |
| `description: Draft my weekly status update in my voice. Use every Friday before 4pm or when I mention a weekly check-in.`                             | Specific task, specific trigger.          |
| `description: Summarize a meeting transcript into action items with owners and due dates. Use when I paste a transcript or mention notes from a call.` | Clear input, clear output, clear trigger. |
| `description: Research a company before a sales call. Pull recent news, leadership, and recent funding. Use when I ask about a company by name.`       | Bounded scope. Claude knows exactly when. |

If your description feels vague, just ask Claude in plain English:

```
Rewrite the description. Make it more specific about when I would want this skill to kick in.
```

> **You're there when:** you can point to the name and description lines and explain what each one does.

---

## Run it. Did it do what you expected?

> **Hint:** _The first version is almost never perfect. That is not a failure. That is the whole point of this checkpoint._

In the same Claude Code window, try your new skill with a real example from your actual work:

```
/weekly-status This week I finished the Q2 report draft, unblocked the team on the budget review, and started the new vendor onboarding. Blocker: waiting on legal for the contract. Next week I want to close legal review and send the report to the VP.
```

Read the output carefully. Ask yourself:

- Does it sound like me?
- Does it follow the format I wanted?
- Did it avoid the things I said to avoid?
- Would I actually send this, or would I rewrite it first?

### The first version is rarely perfect. That is a learning opportunity.

If the output is not quite right, you are not stuck. You are doing the real work now. Push back with Claude in plain English and explain what was off. Be specific.

Examples of useful push-back:

```
The update was too formal. It sounds like a press release. Update the skill so the tone is more casual, like how I actually talk in Slack.
```

```
It missed the Next Week section entirely. Fix the skill so that section always shows up, even if I forget to mention it.
```

```
The bullets are too long. Update the skill so each bullet is under 15 words.
```

```
It made up a win I did not mention. Tighten the skill so it only includes things I explicitly said happened.
```

Each round of push-back is you teaching Claude what "good" looks like for you. The skill gets better every time. This is the muscle memory that matters, more than any single skill you build.

> **You're there when:** you have pushed back at least once and the output is closer to what you wanted.

---

## Run it 3 times on different inputs. Is it reliable?

> **Hint:** _One lucky output is not a working skill. Three good outputs in a row is._

Test your skill on three different real examples. Not the same one three times. Three different weeks, three different topics, three different inputs.

Ask yourself the hard question after each run:

- Is the output consistently useful across different inputs?
- Is the voice steady, or does it drift?
- Does it handle the edge cases (short weeks, busy weeks, weeks with no blockers)?

**Then ask yourself the real test:**

> _Would I trust a teammate to use this skill without me standing next to them to explain it?_

If the answer is yes, you are done. You have a skill you can share.

If the answer is no, go back to Claude and explain what is inconsistent. Something like:

```
When I ran the skill on a week with no blockers, it invented one. Fix the skill so it writes "None" when I do not mention any.
```

```
The tone is casual when the week is light, but formal when the week is busy. Make the voice consistent regardless of how much detail I give.
```

Keep iterating until three in a row pass the teammate test.

> **You're done when:** three different inputs all produce output you would trust a teammate to use without explanation.

---

## What You Just Did

You just did the four things that make up the core of working with AI at your job:

1. **Decomposed** a recurring task into something specific enough to hand off.
2. **Delegated** the build to Claude by describing what you wanted.
3. **Iterated** with plain-English feedback until the output was right.
4. **Validated** with real inputs until the skill was reliable enough to trust.

That is agent management. You will do this same pattern dozens of times as you build out your toolkit. The skill you built today will pay you back every week. Six months from now you will have ten or twelve of these, and your work will feel different.

## What Not to Do

1. **Do not accept a vague description.** Ask Claude to sharpen it until you can clearly say when the skill should kick in.
2. **Do not put everything in one skill.** If your skill starts doing three unrelated things, ask Claude to split it into three separate skills.
3. **Do not forget the "do not" section.** Telling Claude what to avoid is as important as telling it what to do.
4. **Do not ship a skill after one good run.** Test on three different inputs before you trust it.
5. **Do not share a skill before you would trust a teammate to use it without you.** That is the real "done" line.

## Next Steps

When you have used your skill for a week or two and refined it based on real output, move on to:

- **Advanced Skill Building** (medium) — Skills that load supporting files only when needed. Useful for bigger tools with templates and examples.
- **Build a Custom Agent** (medium) — Package a group of skills into a specialist agent for a specific part of your work.
- **Agent Teams** (hard) — Orchestrate multiple agents into a workflow that decomposes, delegates, and aggregates results.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work
- [Good Prompting](/docs/good-prompting) — the patterns that make skill instructions actually work

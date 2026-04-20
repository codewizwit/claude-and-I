---
title: "Claude as a Thought Partner"
difficulty: easy
time: "15 minutes"
tags: ["thought-partner", "foundational", "decisions"]
prerequisites:
  - "Claude Code is already open"
  - "A real decision, idea, or situation you are actually wrestling with right now"
  - "No coding experience needed. You will talk, Claude will reflect back."
learn:
  - "How to set Claude up as a thought partner, not a task-doer"
  - "How to get Claude to probe your thinking instead of giving you answers"
  - "How to notice the assumption you were missing, the counter-case you were avoiding, and the failure mode you were not seeing"
  - "When to use Claude this way and when to use it differently"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/interactive-mode"
order: 3
---

## What You Are Building

Not a file. A new way to use Claude. By the end of this lab you will know how to flip Claude out of "helpful assistant" mode and into "thought partner" mode, where Claude does not offer ideas at all. It only asks the questions that help you think more clearly.

This is called mirror mode. In this mode Claude reflects your thinking back at you. It probes assumptions. It steel-mans the position you did not want to hear. It finds the edge where your idea might break. Every thought that comes out of the session is yours. Claude did not hand you anything. It just asked the right questions.

> **At work, this comes up when you're...**
>
> - making a decision you will have to defend and want to know where the holes are
> - prepping for a hard conversation and wondering what you are not seeing
> - stress-testing a plan before you commit to it
> - writing a recommendation and want to know the strongest counter-case
> - stuck, and more advice is not what you need, more clarity is

## Why This Matters

Most people use Claude as a task-doer: "write this", "summarize that", "plan this." That is useful. But it has a ceiling. The quality of the output is capped by what you knew to ask for.

Thought partner mode breaks the ceiling. Instead of extracting an answer from Claude, you use Claude to extract the answer from yourself. You leave the conversation with better thinking, not with a document.

This is also the mode that builds judgment. Every session, you notice an assumption you were carrying, a question you were avoiding, a consequence you were not imagining. That noticing is a skill. You get better at it every time you do this.

---

## Pick the real thing

> **Hint:** _Pick something you actually care about. The exercise only works on real weight. Do not use a made-up example._

Think of something you are wrestling with right now. Good candidates:

- A decision you have been delaying
- A recommendation you will need to defend to your team or your boss
- A strategy you are pretty sure about but have not stress-tested
- A conversation you are anxious about having
- An opinion you hold that you have never really examined

Say it out loud or write it down in one sentence.

> **You're there when:** you have one sentence describing the real thing.

---

## Set Claude up as a thought partner

> **Hint:** _The setup prompt matters. If you skip it, Claude will default to giving advice, which is the opposite of what you want._

In your Claude Code window, paste this prompt:

```
I want you to be my thought partner for the next 15 minutes. Do not offer suggestions, opinions, recommendations, or ideas of your own. Your only job is to ask probing questions that help me think more clearly.

Specifically:
1. Reflect back what you hear me saying, in my own words, so I can check it
2. Probe my assumptions
3. Ask me what I would say if someone disagreed
4. Ask me what the version of this that fails looks like

One question at a time. Wait for my answer before asking the next one. If I start pulling for advice, redirect me back to my own thinking.

Ready?
```

Send it. Claude will confirm the mode. Now you are set up.

> **You're there when:** Claude has confirmed it will only ask questions, not give answers.

---

## Say the thing out loud

> **Hint:** _Do not try to be articulate. The messier the better. Claude will clean it up by asking you to clarify._

Type out what you are wrestling with. Do not polish it. Imagine you are venting to a friend who you trust to just listen.

Example of what this could look like:

```
I am trying to decide whether to reorganize my team next quarter. I think it would be good for the work but I am worried about the morale hit and I am not sure if I have enough political capital to pull it off. Also I keep telling myself I am doing it for the work but I am worried I am actually doing it because I am frustrated with one person.
```

Claude will reflect back what it heard and ask you a probing question. Answer it honestly. Claude will ask another. You are in the loop now.

> **You're there when:** Claude has asked you at least two questions and you have answered them.

---

## Find the edges

> **Hint:** _The best questions from Claude feel slightly uncomfortable. That is the signal you are getting somewhere._

If Claude is staying too surface-level, ask for harder questions. Try:

```
Ask me the question that someone who disagrees with me would ask.
```

or

```
What am I assuming that I have not examined?
```

or

```
Walk me through the version of this where it fails. What was the first thing that went wrong?
```

These three prompts do the real work. They find the blind spot, the hidden assumption, and the failure mode. You will probably notice at least one of those in the next few minutes. That noticing is the whole point of the session.

> **You're there when:** you have caught yourself saying "oh" or "actually" or "I had not thought about that" at least once.

---

## Close the loop

> **Hint:** _The session is done when Claude can hand back your thinking, clearer than you gave it, without adding anything._

When you feel you have the clarity you wanted, ask Claude:

```
Summarize what I just worked through, in my own words, so I have a clean record.
```

Claude will give you back your own thinking, tightened up. Notice that nothing in that summary is Claude's idea. Every piece is yours. That is the whole trick. You used Claude to think, and you walked away with better thinking, not a document someone else made.

If you want to keep the record, save the summary somewhere you can revisit it. Decisions you document are easier to defend later.

> **You're done when:** you can articulate the decision, assumption, or insight more clearly than you could at the start.

---

## What You Just Did

You just flipped the relationship. Claude was not your assistant in this session. It was your mirror. You did four things:

1. **Set a boundary.** No suggestions, only questions.
2. **Spoke messily.** Let the real thought come out before trying to clean it up.
3. **Found the edges.** Used Claude to surface the assumption, the counter-case, and the failure mode you were avoiding.
4. **Closed the loop.** Got your own thinking back, clearer than when you started.

This is agent management at its purest. You are managing the agent by telling it what NOT to do, which is harder and more useful than telling it what to do.

## What Not to Do

1. **Do not skip the setup prompt.** Without it, Claude will slip into advice-giving mode. The boundary only holds if you set it.
2. **Do not pull for answers.** If you catch yourself asking "so what should I do?", that is the signal that you are not in mirror mode anymore. Redirect.
3. **Do not rush to polish.** The messy version of the thing contains the real answer. Give yourself permission to be imprecise at the start.
4. **Do not use this mode for everything.** When you need a draft, Claude doing the drafting is faster. Thought partner mode is for decisions, not deliverables.
5. **Do not hide from uncomfortable questions.** If a Claude question lands uncomfortably, stay with it. That is the one that matters.

## Next Steps

When you are fluent with thought partner mode, try:

- **Use Plan Mode** (easy) — The planning counterpart. Claude thinks through a task before doing it.
- **Planning with Claude** (easy) — Take the thinking you did here and turn it into a plan you can execute.
- **Build Your First Skill** (easy) — Turn your best thought partner prompt into a reusable skill you can invoke any time.

## Reference

- [Interactive mode (official Claude Code docs)](https://docs.anthropic.com/en/docs/claude-code/interactive-mode)
- [Build Your First Skill](/labs/build-your-first-skill) — turn this pattern into a reusable skill

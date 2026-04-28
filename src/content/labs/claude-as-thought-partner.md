---
title: "Claude as a Thought Partner"
difficulty: easy
time: "20 minutes"
tags: ["thought-partner", "decisions", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A real decision, idea, or situation you are actually wrestling with"
  - "A web browser for the visual artifact"
learn:
  - "How to set Claude up as a thought partner, not a task-doer"
  - "How to get Claude to probe your thinking instead of giving you answers"
  - "How to generate an interactive HTML thought map that grows as you probe"
  - "How to notice the assumption, counter-case, and failure mode you were missing"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/interactive-mode"
order: 5
---

## What You Are Building

An interactive HTML thought map of your own thinking about a real decision. Every assumption, counter-case, and failure mode you name becomes a node on the map. The map grows as you talk. At the end, you can see the whole shape of your own thinking on one page and share it with someone who needs to understand how you arrived at a decision.

You are not learning to code. Claude plays thought partner, you do all the thinking, and Claude generates the visual map.

By the end you will have:

- A real decision, idea, or situation you thought through with Claude as mirror
- An HTML thought map showing your full reasoning tree
- A new instinct for when to use Claude as partner vs task-doer

> **At work, this comes up when you're...**
>
> - making a decision you will have to defend and want to know where the holes are
> - prepping for a hard conversation and wondering what you are not seeing
> - stress-testing a plan before you commit
> - writing a recommendation and want to know the strongest counter-case
> - stuck, and more advice is not what you need — more clarity is

## Why This Matters

Most people use Claude as a task-doer: "write this," "plan that." Useful but has a ceiling. The quality of output is capped by what you knew to ask for.

Thought partner mode breaks the ceiling. You use Claude to extract the answer from yourself. You leave with better thinking, not a document.

The thought map is the upgrade. Text conversations with Claude scroll away. A visual tree of your reasoning is something you refer back to when the decision comes up again in a month.

---

## Pick the real thing

> **Hint:** _Pick something you actually care about. The exercise only works on real weight._

Good candidates:

- A decision you have been delaying
- A recommendation you need to defend
- A strategy you are pretty sure about but have not stress-tested
- A conversation you are anxious about having
- An opinion you hold that you have never really examined

> **You're there when:** you have one sentence describing the real thing.

---

## Set Claude up as a thought partner

> **Hint:** _The setup prompt matters. If you skip it, Claude defaults to giving advice._

Paste this:

```
I want you to be my thought partner for the next 20 minutes. Do not offer suggestions, opinions, recommendations, or ideas of your own. Your only job is to ask probing questions that help me think more clearly.

Specifically:
1. Reflect back what you hear me saying, in my own words
2. Probe my assumptions
3. Ask what I would say if someone disagreed
4. Ask what the version of this that fails looks like

One question at a time. Wait for my answer before the next. If I pull for advice, redirect me back to my own thinking.

After each of my answers, also tag it with one of: [assumption], [counter-case], [failure-mode], [core-belief], [open-question]. These tags will build a thought map at the end.

Ready?
```

> **You're there when:** Claude has confirmed the mode.

---

## Say the thing out loud

> **Hint:** _Do not try to be articulate. Messier is better. Claude will clean it up by asking you to clarify._

Type what you are wrestling with. Do not polish. Imagine venting to a friend you trust to just listen.

Claude will reflect back and ask a probing question. Answer honestly. Claude asks another. You are in the loop.

> **You're there when:** Claude has asked at least two questions and you have answered.

---

## Find the edges

> **Hint:** _The best questions feel slightly uncomfortable. That is the signal you are getting somewhere._

If Claude stays too surface-level, ask for harder questions:

```
Ask me the question someone who disagrees would ask.
```

```
What am I assuming that I have not examined?
```

```
Walk me through the version where this fails. What went wrong first?
```

You will probably notice an assumption, a counter-case, or a failure mode you were avoiding. That noticing is the whole point.

> **You're there when:** you have caught yourself saying "oh" or "actually" at least once.

---

## Close the loop

Paste:

```
Summarize what I worked through, in my own words, so I have a clean record. Do not add anything. Keep all your tags on my statements so I can build a map.
```

Claude hands back your own thinking, tightened up. Nothing is Claude's idea.

> **You're there when:** you have a clean summary of your own reasoning.

---

## Generate the interactive HTML thought map

Paste this:

```
Now build me a single self-contained HTML file called thought-map.html that visualizes the reasoning tree of our conversation. Requirements:

- Header: the question or decision I was wrestling with
- A radial or tree layout where the central node is the core question
- Each of my tagged statements becomes a node on the map. Color-coded by tag:
  - [core-belief] green
  - [assumption] yellow
  - [counter-case] orange
  - [failure-mode] red
  - [open-question] blue
- Lines connect related nodes (the connection reasoning comes from our conversation flow)
- Clicking a node shows the full statement and any reflective question Claude asked about it
- Below the map: a timeline of the conversation showing how my thinking evolved
- Footer: a "What I believe now" box I can fill in, and a "Revisit" date picker
- Clean modern styling, soft palette

Use D3.js or Chart.js via CDN for layout. Otherwise inline CSS and vanilla JS.
```

Open `thought-map.html` in your browser. You should see your reasoning tree. Click nodes. See the whole shape.

> **You're done when:** the map renders and you can trace your own reasoning visually.

---

## What You Just Did

You flipped the relationship. Claude was not your assistant. It was your mirror.

1. **Set a boundary.** No suggestions, only questions.
2. **Spoke messily.** Let real thought emerge.
3. **Found the edges.** Surfaced assumptions, counter-cases, failure modes.
4. **Closed the loop.** Got your thinking back clearer.
5. **Visualized the reasoning** as a shareable tree.

This is agent management at its purest. You managed Claude by telling it what NOT to do.

## What Not to Do

1. **Do not skip the setup prompt.** Without it Claude slips into advice.
2. **Do not pull for answers.** If you catch yourself asking "what should I do," redirect.
3. **Do not rush to polish.** The messy version contains the real answer.
4. **Do not use this mode for everything.** When you need a draft, let Claude draft.
5. **Do not hide from uncomfortable questions.**

## Next Steps

When you are fluent with thought partner mode:

- **Use Plan Mode** (easy) — The planning counterpart.
- **Planning with Claude** (easy) — Turn thinking into a plan.
- **Build Your First Skill** (easy) — Turn your best thought-partner prompt into a reusable skill.

## Reference

- [Interactive mode (official docs)](https://docs.anthropic.com/en/docs/claude-code/interactive-mode)
- [Build Your First Skill](/labs/build-your-first-skill)

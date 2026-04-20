---
title: "Break Out of PowerPoint"
difficulty: medium
time: "30 minutes"
tags: ["presentations", "creative", "storytelling"]
prerequisites:
  - "Claude Code is already open"
  - "A real thing you need to present soon (a pitch, a decision, a recap, an update, a vision)"
  - "Openness to the idea that slides might not be the right format"
learn:
  - "How to pick the right format for what you are actually trying to do"
  - "How to write the talk first and let slides follow, instead of the other way around"
  - "How to build a story-driven presentation with Claude as your editor"
  - "Alternatives to slides when slides are not the right answer"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/overview"
order: 6
---

## What You Are Building

A presentation that actually lands. Not a deck of bullet points that your audience politely endures. By the end of this lab you will have written the talk, chosen the right format (which may not be slides), and produced the materials to deliver it.

The move is simple and most people skip it: **write the thing you want to say before you open the slide tool.** Slides are a visual aid, not a document. When you design the slides first, you end up with a document that also does not read well. When you write the talk first, the slides become whatever supports the talk, which is usually less than you think.

> **At work, this comes up when you're...**
>
> - presenting a decision or recommendation that actually matters
> - giving a vision talk, a kickoff, a quarterly update, or a strategy review
> - realizing your last three presentations felt flat and you do not know why
> - tempted to drop 40 bullets onto 20 slides because that is what everyone else does
> - wondering if slides are even the right format for what you need to do

## Why This Matters

The default for most professionals is "open PowerPoint, start typing." That default produces a category of presentation that neither reads well nor presents well. The audience zones out because the slides are too dense. The speaker reads off the slides because they never wrote the talk. Everyone leaves remembering nothing.

Breaking out of this pattern does two things: it forces you to clarify what you are actually saying (because prose exposes unclear thinking in a way bullets do not), and it opens up format choices you did not know you had. Sometimes the right answer is a one-page memo. Sometimes it is a demo. Sometimes it is a single slide. Sometimes it is still a deck, but a deck that earns every slide.

---

## Say what you are trying to do

> **Hint:** _Not the topic. The intended outcome. "What do I want the audience to think, feel, or do when this is over?"_

In your Claude Code window, paste this prompt:

```
I need to present [describe the thing] to [describe the audience]. Before I pick a format, help me get clear on three things:

1. What do I want the audience to think, feel, or do when this is over?
2. What do they already know, and what would be new to them?
3. What is the one sentence they should walk away repeating?

Ask me questions one at a time until I can answer all three clearly.
```

Claude will walk you through it. Answer honestly. Most presentations fail at this step, not at the design step.

> **You're there when:** you can answer all three questions in one or two sentences each.

---

## Pick the right format

> **Hint:** _Slides are one option, not the only option. Ask which format actually serves the intended outcome._

Paste this prompt:

```
Based on what I told you, recommend the right format for this presentation. Consider:

- A written memo people read first, then discuss
- A single-slide summary with a conversation
- A short demo (live or recorded)
- A story-driven narrative talk with a few visual slides
- A traditional deck (and if so, how many slides is the honest answer)
- Something else entirely

Tell me which format would actually work best given my goal and audience, and why.
```

Claude will recommend a format with reasoning. Read the reasoning carefully. You may push back:

```
A memo will not work because my audience will not read it in advance. What is the next best option?
```

```
I have to use slides because leadership expects them. Given that constraint, what is the tightest version?
```

The goal is honesty about what will actually work in your context.

> **You're there when:** you have picked a format and can say why it fits.

---

## Write the talk first

> **Hint:** _Write what you would say, not what would go on the slides. Prose first. Visuals later._

Paste this prompt:

```
I am going to write the talk first, in prose, before I design anything visual. Help me draft it.

Goal: [paste your goal from Checkpoint 1]
Audience: [paste audience]
One sentence they should walk away repeating: [paste that sentence]
Format chosen: [paste format]
Time I have to present: [X minutes]

Draft the talk as flowing prose, using a story structure (setup, tension, resolution). Use my voice (direct, warm, not corporate). Do not include slide notes or formatting. Just the words I would say.
```

Claude will produce a draft. Read it aloud. You will notice the parts that do not sound like you, the sentences that are too long to speak, the transitions that do not land. Push back:

```
The opening is too corporate. Rewrite it like I am telling my team a story over coffee.
```

```
The middle is flat. There is no tension. Rework it so the audience feels the problem before they hear the solution.
```

```
The ending is vague. Make the ask explicit. I need them to commit to X by Y.
```

Iterate two or three rounds.

> **You're there when:** you can read the talk aloud and it sounds like you, flows well, and makes the point.

---

## Derive the visuals from the talk

> **Hint:** _Every slide must earn its place. If the slide repeats what you are saying, it is dead weight._

Paste this prompt:

```
Here is my talk: [paste the draft].

Now tell me: what visuals (if any) would support this talk? For each one:

- What is the slide for (not what is on it, what does it do for the audience)
- What is the minimum content needed (one image, one word, one chart, one diagram)
- Where in the talk it appears

Do not give me more than 5 slides. Fewer is better. If a slide does not earn its place, cut it.
```

Claude will propose visuals. You will probably end up with 3 to 7 slides, each doing real work. That is the whole deck.

If you are not using slides, ask instead:

```
What single artifact (one image, one chart, one short memo, one demo clip) would most support this talk?
```

Sometimes the answer is "nothing, just talk." That is a real answer.

> **You're there when:** you have a list of visuals (or a single supporting artifact) and can justify each one.

---

## The rehearsal

> **Hint:** _Reading the slides back does not count. Reading the talk aloud, without slides, does._

Read the talk aloud, start to finish, without looking at your visuals. Time it. Ask yourself:

- Did I stumble anywhere? That is where the language is not yet yours.
- Did I lose my place? That is where the structure is weak.
- Did I run long or short? Adjust the pacing.
- Does the ending land? If not, something earlier is wrong.

Go back and revise. This is the step that turns a presentation from passable to memorable.

> **You're done when:** you can deliver the talk cold, from start to finish, and the ending lands the way you wanted.

---

## What You Just Did

You just broke four defaults at once:

1. **Outcome before format.** You asked what you wanted to happen, not what tool to open.
2. **Talk before visuals.** You wrote what you would say, and let the visuals follow.
3. **Every slide earns its place.** You cut anything that did not do real work.
4. **Rehearsal as part of design.** You treated the rehearsal as a revision step, not a final check.

You also did agent management at a higher level: you used Claude to push back on your own defaults, not just to produce artifacts. That is the mature version of this skill.

## What Not to Do

1. **Do not open the slide tool first.** Every minute spent in the slide tool before the talk is written is a minute making the talk worse.
2. **Do not cram every point into slides.** If the audience can read the slides, they do not need you. The slides support the talk, not replace it.
3. **Do not skip the format question.** Slides are not always the right answer. Pretending they are costs you and your audience.
4. **Do not rehearse by reading.** Rehearse by speaking. The talk lives in your mouth, not on the page.
5. **Do not keep a slide just because it looks good.** If it does not serve the point, cut it.

## Next Steps

Once you have run this pattern on a real presentation:

- **Build Your First Skill** (easy) — Turn your favorite prompt from this lab into a reusable "talk structure" or "deck review" skill.
- **Claude as a Thought Partner** (easy) — Use thought partner mode before this lab to figure out what you even want to say.
- **TLDR: Explain It Like I'm...** (easy) — Use audience framing to tighten the opening and the key line.

## Reference

- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn your favorite prompt into a reusable tool

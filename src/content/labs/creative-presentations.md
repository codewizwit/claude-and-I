---
title: "Creative Presentations"
difficulty: medium
time: "30 minutes"
tags: ["presentations", "storytelling", "creative", "narrative"]
prerequisites:
  - "Claude Code is already open (if you are not sure how, your team lead or IT can help in 2 minutes)"
  - "A real thing you need to present soon (a pitch, a decision, a recap, a vision, a proposal)"
  - "Openness to the idea that slides might not be the best container for your ideas, and that PowerPoint is not the only tool"
learn:
  - "How to prompt Claude for a narrative structure before you open any slide tool"
  - "How to write the talk as a story first and let the visuals follow"
  - "How to build a presentation in HTML or Marp (markdown-based slides) that is more memorable than bullet-point decks"
  - "How to rehearse from the narrative, not from the slides"
docs:
  - "https://marp.app/"
  - "https://docs.anthropic.com/en/docs/claude-code/overview"
order: 9
---

## What You Are Building

A narrative-driven presentation that people actually remember. By the end of this lab you will have a story-structured outline, a set of visuals shaped by the story (not the other way around), and a presentation built in HTML or Marp instead of PowerPoint.

The move is simple and most people skip it: **prompt Claude for the narrative before you ever open a slide tool.** Slides are a visual aid, not a document. When you design the slides first, you end up with a document that also does not present well. When you write the narrative first, the slides become whatever supports the talk, which is usually less than you think.

> **At work, this comes up when you're...**
>
> - presenting a decision, a vision, or a recommendation that actually matters
> - tired of making and watching the same flat bullet-point decks that nobody remembers
> - wanting a presentation to feel designed, not dumped
> - realizing your last three talks felt corporate and you do not know why
> - wondering if there is a better way than opening PowerPoint and staring at the title slide

## Why This Matters

The default for most professionals is "open PowerPoint, pick a template, start typing bullets." That default produces presentations that neither read well nor present well. The audience zones out because the slides are too dense. The speaker reads off the slides because they never wrote the talk. Everyone leaves remembering nothing.

Breaking out of this pattern does two things. First, it forces you to clarify the story you are actually telling, because prose exposes unclear thinking in a way bullets do not. Second, it opens up format choices you did not know you had. HTML presentations and Marp decks are more flexible, more elegant, and more memorable than slide templates. They let you control the pacing, the typography, and the feel of the whole thing.

You are also going to lean on Claude for the narrative structure. That is the highest-leverage move in this lab. A good narrative arc makes an average talk great. A bad narrative arc makes even great content forgettable.

---

## Prompt Claude for the narrative first, before any tool

> **Hint:** _Do not open PowerPoint. Do not open Keynote. Do not open a Google Slides template. Open Claude Code and describe the presentation in plain English._

In your Claude Code window, paste this prompt. Fill in the brackets with real details.

```
I need to create a presentation. Before I touch any slide tool, I want to get the narrative right.

Topic: [describe the topic in one sentence]
Audience: [who is in the room, what they care about, what they already know]
Time I have: [X minutes]
The one sentence they should walk away repeating: [what you most want them to remember]

Ask me 4 to 6 clarifying questions one at a time. Then propose a narrative arc with 3 to 5 story beats. For each beat, give me:
- The beat's role in the story (setup, tension, turn, resolution)
- The core idea of that beat, in one sentence
- The emotional register (curious, uncomfortable, hopeful, decisive, etc.)

Do not suggest slides yet. Do not suggest visuals. Just the story.
```

Claude will start asking you questions. Answer honestly, not aspirationally. If the audience is actually skeptical, say skeptical. If you are actually nervous about one part, say so.

When Claude proposes the narrative arc, read it slowly. Ask yourself:

- Does this story structure match what I am actually trying to do?
- Is there tension in the middle, or does it flatten out?
- Does the resolution actually land the one sentence I said I wanted them repeating?

Push back in plain English if anything is off:

```
The third beat is too similar to the second. Make it the turn, not another piece of setup. I want the audience to feel the shift in their thinking here.
```

```
The arc is too smooth. Add a real tension point in the middle where the audience is uncomfortable or surprised. Right now it reads like a report, not a story.
```

> **You're there when:** you have a 3 to 5 beat narrative arc you could read aloud and follow like a story.

---

## Write the talk as flowing prose

> **Hint:** _Write what you would say, not what would go on the slides. Prose first. Visuals come later. This is where most presentations die._

Paste this:

```
Now write the talk as flowing prose, based on the narrative arc we just agreed on. Rules:

- Write it as a script of what I would actually say, not as slide content
- Use my voice: direct, warm, no corporate filler
- Keep the tension point from the third beat intact
- Each section should have a clear transition into the next
- Avoid bullet-point thinking entirely. Write in paragraphs.
- Target about [X minutes] when read aloud at a conversational pace

Do not include slide notes or stage directions. Just the words I would speak.
```

Read the draft aloud. Yes, literally aloud. Do not skip this. You will catch:

- Sentences that are too long to speak
- Openers that sound too corporate
- Transitions that do not land
- Moments where you lose your own attention

Push back:

```
The opening is too formal. Rewrite it like I am telling my team a story over coffee. Name the real stakes in the first sentence.
```

```
The middle went flat. The tension point got softened. Rewrite so the audience actually feels the problem before they hear the solution.
```

```
The ending hedges. Make the ask explicit. I need them to commit to X by Y.
```

Iterate two or three rounds until the talk flows and you can read it without stumbling.

> **You're there when:** you can read the talk aloud start to finish and it sounds like you, with a clear arc and a real ending.

---

## Choose the format: HTML or Marp

> **Hint:** _Marp is a markdown-based slide tool. HTML is a full webpage. Both beat PowerPoint for custom, memorable presentations. Pick based on what you actually need._

You have two strong options that are not PowerPoint:

**Marp (`marp.app`) is best when you want:**

- Fast, markdown-based slides with clean typography
- Export to PDF, PowerPoint, or a standalone HTML file
- Simple slide decks where you want to focus on content and minimal design overhead
- A preview right inside your editor

**HTML is best when you want:**

- A scrolling, story-driven experience (more like a well-designed webpage)
- Custom animations, interactive elements, or embedded media
- Something that does not feel like a deck at all
- Full control over spacing, typography, and layout

Ask Claude which one fits:

```
Based on my talk, audience, and time, which format would work better: Marp (markdown slides) or HTML (a custom scrolling page)? Give me your recommendation and why, then show me a minimal starter for whichever one you recommend.
```

Claude will recommend one and generate a starter file. If you disagree with the recommendation, push back:

```
I want HTML instead. This talk is only going to be seen live, and I want it to feel more like a conversation than a deck.
```

> **You're there when:** you have picked a format and you have a starter file open.

---

## Let Claude derive the visuals from the talk

> **Hint:** _Every slide must earn its place in the story. If a visual just repeats what you are saying, it is dead weight. Cut it._

Paste this (attach or paste your finished talk prose):

```
Here is my talk: [paste the draft].

Now generate a [Marp deck / HTML presentation] that supports this talk, with these rules:

- Fewer slides is better. Aim for 3 to 7 total.
- Every slide has to earn its place. Cut anything that just repeats what I am saying aloud.
- Each slide should be visually minimal. One image, one short phrase, one chart, one diagram. Not all four.
- Map each slide to a specific moment in the narrative: setup, tension, turn, resolution.
- Do not include slide notes with the full script. I am memorizing this from the prose, not reading off the slides.
- Use clean typography. Large type, lots of whitespace.

Produce the full file I can save and present from.
```

Claude will generate the file. Open it in a browser (HTML) or Marp preview. Walk through it while reading the talk aloud. Ask:

- Does every slide serve the story?
- Is there any slide that makes me want to read it instead of listen to me?
- Does the visual rhythm match the emotional rhythm of the talk?

Push back:

```
Slide 3 has too much text. Replace the bullets with one image and one sentence that captures the tension point.
```

```
The whole deck is too uniform. Make the tension-point slide visually different from the rest (maybe darker, larger type, more space) so the audience feels the shift.
```

If a slide is not earning its place, tell Claude to cut it. A 5-slide deck for a 15-minute talk is almost always better than a 20-slide deck.

> **You're there when:** every slide serves the talk, and cutting any one slide would weaken the arc.

---

## Rehearse from the narrative, not from the slides

> **Hint:** _Good speakers rehearse the talk. Bad speakers rehearse the slides. The talk lives in your mouth, not on the screen._

Print the prose script, or put it on a second screen. Do not look at the slides. Read the talk aloud start to finish. Time it. Ask yourself:

- Did I stumble anywhere? That is where the language is not yet yours.
- Did I run long or short? Adjust pacing, not content.
- Does the tension point still land? If you rush through it in rehearsal, you will rush through it live.
- Does the ending feel inevitable or forced? If forced, go back to the narrative arc and tighten.

Once the talk reads clean without slides, do one more pass with slides. This time, check that the slide changes feel natural, not interruptive. If a slide break pulls you out of the story, move or cut that slide.

> **You're done when:** you can deliver the whole talk cold, the slides feel like natural punctuation, and the ending lands.

---

## What You Just Did

You just broke four defaults at once:

1. **Narrative before tool.** You prompted Claude for the story structure before opening any slide app.
2. **Prose before slides.** You wrote the talk as flowing prose, so the story could actually have an arc.
3. **Format by intent.** You chose HTML or Marp based on what the talk needed, not because PowerPoint was the default.
4. **Rehearsal from the talk.** You memorized the story, not the slides. Slides became punctuation, not a script.

You also did something most presenters never do: you let Claude act as a story editor, not just a layout generator. That is the mature version of this skill.

## What Not to Do

1. **Do not open the slide tool first.** Every minute in the slide tool before the narrative is written is a minute making the talk worse.
2. **Do not accept a generic narrative arc.** If Claude's first pass reads like a report, push back until it has a real turn in the middle.
3. **Do not treat Marp or HTML like PowerPoint.** If you end up cramming bullets into markdown, you have not broken the default. You have just changed the file extension.
4. **Do not rehearse by reading slides.** Rehearse by speaking the prose. The slides are punctuation, not a prompt.
5. **Do not keep a slide just because it looks good.** If it does not serve the story, cut it. Every time.

## Next Steps

Once you have run this pattern on a real presentation:

- **Claude as a Thought Partner** (easy) — Use thought partner mode before this lab to figure out what you even want to say.
- **TLDR: Explain It Like I'm...** (easy) — Use audience framing to tighten the opening and the key line.
- **Build Your First Skill** (easy) — Turn your favorite narrative-arc prompt from this lab into a reusable "presentation narrative" skill.

## Reference

- [Marp: Markdown Presentation Ecosystem](https://marp.app/)
- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn your favorite prompt into a reusable tool

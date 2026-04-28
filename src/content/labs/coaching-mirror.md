---
title: "Practicing a Coaching Conversation"
difficulty: medium
time: "35 minutes"
tags: ["coaching", "management", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A real coaching situation you are preparing for (1:1 coming up, or a recent one you wish had gone better)"
  - "A willingness to see a transcript of your own coaching style"
  - "A web browser for the visual artifact"
learn:
  - "How to role-play a hard 1:1 with Claude playing your direct report"
  - "How to get a structured critique of your questions, listening ratio, and advice-giving moments"
  - "How to generate an interactive HTML transcript with color-coded annotations"
  - "How to build a reusable skill that analyzes any real 1:1 notes"
docs:
  - "/docs/what-is-a-skill"
  - "/docs/good-prompting"
order: 21
---

## What You Are Building

An interactive HTML transcript of a coaching role-play where Claude played your direct report. Every question is color-coded (green for open, yellow for closed, red for leading). Every advice-giving moment is flagged in the margin. A stats panel shows your listening ratio and question counts. Click any annotation to see what you could have asked instead.

You are not learning to code. You improvise the conversation. Claude plays the report, critiques afterward, and generates the visual transcript.

By the end you will have:

- A full role-play transcript with Claude as your direct report
- An interactive HTML transcript with annotations and stats
- A reusable skill that critiques any real 1:1 notes on the same rubric

> **At work, this comes up when you're...**
>
> - preparing for a 1:1 where someone is struggling and you do not want to just tell them what to do
> - practicing a coaching framework before you try it live
> - noticing your 1:1s drift into status updates when they were supposed to be developmental
> - getting feedback that you "jump to solutions too fast"
> - onboarding into a manager role and needing to build the coaching muscle before stakes go up

## Why This Matters

Managers think they are coaching far more often than they actually are. Most 1:1s labeled "coaching" are a mix of status checking and solution giving. You ask a question, hear enough to form a hypothesis, and then the rest is advice dressed up as dialogue.

You cannot see this in yourself in real time. You can see it in a transcript. And you can almost never convince yourself to ask a coworker to sit in on a real 1:1 to count your questions.

Claude can play the direct report and stay in character. The HTML transcript is the artifact that makes your own pattern visible.

---

## Pick the coaching situation

> **Hint:** _Pick a real one. The exercise is only useful if the person and the stuck point are things you actually carry around._

Choose one:

- A 1:1 coming up with someone who is struggling
- A recent 1:1 that did not go the way you wanted
- A conversation you have been avoiding

Write a few lines of context:

- Who is the person (role, tenure, relationship)
- Their stuck point from their perspective
- Their stuck point from your perspective
- What a great 30-minute outcome looks like

Do not script the conversation. You are going to improvise.

> **You're there when:** you have a real situation and a few lines of context.

---

## Set up the role-play

Paste this:

```
I want to practice a coaching conversation. You will play my direct report. Context:

[paste context]

Rules:
- Stay in character. Be defensive, deflect, or go quiet if it is in character.
- Do not solve the problem for me. Do not offer coaching moves. Just be the report.
- If I ask a bad question, answer the way a real person would answer a bad question (short, surface-level, or pivoting).
- Do not narrate internal thoughts.

I will open. You respond. We run about 10-15 exchanges. When I type "end role-play," drop character and deliver this critique:

1. Question count: open (what/how/tell me), closed (yes/no), leading (answer embedded)
2. Listening ratio: what percent I spoke vs you spoke
3. Advice-giving moments: quote sentences where I stopped coaching and started telling. For each, suggest a question I could have asked instead.
4. The one move that would have changed the conversation most.

Confirm and wait for my opener.
```

> **You're there when:** Claude has confirmed and is waiting for your first line.

---

## Run the role-play

> **Hint:** _Improvise. You are trying to produce the version of you that would show up in the real 1:1._

Open naturally. Let it run. Tips:

- Let silences be silences. Do not fill air.
- Notice the urge to solve. Ask one more question before offering.
- Follow deflections. They often lead somewhere real.
- If the conversation stalls, keep going. A stalled rehearsal is more useful than a smooth one.

Go 10-15 exchanges. Then type `end role-play`.

Claude drops character and delivers the critique.

> **You're there when:** you have the full transcript and the four-part critique.

---

## Read the critique honestly

Look at the numbers. If you asked 12 questions and 9 were closed, you were checking status, not coaching. If you spoke more than 50 percent, you were not really coaching.

Read the advice-giving moments. These are where you jumped to the answer. For each, what were you afraid of in that moment?

Push back if Claude misread:

```
You counted "have you thought about talking to product?" as a coaching question. That was a leading suggestion. Recount.
```

> **You're there when:** you have read the critique, pushed back on anything that felt off, and can name one specific thing to do differently in the real 1:1.

---

## Generate the interactive HTML transcript

Paste this:

```
Build me a single self-contained HTML file called coaching-transcript.html that visualizes the role-play and the critique. Requirements:

- Header: date, role-play topic, final stats (question counts, listening ratio)
- Main panel: the full transcript in a two-column layout (me on one side, direct report on the other). Each of my lines is color-coded: green for open questions, yellow for closed, red for leading, gray for statements. Click any line to see the critique for it.
- Advice-giving moments: highlighted with a margin flag. Click the flag to see the suggested coaching question alternative.
- Stats panel on the right: donut chart for question type breakdown, bar for speaking ratio, count of advice moments
- "The one move" card at the top: the single change that would have shifted the conversation most
- Clean modern styling, calm palette

Use Chart.js via CDN for the charts. Otherwise inline CSS and vanilla JS.
```

Open `coaching-transcript.html`. Click through your lines. See the color patterns.

> **You're there when:** the transcript renders, color-coding is clear, and clicking advice flags shows the alternative question.

---

## Build the Coaching Check skill

Paste this:

```
Build a reusable Claude Code skill called "coaching-check". It should take any 1:1 notes or transcript I paste (full transcripts or rough notes) and produce:

1. Question count (open/closed/leading)
2. Listening ratio
3. Advice-giving moments with coaching-question alternatives
4. The one move

If the notes are too sparse for precise ratios, say so and give qualitative analysis instead.

Generate the HTML transcript file as the final artifact.

Install at ~/.claude/skills/coaching-check/SKILL.md.
```

Now run it on a real past 1:1. Reconstruct from memory if you do not have notes.

> **You're done when:** the skill analyzes a real past 1:1 and catches at least one pattern you recognize.

---

## What You Just Did

You did something most coaching training skips: you watched yourself coach, in your own language, on a real situation.

1. **Role-played** a hard 1:1 improvised not scripted.
2. **Got a count** of your questions, listening ratio, and advice moments.
3. **Visualized** your own pattern as a color-coded transcript.
4. **Built** a reusable skill to run the same analysis on real 1:1s.

## What Not to Do

1. **Do not script the role-play.** Improvise.
2. **Do not let Claude break character to help you.** Tell it to stay in character.
3. **Do not dismiss the critique.** Read it twice.
4. **Do not use the skill to catch other people's bad coaching.** Use it on yourself.
5. **Do not run this once and call it done.** Monthly for the next quarter.

## Next Steps

Once you have run the check on 3-4 real 1:1s:

- **Reviewing Hard Feedback** (medium) — Pressure-test feedback before delivery.
- **Tuning Messages for Stakeholders** (medium) — Tune one message for multiple audiences.
- **Build Your First Skill** (easy) — Foundational skill-building.

## Reference

- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview
- [Good Prompting](/docs/good-prompting) — patterns that work

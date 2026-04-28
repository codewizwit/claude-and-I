---
title: "Decision Journal"
difficulty: easy
time: "20 minutes"
tags: ["decisions", "judgment", "timeline"]
prerequisites:
  - "Claude Code is already open"
  - "One real decision you are making this week (a hire, a spend, a strategy call, a vendor choice)"
  - "10 minutes of honest reflection"
  - "A web browser for the visual artifact"
learn:
  - "How to capture a real decision in 15 minutes with Claude as interviewer"
  - "How to separate what you know from what you are assuming from what you are predicting"
  - "How to generate an interactive HTML decision timeline that tracks entries and revisit dates"
  - "How to turn the pattern into a reusable skill so journaling becomes a 5-minute habit"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 12
---

## What You Are Building

A decision journal entry about a real decision, plus an interactive HTML timeline that tracks every decision you journal from now on. Each entry appears as a card on the timeline with the decision, your prediction, confidence level, and revisit date. When a revisit date arrives, the card lights up. Click it to see your original thinking and grade whether you were right.

You are not learning to code. Claude plays interviewer and scribe. You just think and talk.

By the end you will have:

- A real decision journal entry for a decision you are making this week
- An HTML timeline file that grows as you add future entries
- Calendar reminders on the revisit dates
- A reusable skill that runs the interview in 5-10 minutes

> **At work, this comes up when you're...**
>
> - about to extend an offer and want a record of why this candidate over others
> - approving a meaningful spend and want to capture what you expect it to produce
> - picking between two strategic directions and want to know later which bet was better
> - killing a project and want to remember what signals told you it was time
> - making any call you will second-guess in six months

## Why This Matters

You make dozens of non-trivial decisions every month and remember almost none of them clearly. Ask yourself about a call you made six months ago and you will tell a clean story. That clean story is almost certainly wrong. Memory reconstructs decisions to match how they turned out.

This is why calibrated judgment is rare. Most people do not have a real record to learn from. A decision journal is the fix. It takes 10 minutes per entry and over a year compounds into the single best professional development tool you have.

The HTML timeline is the upgrade that makes the journal sticky. Text entries sit in files you forget. A visual timeline you open monthly shows you patterns in your own decisions.

---

## Pick one real decision

> **Hint:** _Pick a decision not yet finalized. The journal is 10x more useful when it captures real-time thinking, not hindsight._

Good candidates:

- A hire you are about to make or pass on
- A spend that requires a real trade-off
- A strategic fork (A or B, invest now or wait)
- A personnel call (promote, reorg, let go)
- A call to kill or continue an existing initiative

Bad candidates: trivial decisions, or decisions already made (those go in a retrospective).

> **You're there when:** you have one real not-yet-finalized decision you would second-guess in 6 months.

---

## Ask Claude to interview you

> **Hint:** _Do not try to write the journal entry yourself. Let Claude pull it out of you. Answers get sharper under questioning._

Paste this:

```
I want to capture a decision I am making this week. Act as a calm, thoughtful interviewer. Ask me these nine questions one at a time. Wait for my answer before the next. Reflect back what you heard after each so I can correct misreads.

1. What is the decision in one sentence, including the timeframe?
2. What are the realistic options I am choosing between?
3. What do I actually know for sure that is relevant?
4. What am I assuming that I cannot fully verify? Name the assumptions honestly.
5. What outcome am I predicting from the option I am leaning toward? What does success look like? What does failure look like?
6. What would change my mind between now and the decision point?
7. Who am I not consulting who might have a useful view? Why am I not consulting them?
8. What is my confidence level (low, medium, high) and why?
9. When should I revisit to check whether my prediction was right? Pick a real calendar date.

After the interview, write up my answers as a clean, dated decision journal entry. Do not add anything I did not say. Do not polish away uncertainty.
```

Answer all nine. Honestly, not aspirationally.

> **You're there when:** Claude has asked all nine questions and produced a written entry.

---

## Read it like it is 6 months from now

> **Hint:** _The test of a good entry is whether your future self could learn from it. If it reads like a press release, it is not doing its job._

Read the entry. Ask:

- Does it capture what I actually believed, or the official version?
- Are the assumptions named honestly?
- Did I hide behind "we will see"?
- Is the revisit date specific?

If any of those are off, push back:

```
My prediction is too vague. Rewrite it so there is a specific, checkable outcome I could grade myself on.
```

```
The revisit is "Q3." Make it a specific calendar date.
```

> **You're there when:** the entry reads like an honest record, including the uncomfortable parts.

---

## Generate the interactive HTML timeline

> **Hint:** _One entry is a note. A timeline of entries is a learning system._

Paste this:

```
Now build me a single self-contained HTML file called decision-timeline.html that visualizes a decision journal. Requirements:

- Header: "Decision Journal" with my name
- A vertical timeline running down the page with decision cards on alternating sides
- Each decision card shows: title, date, decision summary (one sentence), confidence level (colored pill), predicted outcome (condensed), and revisit date
- Cards for decisions whose revisit date has passed get a yellow "Revisit due" stripe
- Cards for decisions where I have added an outcome grade get a green or red border based on whether I was right
- Clicking any card expands it to show the full 9-question entry plus space to add an "Outcome" and a "What I learned" note
- An "Add new entry" button at the top that opens a blank entry form
- The file is self-contained so entries persist via localStorage (simple JSON)
- Generate the file with the one entry I just wrote as the first card
- Clean modern styling: good typography, generous whitespace, soft palette

Use only inline CSS and vanilla JavaScript.
```

Open `decision-timeline.html` in your browser. You should see your first decision card. Click it. Read the entry. Click "Add new entry" to preview the blank form.

> **You're there when:** the timeline renders, your entry appears as a card, and clicking it shows the full interview.

---

## Set the revisit

> **Hint:** _An entry without a calendar reminder is a note. An entry with a revisit is a learning system._

Add the revisit date you named to your calendar. When the reminder fires:

1. Open `decision-timeline.html`
2. Click the card (it should be highlighted with "Revisit due")
3. Add an outcome and a "What I learned" note
4. The card border turns green (right) or red (wrong)

That loop is how calibrated judgment compounds.

> **You're there when:** the calendar reminder is set.

---

## Save as a skill

Paste this:

```
Turn this into a reusable Claude Code skill called "decision-interview". It should:

- Walk me through the 9-question interview one at a time
- Reflect back after each answer
- Enforce specific predictions and specific revisit dates
- Add the new entry to decision-timeline.html instead of creating a new file each time

Install at ~/.claude/skills/decision-interview/SKILL.md.
```

> **You're done when:** the skill is installed and the timeline has one entry ready for revisit.

---

## What You Just Did

You just built the foundation of calibrated professional judgment:

1. **Captured** a decision with honest separation between facts, assumptions, and predictions.
2. **Delegated** the interview and scribe roles to Claude.
3. **Iterated** on vague predictions until the entry was uncomfortably honest.
4. **Visualized** the entry on a timeline that will grow with every future decision.

One entry is a record. Twelve entries is a mirror. Fifty entries is a training program for your own judgment.

## What Not to Do

1. **Do not journal trivial decisions.** The journal is for decisions you would second-guess in 6 months.
2. **Do not write the official version.** Capture what you actually believe.
3. **Do not skip the revisit date.** An entry without a reminder is a note, not a learning system.
4. **Do not hide assumptions.** The ones you did not want to name are the ones that will bite you.
5. **Do not let Claude give you its opinion.** Claude is interviewer and scribe. The decision is yours.

## Next Steps

When you have two or three entries and the first revisit has fired:

- **Running a Pre-Mortem** (easy) — Pair journals with pre-mortems on major commitments.
- **Meeting Notes to Decision Log** (easy) — Decisions usually happen in meetings. Combine this with meeting logs.
- **Build Your First Skill** (easy) — If you want to sharpen your skill-building muscle.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work

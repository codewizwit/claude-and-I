---
title: "Reviewing Hard Feedback"
difficulty: medium
time: "30 minutes"
tags: ["feedback", "management", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A real piece of feedback you need to deliver this week or next"
  - "A willingness to see your own draft flagged"
  - "A web browser for the visual artifact"
learn:
  - "How to pressure-test hard feedback before delivery using a structured rubric"
  - "How to spot the 3 sentences in any draft that will be heard as attacks"
  - "How to generate an interactive HTML feedback scorecard with inline annotations"
  - "How to pick a better opener when the stakes are high"
docs:
  - "/docs/what-is-a-skill"
  - "/docs/good-prompting"
order: 20
---

## What You Are Building

An interactive HTML feedback scorecard that shows your feedback draft with inline annotations: vague language flagged, emotional leakage underlined, Behavior statements that are really Interpretations marked in the margin. Click any annotation to see Claude's reasoning and the suggested rewrite. At the top, a verdict banner ("Ready to send," "Needs one pass," or "Needs rewrite") and three opener suggestions tuned for different dynamics.

You are not learning to soften feedback. You are learning to make it clearer and cleaner without softening it.

By the end you will have:

- A pressure-tested draft of real feedback you are about to deliver
- An interactive HTML scorecard showing the original and the cleaned version
- A reusable skill that runs the review on any future feedback draft

> **At work, this comes up when you're...**
>
> - preparing a performance conversation and rewriting the same paragraph for the fourth time
> - giving a peer feedback on something that affected your team without damaging the relationship
> - giving upward feedback and feeling the draft get more cautious every time you read it
> - putting something in writing that HR, a skip level, or the person months from now will read
> - noticing you are burying the actual feedback in three paragraphs of cushioning

## Why This Matters

The hardest part of delivering feedback is rarely writing it. It is noticing the two or three sentences that will be heard as attacks even though you did not mean them that way. A friend will not flag those sentences. Claude will.

Feedback that lands is specific, tied to observable behavior, clear about impact, and stripped of emotional leakage (words like "always," "never," "lazy," "defensive," "you should have known"). Most first drafts have at least one of these problems and nobody can see their own.

The HTML scorecard is the upgrade. Inline annotations make the problems visible in the draft itself, not in a text list you skim.

---

## Draft the feedback first, without help

> **Hint:** _Write the draft before you open Claude. You want the skill to review what you actually would have sent, not a version Claude shaped from the start._

Write your feedback. Keep it short, 1-3 paragraphs. Include:

- What happened (situation)
- What the person did (behavior)
- What the impact was
- What you want to change or discuss

Do not polish. Do not hedge. Write the honest version.

> **You're there when:** you have a draft you would send if you had to send something today.

---

## Ask Claude to build the review skill

Paste this:

```
Build a Claude Code skill called "feedback-review" that takes any draft of hard feedback (performance, peer, or upward) and runs four checks:

1. SBI check. Identify Situation, Behavior, Impact. Flag anything mislabeled — especially interpretations presented as behaviors.
2. Vague language. Quote imprecise words or phrases ("attitude," "communication issues," "always," "never," "lately," "a bit of a") and suggest specific replacements.
3. Emotional leakage. Quote sentences where frustration, disappointment, or judgment leaks through in a way the recipient will hear as an attack. Rewrite each while preserving the honest content.
4. Opener suggestions. Give me 3 openers tuned for: (a) likely-defensive recipient, (b) likely-anxious recipient, (c) senior-to-me recipient.

Output also includes a one-line verdict: "Ready to send," "Needs one pass," or "Needs rewrite."

Ask me 3 clarifying questions: what kinds of feedback I give most often, whether I want the tone blunt or gentle, and whether I want a cleaned draft or just the critique. Then install the skill.
```

Answer the questions. "Blunt" is almost always the right answer.

> **You're there when:** the skill is installed.

---

## Run it on your real draft

Paste:

```
/feedback-review Here is a draft I need to deliver this week:

[paste your real draft]

Context: [one line about who this is for and the relationship]
```

Read the review. Brace yourself. A good review flags more than feels comfortable.

Push back if it is being pedantic:

```
"Recently" got flagged as vague but it is tied to a specific meeting I named in the next sentence. Tighten the skill so it only flags vague time words when the surrounding text does not anchor them.
```

If it missed something:

```
"You should have known better" did not get flagged. That is classic emotional leakage. Update the skill so any "you should have" sentence gets flagged by default.
```

> **You're there when:** you have run the review and can name at least one specific change you will make.

---

## Rewrite and run it again

> **Hint:** _The first pass finds the problems. The second pass tells you if you fixed them._

Rewrite the draft based on the review. Reread the whole thing fresh. Run the review again.

Ask the real test: _If this feedback were forwarded to HR, a skip level, or the person six months from now, would I still stand behind every sentence?_

If yes, you are done with the draft.

> **You're there when:** the second pass comes back with "Ready to send" or "Needs one pass" with only minor notes.

---

## Generate the interactive HTML scorecard

Paste this:

```
Now build me a single self-contained HTML file called feedback-scorecard.html visualizing the review. Requirements:

- Header: verdict banner (Ready to send / Needs one pass / Needs rewrite) with color coding
- Main panel: the current draft with inline annotations. Yellow underline for vague language. Orange highlight for emotional leakage. Red margin flags for interpretations mislabeled as behaviors. Each annotation has a tooltip with the reasoning and the suggested fix.
- Side panel: three opener options as cards (defensive, anxious, senior) with one-click copy buttons
- Below the main panel: a "Before/After" view showing both drafts side by side, with resolved annotations struck through in green
- A "Practice delivery" button that reads the final draft aloud using the browser's speech synthesis (so I can hear how it lands)
- Clean modern styling, calm palette

Inline CSS and vanilla JavaScript only.
```

Open `feedback-scorecard.html`. Read annotations. Click the openers to copy. Click "Practice delivery" to hear it aloud.

> **You're there when:** the scorecard renders, annotations have tooltips, and the practice delivery button works.

---

## Test on a different kind of feedback

> **Hint:** _The skill is reusable only if it works for performance, peer, and upward feedback. Test a different category._

Pick a second piece of feedback. Different type (if the first was performance, try upward). Run the skill. Push back if the openers or tone do not fit the dynamic.

```
When I ran an upward feedback draft, the openers treated my manager like a peer. Update the skill so upward feedback openers acknowledge the power difference and invite pushback.
```

> **You're done when:** two different kinds of feedback come out the other side with reviews you would trust a thoughtful colleague to give you.

---

## What You Just Did

You built the habit most managers never build: pressure-testing hard feedback before delivery with a rubric that does not flinch.

1. **Wrote** the honest version first without sanitizing.
2. **Structured** a review rubric (SBI, vague language, emotional leakage, openers) that catches what you cannot see.
3. **Iterated** until the draft was cleaner without being softer.
4. **Visualized** the review as an annotated scorecard with practice delivery.

## What Not to Do

1. **Do not draft inside the skill.** Write first, review second. Otherwise the review inherits Claude's bias.
2. **Do not use the skill to make feedback nicer.** The goal is clearer and cleaner, not softer.
3. **Do not skip the second pass.**
4. **Do not rely on the skill when the feedback is really about the relationship.** Name that to yourself honestly.
5. **Do not send after one round.** Every hard feedback draft deserves at least one review pass.

## Next Steps

When you have run the skill on 3-4 real drafts:

- **Practicing a Coaching Conversation** (medium) — Role-play a hard 1:1 before it happens.
- **Tuning Messages for Stakeholders** (medium) — Tune one message for multiple audiences.
- **Build Your First Skill** (easy) — The foundational lab on skill-building.

## Reference

- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work
- [Good Prompting](/docs/good-prompting) — the patterns that make skill instructions actually work

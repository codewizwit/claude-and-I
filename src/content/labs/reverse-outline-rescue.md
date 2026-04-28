---
title: "Reverse-Outlining a Document"
difficulty: easy
time: "25 minutes"
tags: ["writing", "editing", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A real doc that is rambling, unclear, or not landing"
  - "A web browser for the visual artifact"
learn:
  - "How to reverse-outline a doc to see its actual argument, not its prose"
  - "How to spot structural moves that make a doc confusing"
  - "How to generate an interactive HTML side-by-side view comparing original to rebuilt"
  - "How to turn the pattern into a reusable skill for any doc"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 16
---

## What You Are Building

An interactive HTML side-by-side view of a real doc you are fixing: the original on the left with each paragraph labeled by what it is actually doing, and the rebuilt version on the right showing the new structure. Color-coded labels flag redundancy, paragraphs doing two jobs, and dead paragraphs. Click any label to see the reasoning.

You are not learning to code. You paste the doc, Claude reverse-outlines it, you approve the restructure, and Claude generates the HTML compare view.

By the end you will have:

- A cleaned-up version of a real doc you are working with
- An interactive HTML comparison showing structural changes
- A reusable skill for any future rambling doc

> **At work, this comes up when you're...**
>
> - editing a teammate's memo and knowing it is not landing but unable to say why
> - staring at your own draft after the tenth line edit, still not happy
> - reviewing a proposal or strategy doc that feels thorough but slippery
> - trying to get a long email down to a short one without losing the point
> - giving writing feedback and wanting something more useful than "tighten this up"

## Why This Matters

Most bad docs are not bad because of prose. They are bad because the logic is jumbled. Paragraphs are fine one at a time and confusing in sequence. Line editing cannot fix that.

Reverse outlining strips prose and exposes the skeleton. Once you see the skeleton, the fix is obvious. The HTML side-by-side is the upgrade — you can point at structural changes and make them visible to your team.

---

## Pick a real doc that is not landing

> **Hint:** _Pick something that matters. The point is feeling the difference between before and after on something real._

Good candidates:

- A memo or strategy doc you are drafting that will not land
- A teammate's draft you are reviewing but struggling to give feedback on
- A long email you have rewritten three times
- A recurring doc (monthly report, QBR narrative) that has gotten sloppy

4+ paragraphs. Strip confidential material.

> **You're there when:** you have a real doc ready to paste and can describe what is off in one sentence.

---

## Ask Claude to reverse-outline

Paste this, then paste your doc:

```
Reverse-outline the doc I paste next. For each paragraph, give me one bullet that describes what it is doing, not what it is saying. Think: "setting up the problem," "introducing counter-argument," "giving example that supports point 2."

After the outline, tell me:
- Which paragraphs are doing the same job (redundant)
- Which paragraphs are doing two jobs (should be split)
- Which paragraphs are doing no clear job (should be cut)
- Where the logic is out of order
- What the doc is missing

Be blunt. I am trying to fix this.

[paste doc]
```

Read the outline. Three things usually jump out: paragraphs doing two jobs, paragraphs doing no job, and order problems.

> **You're there when:** you can look at the outline and say "oh, that is the problem" out loud.

---

## Rebuild from the skeleton

Paste:

```
Based on the outline, let's:
- Combine paragraphs [X and Y] since they are making the same point
- Split paragraph [Z] into two
- Move paragraph [N] before [M]
- Cut paragraph [K]

Rewrite the doc with the new structure. Keep my voice and specifics. Do not invent new facts. If something feels missing, flag it but do not fill it in.
```

Compare against the original. Push back on anything that drifted:

```
You cut paragraph [K] but also cut its specific example. Restore that example in paragraph [M].
```

```
The voice flattened. Keep my sentence rhythm and specifics.
```

> **You're there when:** the rewrite reads in half the time and makes the argument more clearly.

---

## Generate the interactive HTML comparison

Paste this:

```
Build me a single self-contained HTML file called outline-compare.html. Requirements:

- Two-column layout: original on left, rewrite on right
- Each paragraph in the original has a colored label above it showing what it is doing (setup, tension, example, transition, restatement, etc.)
- Labels are color-coded: green for structural work (setup, resolution), blue for support (example, evidence), yellow for problem paragraphs (redundant, doing two jobs, doing no job), red for dead paragraphs
- Clicking a label shows the reasoning and what happened to that paragraph in the rewrite
- On the rewrite side: color-coded borders show which paragraphs are new, restructured, combined, or preserved
- A header showing: original paragraph count, rewrite paragraph count, number of redundancies fixed, number of order problems fixed
- Clean modern styling, soft palette

Inline CSS and vanilla JS only.
```

Open `outline-compare.html`. Hover the labels. See the structural story visually.

> **You're there when:** both versions render side by side and you can see the structural changes at a glance.

---

## Save as a skill

Paste this:

```
Turn this into a reusable Claude Code skill called "reverse-outline". It should:

- Take any doc I paste
- Produce the reverse outline
- Flag redundancy, double-duty, dead paragraphs, and order problems
- Propose a restructure
- On approval, produce the rewrite preserving voice and specifics
- Generate outline-compare.html as the artifact

Install at ~/.claude/skills/reverse-outline/SKILL.md.
```

Run it on a second doc cold. If the skill drifts, name what was off.

> **You're done when:** the skill works on a second doc you did not build it with.

---

## What You Just Did

You learned the editing move that separates careful writers from everyone else:

1. **Named the real problem** (structure, not prose).
2. **Saw the skeleton** through reverse-outlining.
3. **Rebuilt from the skeleton** instead of line-editing the original.
4. **Visualized the change** in a side-by-side compare view.
5. **Captured the pattern** as a reusable skill.

## What Not to Do

1. **Do not skip to rewriting.** The outline is the diagnostic.
2. **Do not let Claude describe what paragraphs are saying.** What they are doing.
3. **Do not let the rewrite invent facts.**
4. **Do not generic-ify the voice.** Blunt original stays blunt.
5. **Do not use this on short messages.** 4+ paragraphs minimum.

## Next Steps

Once you have the skill in your toolkit:

- **Building a Voice Guide** (medium) — Pair voice with structure so rewrites preserve both.
- **Recurring Weekly Updates** (easy) — An update skill that calls reverse-outline when drafts get tangled.
- **Build Your First Skill** (easy) — Foundational skill-building.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview

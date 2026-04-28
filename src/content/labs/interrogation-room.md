---
title: "Critiquing Claude's Drafts"
difficulty: easy
time: "25 minutes"
tags: ["review", "quality", "html"]
prerequisites:
  - "Claude Code is already open"
  - "One recent Claude-generated draft (memo, email, summary, plan) or the ability to generate one in 2 minutes"
  - "A web browser for the visual artifact"
learn:
  - "How to stress-test a Claude draft instead of accepting it at face value"
  - "How to use role-based pushback to expose weak spots fast"
  - "How to generate an interactive HTML critique report with annotated drafts"
  - "How to build a reusable checklist you can run on any future output"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 9
---

## What You Are Building

An interactive HTML critique report that shows a Claude draft with color-coded annotations: weak claims highlighted yellow, unsupported assumptions underlined, vague language flagged in the margin. Click any annotation to see the critique reasoning. Switch between three reviewer personas (hostile reviewer, skeptical board member, red team) to see different kinds of pushback on the same draft.

You are not learning to write better. You are learning to review better. Most people read a Claude draft, nod, and ship it. You are building the muscle that separates "looks fine" from "actually holds up."

By the end you will have:

- A Claude draft you interrogated from B+ to A
- An interactive HTML critique report showing the draft with inline annotations
- A reusable "interrogation" skill you can run on any future output

> **At work, this comes up when you're...**
>
> - reviewing anything Claude drafted before you put your name on it
> - quality-gating an important output (board update, plan for your director, wide communication)
> - trying to break the habit of accepting first drafts because they read nicely
> - preparing a document that has to survive pushback from someone skeptical
> - mentoring someone new to Claude who trusts output too quickly

## Why This Matters

The quality of Claude's output is capped by the quality of your pushback. "Looks good" is the enemy. A polished B+ draft hides its own weak spots, and if you do not look for them on purpose, you will ship them.

Structured interrogation surfaces what the draft is quietly assuming, skipping, or softening. Two rounds of honest pressure usually take a B+ to an A. No extra research. Just better questions aimed at what is already on the page.

The HTML critique report is the upgrade. Inline annotations make the weak spots visible in the draft itself. You can scan a document and see the problems.

---

## Pick a draft with stakes

> **Hint:** _Do not pick something trivial. Pick something where "looks good" would cost you if it was wrong._

Open something Claude recently drafted, or ask Claude to draft one of these:

- A memo or update going to a director or executive
- A plan or proposal you would present in a meeting
- A recommendation ("should we do X or Y")
- An external email where tone and accuracy matter

> **You're there when:** you have one real draft open and you can say in one sentence why it matters that it is right.

---

## Read and name your gut reaction

> **Hint:** _Your gut is data. Do not skip this step just because it feels soft._

Read the draft slowly once. Write down:

1. Letter grade (A, B+, B, C)
2. Your least-certain sentence
3. The strongest part of the draft
4. Where your boss would push first

Most Claude drafts land around B+. They read smoothly and feel done. They are rarely done.

> **You're there when:** you have written your gut grade and your weakest sentence.

---

## Run three interrogations

> **Hint:** _Role-playing is not a gimmick. A persona forces a specific kind of critique you would not get otherwise._

**Round 1: Hostile reviewer.** Paste:

```
Act as a hostile but fair reviewer of the draft above. You do not trust it. List the 5 weakest points and why each one is weak. No fixes yet.
```

**Round 2: Skeptical board member.** Paste:

```
Now act as a skeptical board member reading this in a meeting. You have 90 seconds. What are the 3 questions you would ask out loud that this draft does not answer?
```

**Round 3: Red team.** Paste:

```
Now act as a red team. Argue the opposite position as persuasively as possible. Where does the draft's argument break?
```

Each role applies different pressure. Do all three.

> **You're there when:** you have three distinct critiques and you can pick out the 3 issues genuinely worth fixing.

---

## Rewrite once, targeted

> **Hint:** _Do not ask Claude to "address all the feedback." That produces mush. Pick the 3 real issues and fix those directly._

Paste:

```
Rewrite the draft to fix exactly these 3 issues:

1. [issue one in your own words]
2. [issue two]
3. [issue three]

Keep everything else the same. Do not rewrite for style. Do not add new sections. Only address these three problems.
```

Compare against your gut notes. Has the weak sentence been fixed? Has the board member's question been answered?

> **You're there when:** the rewritten draft answers the pushback and you can point to what changed and why.

---

## Generate the interactive HTML critique report

Paste this:

```
Now build me a single self-contained HTML file called critique-report.html that visualizes the interrogation. Requirements:

- Header: title of the draft, date, my gut grade, final grade
- Main panel: the current draft text with inline annotations. Underline unsupported assumptions in yellow. Highlight weak claims in orange. Flag vague language with a margin note. Each annotation has a tooltip with the reviewer's reasoning.
- Side panel: three tabs for the reviewer roles (Hostile Reviewer, Skeptical Board Member, Red Team). Clicking a tab loads that reviewer's critique list.
- "Before/After" toggle at the top: switch between the B+ draft and the A draft with annotations still attached so I can see which ones got resolved (resolved annotations shown struck through in green).
- "Print critique" button for sharing
- Clean modern styling: good typography, soft colors, readable even at a glance

Use only inline CSS and vanilla JavaScript.
```

Open `critique-report.html`. Toggle between before/after. Hover annotations. Click tabs to read each reviewer's take.

> **You're there when:** the report renders, annotations have tooltips, and the before/after toggle shows resolved issues.

---

## Save as a skill

Paste this:

```
Turn this into a reusable Claude Code skill called "interrogate". It should:

- Take any Claude draft
- Run three reviewer passes (hostile, board member, red team)
- Let me triage and name the 3 real issues
- Produce a targeted rewrite
- Generate critique-report.html with annotations

Install at ~/.claude/skills/interrogate/SKILL.md.
```

> **You're done when:** the skill is installed and the report is saved.

---

## What You Just Did

You did the four moves that separate shippers of average work from shippers of sharp work:

1. **Named your gut reaction** before letting Claude influence you.
2. **Pressured the draft** from three angles to surface different weaknesses.
3. **Triaged the feedback** and fixed only what mattered.
4. **Visualized the critique** as an annotated report you can share.

## What Not to Do

1. **Do not skip the gut-reaction step.** Your own read sets the baseline.
2. **Do not run all three reviewer roles in one prompt.** Each role gets a cleaner answer alone.
3. **Do not fix every issue.** Triage. Some critiques are noise.
4. **Do not rewrite from scratch.** Targeted fixes only.
5. **Do not trust the skill after one run.** Test on a second draft first.

## Next Steps

Once you have run the skill on a handful of drafts:

- **Interactive Data Dashboards** (easy) — Apply the same "how did you compute this" instinct to charts.
- **Build Your First Skill** (easy) — Build a skill for a task you do weekly.
- **Build a Custom Agent** (medium) — Package interrogation with other review skills into a specialist reviewer agent.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work

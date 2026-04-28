---
title: "Recurring Weekly Updates"
difficulty: easy
time: "25 minutes"
tags: ["writing", "updates", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A weekly or recurring update you are already responsible for sending"
  - "A rough idea of who reads it and what they care about"
  - "A web browser for the visual artifact"
learn:
  - "How to separate the format of a recurring update from the content, so you only write the content"
  - "How to tune the update to the specific audience who reads it"
  - "How to generate an interactive HTML weekly dashboard that tracks your updates over time"
  - "How to keep your update consistent week over week so readers scan fast"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 15
---

## What You Are Building

A weekly update skill tuned to your specific audience, plus an interactive HTML dashboard that archives every update you send and shows trends over time. Each update is a card on the dashboard with the week, the wins, the blockers, and the asks. Hover over the trend chart to see which weeks had which risks. Click a card to open the full update.

You are not learning to code. You describe the audience, Claude builds the skill and generates this week's update, and the HTML dashboard grows every time you run the skill.

By the end you will have:

- A weekly update skill installed and tuned to your audience
- This week's actual update drafted and ready to send
- An HTML dashboard file that archives updates with trend visualization
- A 10-minute Friday workflow instead of a 45-minute one

> **At work, this comes up when you're...**
>
> - writing Monday kickoffs or Friday wrap-ups every week
> - sending a recurring update to your boss, skip-level, or board
> - running a program with partners who need steady visibility
> - trying to stay "on the radar" without writing novels nobody reads
> - inheriting an update cadence and wanting to make it faster without losing signal

## Why This Matters

Weekly updates are 80 percent format. The sections, the section order, the tone, the length. Once the format is nailed, each week is just facts. That is a 10-minute job, not 45.

The dashboard is the upgrade. Text updates disappear into Slack scrollback. A visual archive with trends shows patterns: "we have had three weeks of the same blocker" or "asks have been ignored two weeks in a row." That pattern visibility is what makes the updates actually change things.

---

## Name who reads it

> **Hint:** _The reader is not you. Write for them._

Answer three questions:

1. Who is the primary reader? Name a role or person.
2. What do they actually care about? Honest, not aspirational.
3. What do they not want? Every update has a section included out of habit that nobody reads.

> **You're there when:** you can describe the reader, what they care about, and what they do not care about.

---

## Build the skill with Claude

Paste this:

```
I want to build a weekly update skill. Context:

- Reader: [who]
- They care about: [what]
- They do not care about: [what to leave out]
- Length: [short/medium/long or word count]
- Cadence: [weekly, biweekly, Fridays, etc.]

Ask me 4-6 clarifying questions one at a time about sections, tone, and what "good" looks like. Then draft the skill, explain each section, and install it.
```

Answer honestly. Claude will surface decisions like: TL;DR at the top or straight into sections? Numbers explicit or referenced? When at risk, default to honest or diplomatic? Include a "what I need from you" section?

> **You're there when:** the skill is installed.

---

## Generate this week's update

Paste:

```
/weekly-update Here is this week:

[brain dump: what you did, decided, shipped, fumbled, learned. Bullets are fine. Typos are fine.]

[Any risks or blockers, even awkward ones]

[Anything you need from your reader]

[Top 2-3 priorities for next week]
```

Read the output. Does the TL;DR capture the headline or is it generic? Are progress bullets specific? Are risks honest or softened?

Push back:

```
The TL;DR is vague. Make it name the single most important thing that happened.
```

```
You invented a risk I did not mention. Tighten the skill so it only surfaces things I named.
```

```
The progress section lost my numbers. Preserve numbers word-for-word.
```

> **You're there when:** you have a draft you would send with at most a one-minute edit.

---

## Generate the interactive HTML dashboard

Paste this:

```
Build me a single self-contained HTML file called weekly-dashboard.html that archives my weekly updates. Requirements:

- Header: my name and update title
- A chronological grid of update cards, most recent at top
- Each card: week-of date, TL;DR as the title, 3-5 progress bullets, a risks pill count, an asks pill count
- Clicking a card expands the full update
- A "Trends" panel at the top showing:
  - Bar chart: asks made vs asks answered over weeks
  - Line chart: blocker count per week
  - Tag cloud: most-mentioned topics over the last 8 weeks
- Seed the file with this week's update as the first card. Leave room for more.
- Store future entries in localStorage so I can add updates and the archive grows
- Clean modern styling, soft palette

Use Chart.js via CDN. Otherwise inline CSS and vanilla JS.
```

Open `weekly-dashboard.html`. Click this week's card. Next Friday, add the next update through the skill and the card appears on the dashboard.

> **You're there when:** the dashboard renders, this week's update is the first card, and the trends panel shows at least placeholder charts.

---

## Stress test on three different kinds of weeks

> **Hint:** _One good update is a coincidence. Three in a row is a skill._

Simulate or wait through:

1. A busy week with lots of progress and a blocker or two.
2. A light week where not much moved. (This is where skills break. They invent progress.)
3. A messy week where something went sideways and you need to be honest.

If the skill drifts:

```
On the light week, it still produced 5 progress bullets when I gave it 2. Respect the actual input. Do not pad.
```

```
On the messy week it used "challenge" and "opportunity" to describe a failure. Name failures as failures.
```

Ask: _Would I trust this on a week I am too tired to babysit?_

> **You're done when:** three different kinds of weeks pass the "too tired to babysit" test.

---

## What You Just Did

You moved a 45-minute weekly task down to 10 minutes without losing quality:

1. **Named the audience** and what they actually care about.
2. **Designed the format once** instead of reinventing every Friday.
3. **Separated format from content** so the weekly lift is only facts.
4. **Visualized your updates over time** so patterns become visible.
5. **Stress-tested** across real kinds of weeks.

## What Not to Do

1. **Do not design for a generic "leader" audience.** Pick one primary reader.
2. **Do not include every section you have ever used.** 4-6 sections max.
3. **Do not let Claude invent progress.** Test for it.
4. **Do not skip the light-week test.**
5. **Do not polish inputs before pasting.** Brain dump is the point.

## Next Steps

Once your update is on rails:

- **Building a Voice Guide** (medium) — Build a voice skill that the weekly update calls automatically.
- **Reverse-Outlining a Document** (easy) — Audit longer docs before you send them.
- **Build Your First Skill** (easy) — Foundational skill-building.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview

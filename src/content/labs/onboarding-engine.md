---
title: "Build a 30/60/90 Onboarding Plan"
difficulty: medium
time: "30 minutes"
tags: ["onboarding", "management", "visualization"]
prerequisites:
  - "Claude Code is already open"
  - "A real or hypothetical new hire in mind (name, role, rough background)"
  - "Basic context about the team they are joining"
  - "A web browser for the visual artifact"
learn:
  - "How to translate role, team context, and a specific human into a concrete onboarding plan"
  - "How to build a week-by-week 30/60/90 that someone would actually follow"
  - "How to generate an interactive HTML timeline with milestones, meetings, and a reading list"
  - "How to save the whole approach as a reusable skill for every future hire"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 6
---

## What You Are Building

A real 30/60/90 onboarding plan for a specific new hire, plus an interactive HTML timeline the hire can actually use on day one. The timeline shows week-by-week milestones, a first-week meeting schedule, a recommended reading list with links, and 30/60/90 checkpoints. Click a week to expand it. Click a checkpoint to see what "ramped and contributing" looks like.

You are not learning to code. You describe the person, role, and team moment. Claude interviews you, drafts the plan, and generates the HTML timeline.

By the end you will have:

- A complete 30/60/90 plan specific to one real hire
- An interactive HTML timeline file the hire can open on day one
- A reusable skill that generates a full plan in under 20 minutes for every future hire

> **At work, this comes up when you're...**
>
> - welcoming someone new who starts in the next 30 days and you have not written anything yet
> - rebooting a hire who stalled because they never got a clear picture of success
> - inheriting a team and wanting your first few hires to ramp faster than you did
> - realizing the generic onboarding doc HR sent has not been opened by anyone in two years

## Why This Matters

Onboarding plans usually exist as generic documents nobody reads. A real new hire is a specific person joining at a specific moment, inheriting specific work. When you feed Claude the human, the team, and the moment, you get a plan that answers the real questions: what do I work on first, who do I meet, what do I read, what does week four look like if this is going well.

The HTML timeline is the upgrade. Text plans get skimmed once and forgotten. A clickable timeline with weeks, meetings, and checkpoints is something the hire opens every Monday.

---

## Gather the facts before you open Claude

> **Hint:** _A generic plan for a generic hire is the whole problem. Rough notes on a real person beat a polished template every time._

Take 5 minutes. Write down three things:

**1. The person.** Name, background, why you hired them, what they are strong at, what is new for them.

**2. The role.** What they actually own. Who they report to. Who they partner with. Where they sit on the team.

**3. The moment.** What is going on with the team right now. Any projects in flight they will inherit? Any deadline looming?

> **You're there when:** you have three short paragraphs covering the person, the role, and the moment.

---

## Let Claude interview you

> **Hint:** _Do not hand over everything you know up front. Let Claude's questions pull out the specifics that shape a real plan._

Paste this:

```
I need to build a 30/60/90 onboarding plan for a new hire. Before you draft anything, interview me. One question at a time. Cover:

- The person (background, strengths, what is new for them)
- The role (what they own, partners, what good looks like)
- The team (mission now, projects in flight, the moment)
- The first week (what meetings happen, what waits, what to read day one vs week three)

When you have enough context that the plan would feel specific and not generic, tell me you are ready to draft.
```

Answer each question specifically. If Claude asks "what does this person struggle with?" do not say "nothing." Say the real thing.

> **You're there when:** Claude tells you it has enough context to draft.

---

## Draft the 30/60/90

Paste this:

```
Now draft the 30/60/90 plan with this structure:

- Week-by-week milestones for the first four weeks (week 1, week 2, week 3, week 4)
- 30-day checkpoint: what they can do, who they know, what they have shipped
- 60-day checkpoint: the same categories, scaled up
- 90-day checkpoint: what "ramped and contributing independently" looks like for this specific role
- Recommended reading list: 3-5 items with a one-sentence reason per item
- First-week meeting schedule: suggested day and duration. Do not overload day one. Spread intros.

Keep the voice direct. Write it as if I am handing it to the hire on day one.
```

Read what you get. Push back on anything generic:

```
"Review relevant documentation" is too vague. Replace it with the three specific docs this person should read in week one and one sentence for each on why.
```

```
The first-week schedule has five meetings on day one. Spread them out. Day one should have their manager, one teammate, and nothing else heavy.
```

> **You're there when:** every line in the plan is specific enough that it could not apply to a different hire on a different team.

---

## Stress-test the plan

> **Hint:** _A plan that only works in the happy path is not a plan. Pressure-test before you hand it over._

Paste this:

```
Stress-test the plan. Walk through three scenarios and tell me where it breaks:

1. The hire's first major project gets delayed 2 weeks because of a dependency outside our control. What shifts?
2. The hire is ahead of schedule at day 30. They are bored. What do you add?
3. The hire is behind at day 30, not from lack of effort, just needs more ramp time. What do you cut? How do you reset expectations without making them feel like they are failing?
```

Integrate the useful adjustments. Usually the behind-schedule scenario reveals a milestone that was too aggressive.

> **You're there when:** the plan has an adjustment path written in for at least the behind-schedule scenario.

---

## Generate the interactive HTML timeline

> **Hint:** _The timeline is what turns the plan from a doc into something the hire uses every week._

Paste this:

```
Now build me a single self-contained HTML file called onboarding-timeline.html that visualizes this plan. Requirements:

- Header: hire's name, start date, role
- A horizontal timeline with 4 week markers, then 30/60/90 day milestones
- Each week is an expandable card. Clicking it shows: week goal, specific tasks, people to meet, things to read, and what success looks like at end of that week
- The 30/60/90 markers are larger and visually distinct. Clicking each shows the full checkpoint with what they can do, who they know, what they have shipped
- A "First week schedule" section with a clean day-by-day grid (Monday through Friday, with meetings slotted in)
- A "Reading list" section with 3-5 items, each with a link placeholder and a one-sentence reason
- A "Flex plan" sidebar showing the three adjustment scenarios (ahead, behind, project delayed)
- Clean modern styling: good typography, generous whitespace, soft colors. Friendly, not corporate.

Use only inline CSS and vanilla JavaScript. Inline everything so the file is standalone.
```

Open `onboarding-timeline.html` in your browser. Click through the weeks. Click the 30/60/90 markers. This is what the hire sees on day one.

> **You're there when:** the timeline renders, weeks expand on click, and the first-week schedule is legible.

---

## Save the pattern as a skill

Paste this:

```
Turn this whole sequence into a reusable Claude Code skill called "new-hire-plan". It should:

- Interview me one question at a time about the person, role, and team moment
- Wait until context is specific before drafting
- Produce a 30/60/90 with week-by-week milestones
- Include a first-week meeting schedule that protects day one
- Include a 3-5 item reading list with one-sentence reasons
- Include the three stress-test scenarios
- Generate the onboarding-timeline.html file as the final artifact
- Refuse to use generic phrases like "meet with key stakeholders" or "review relevant documentation" without specifics

Install at ~/.claude/skills/new-hire-plan/SKILL.md.
```

Every future hire now starts with this same pattern.

> **You're done when:** the skill is installed and the HTML timeline renders.

---

## What You Just Did

You did four things that separate a real onboarding plan from a generic doc:

1. **Grounded** the plan in a specific person, role, and moment.
2. **Built** a week-by-week ramp where day one, week two, and month two feel different.
3. **Stress-tested** against common derailments so the plan has adjustment paths.
4. **Visualized** the plan as an interactive timeline the hire opens every Monday.

## What Not to Do

1. **Do not start from a generic template.** The whole point is to ground the plan in this person.
2. **Do not skip the interview step.** Dump everything at once and the plan flattens.
3. **Do not overload day one.** Seven meetings is hazing, not a welcome.
4. **Do not write "review relevant documentation" anywhere.** Replace with the three specific docs and why.
5. **Do not skip saving the skill.** The value doubles when the next hire's plan takes 15 minutes instead of 3 hours.

## Next Steps

Once you have used the skill on a second real hire:

- **Rewriting a Job Description** (easy) — If the role was hired against a vague posting, rebuild the JD.
- **Build Your First Skill** (easy) — The foundational pattern if you skipped it.
- **Build a Lab** (medium) — Capture a workflow you do well and turn it into a shareable lab.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work

---
title: "Meeting Notes to Decision Log"
difficulty: easy
time: "20 minutes"
tags: ["meetings", "decisions", "visualization"]
prerequisites:
  - "Claude Code is already open"
  - "A real meeting you attended recently that ended in ambiguity"
  - "Whatever you have from that meeting: a transcript, scribbled notes, a Slack thread, or a few bullet points"
  - "A web browser for the visual artifact"
learn:
  - "How to turn messy meeting material into a structured decision log in under 10 minutes"
  - "How to ask Claude to extract Decisions, Open Questions, Owners, Risks, and Follow-ups"
  - "How to generate an interactive HTML decision log that filters by owner, status, and priority"
  - "How to push back when Claude invents decisions that were not actually made"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 10
---

## What You Are Building

An interactive HTML decision log from a real meeting. Every decision, open question, owner, risk, and follow-up appears as a filterable card. You can filter by owner ("show me what is on my plate"), by status ("which questions are still unresolved"), and by priority. Send the link to anyone who was or was not in the room.

You are not learning to code. You paste your meeting material, Claude structures it, and Claude generates the HTML log.

By the end you will have:

- A clean decision log from a real recent meeting
- An interactive HTML file that filters and sorts the log
- A reusable skill you can run on any meeting transcript in the future

> **At work, this comes up when you're...**
>
> - leaving a meeting that had no notetaker and realizing nobody knows what was decided
> - catching up after missing a session and trying to figure out what you owe
> - staring at a Zoom transcript that is technically complete but totally unusable
> - sending a recap to stakeholders who were not in the room
> - tired of meeting notes that turn into nothing

## Why This Matters

Meetings are where decisions get made, risks get raised, and commitments get handed out. When the record is fuzzy, every one of those leaks. Decisions get relitigated. Risks get forgotten. Commitments quietly disappear.

A 3-minute Claude pass turns 60 minutes of chaos into a decision log that closes loops. The HTML version is the upgrade: instead of a document people skim once, it becomes a shareable artifact that filters itself to each reader's needs.

---

## Pick one meeting

> **Hint:** _Pick the worst one from the last two weeks. The messier the input, the more obvious the value of the output._

Grab real material:

- A full transcript from Zoom, Teams, or Otter
- A block of notes you typed or scribbled
- A Slack thread where the conversation happened
- Bullet points you never turned into anything

Do not clean it up before you paste it. Claude handles the mess.

> **You're there when:** you have a block of raw meeting material ready to paste.

---

## Ask Claude to structure it

> **Hint:** _Structure is what turns noise into a document people can act on. Ask for five specific sections._

Paste this, then paste your material:

```
Run a "meeting autopsy" on this material. Produce a structured debrief with five categories:

1. Decisions Made — things actually settled, with just enough context for someone not in the room
2. Open Questions — raised but unresolved, with who should resolve each
3. Owners and Commitments — who committed to what, with due date if mentioned (format: "Name owns X, due Y")
4. Risks and Concerns — anything that could derail the work, even if brushed past
5. Follow-ups — 3-5 specific next steps for the next 48 hours

Rules:
- Do not invent decisions that were not actually made
- Flag anything uncertain with "UNCLEAR:"
- If a section has nothing, write "None identified"
- For each item, also tag a priority (high, medium, low) and a status (done, in-progress, blocked, not-started)

Here is the material:
[paste your raw meeting material]
```

Claude will return a structured log.

> **You're there when:** you have all five categories filled in with items tagged by priority and status.

---

## Push back on anything Claude made up

> **Hint:** _If Claude promotes "we discussed" into "we decided," push back every time. The integrity of the log depends on it._

Read Claude's output. Examples of useful push-back:

```
You listed "move the launch to Q3" as a decision. Nobody actually decided that. It was floated and the group said "let's think about it." Move it to Open Questions.
```

```
The Owners section is vague. Give me each commitment in the format "Name owns X, due Y." If no due date was mentioned, say "no date mentioned" so I know to ask.
```

```
You missed the concern about the vendor contract. Re-read the section near the end.
```

Keep going until the log reads like something you would send to a stakeholder.

> **You're there when:** the log accurately reflects what actually happened, with no invented decisions.

---

## Generate the interactive HTML decision log

> **Hint:** _The log in text is useful. The log in HTML with filters is shareable._

Paste this:

```
Now build me a single self-contained HTML file called decision-log.html that visualizes the log as an interactive dashboard. Requirements:

- Header: meeting name (I will tell you), date, and attendees if known
- Top row of filters: filter by owner (dropdown), filter by status (pill buttons), filter by priority (pill buttons)
- Below filters: a grid of cards, one per item. Each card shows:
  - Category badge (Decision, Open Question, Commitment, Risk, Follow-up)
  - One-sentence summary
  - Owner (if any)
  - Due date (if any)
  - Priority indicator (colored dot)
  - Status pill (done, in-progress, blocked, not-started)
- Clicking a card expands it to show the full context
- Cards flagged "UNCLEAR:" have a yellow warning stripe on the left
- Bottom section: a "What to send" button that generates a plain-text email summary of high-priority unresolved items for a specific owner (picked from a dropdown)
- Clean modern styling: good typography, generous whitespace, soft colors

Use only inline CSS and vanilla JavaScript. Meeting name for the header: [paste the name].
```

Open `decision-log.html` in your browser. Click through the filters. "Show me what is on Sarah's plate." "Show me unresolved risks." Click a card to expand.

> **You're there when:** the log renders, filters work, and you can click an owner filter to see only their commitments.

---

## Run it on a different meeting

> **Hint:** _One good log is a coincidence. Two in a row is a working skill._

Find a second meeting. Different topic, different mess. Paste it in. Ask for the decision log. Regenerate the HTML.

If the quality drops, name what drifted:

```
The owners section lost its format on this run. Update the skill so it always uses "Name owns X, due Y" even when the source material is sloppy.
```

Ask the real test: _would I trust a teammate to run this on their own meetings without me standing next to them?_

> **You're done when:** two different meetings both produce decision logs you would send without heavy editing, and you have a reusable skill installed.

---

## Save the pattern as a skill

Paste this:

```
Turn the pattern we just used into a reusable Claude Code skill called "meeting-autopsy". It should:

- Take any meeting material (transcript, notes, Slack thread)
- Produce the 5-category structured log
- Never invent decisions
- Flag uncertainties with UNCLEAR:
- Tag each item with priority and status
- Generate the decision-log.html file as the final artifact

Install it at ~/.claude/skills/meeting-autopsy/SKILL.md.
```

Now any meeting in the future is one `/meeting-autopsy` away from a shareable decision log.

> **You're there when:** the skill is installed at `~/.claude/skills/meeting-autopsy/SKILL.md`.

---

## What You Just Did

You just turned something that usually rots (the messy aftermath of a meeting) into a shareable 10-minute deliverable:

1. **Decomposed** a fuzzy task into five concrete categories.
2. **Delegated** the extraction to Claude with a prompt that enforced structure and honesty.
3. **Iterated** in plain English when the output was off.
4. **Visualized** the log as an interactive HTML dashboard with filters and status tracking.
5. **Captured** the pattern as a skill so every future meeting benefits.

## What Not to Do

1. **Do not clean up the input before pasting.** The point is Claude handles the mess.
2. **Do not accept invented decisions.** Push back every time.
3. **Do not skip the UNCLEAR flag.** The flags are your action items.
4. **Do not stop after one meeting.** Two different meetings is the minimum bar.
5. **Do not send the raw output without scanning it.** Your eyes are the last filter.

## Next Steps

When you have run this on a few real meetings:

- **Running a Pre-Mortem** (easy) — Apply the same instinct to risk surfacing before commitments.
- **Decision Journal** (easy) — Capture the decisions that came out of the meeting in a format your future self can learn from.
- **Build Your First Skill** (easy) — If you skipped it, the foundational pattern for any skill.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work

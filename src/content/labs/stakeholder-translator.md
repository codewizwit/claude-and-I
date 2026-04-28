---
title: "Tuning Messages for Stakeholders"
difficulty: medium
time: "30 minutes"
tags: ["stakeholders", "communication", "html"]
prerequisites:
  - "Claude Code is already open"
  - "One real message you need to send this week"
  - "A rough sense of 4-6 stakeholders you talk to regularly"
  - "A web browser for the visual artifact"
learn:
  - "How to take one message and produce versions tuned for different stakeholders without changing the facts"
  - "How to capture what a stakeholder fears and values so Claude can speak to it"
  - "How to generate an interactive HTML stakeholder viewer that switches framing with one click"
  - "How to reuse the stakeholder map on every message you send"
docs:
  - "/docs/what-is-a-skill"
  - "/docs/good-prompting"
order: 19
---

## What You Are Building

An interactive HTML stakeholder viewer for a real message. One source message, multiple stakeholder-tuned versions, switchable with a single click. Pick your boss, your CFO, your skeptical peer, your anxious client, or your board chair, and the same message reshapes itself for that reader. Same facts. Different emphasis, different opening, different tone.

You are not learning to code. You build a stakeholder map once with Claude, and the viewer becomes reusable for every message you send from now on.

By the end you will have:

- A reusable stakeholder map with 4-6 of your recurring stakeholders
- An interactive HTML file showing today's message tuned for each one
- A reusable skill you can invoke on any future message

> **At work, this comes up when you're...**
>
> - sending the same update to your boss, your team, and your client and wondering why one is upset
> - announcing a change (reorg, policy, budget cut) and needing it to land with five audiences
> - asking for buy-in from someone skeptical while keeping your sponsor energized
> - managing up to a board while managing down to a team that needs a different story
> - noticing your "one size fits all" message keeps getting misread by at least one reader

## Why This Matters

The facts of a message rarely change. What changes is what each listener is scanning for. A CFO listens for risk and cost. A skeptical peer listens for whether you are stepping on their turf. An anxious client listens for whether they are still safe. A board chair listens for whether the org is in control. A new hire listens for whether this is a place that tells the truth.

Most people write one version and hope. The same paragraph that reassures your board will panic your new hire. The same paragraph that energizes your team will read as political to your peer.

The HTML viewer is the upgrade. Instead of four separate drafts, you get one shareable file where a click swaps the framing. Perfect for pre-send review and for showing teammates "here is how this lands for each audience."

---

## Pick the message

> **Hint:** _Use a real message. Rough is fine._

Good candidates:

- An update on a project that is slipping
- An announcement about a change in direction, budget, or team
- A request for resources, approval, or a decision
- A recap of something that went wrong

> **You're there when:** you have one real draft ready to paste.

---

## List your recurring stakeholders

> **Hint:** _Use roles or archetypes so the map is reusable. "My boss." "The CFO." "The skeptical peer." Not one-off names._

Jot down 4-6 stakeholders. For each, write one sentence on what they fear and one on what they value:

- My boss (fears surprises, values the headline in the first line)
- The CFO (fears cost overruns, values numbers and timeframes)
- A skeptical peer (fears scope creep, values clear boundaries)
- An anxious client (fears being burned again, values stability)
- The board chair (fears the story being unclear, values coherence)
- A new hire (fears being lost, values clarity about what to do)

> **You're there when:** you have 4-6 stakeholders with rough fears and values.

---

## Build the stakeholder map skill

Paste this:

```
Build a Claude Code skill called "stakeholder-map" that stores 4-6 of my recurring stakeholders with their priorities, fears, preferred tone, and what not to say.

Interview me one stakeholder at a time. For each, ask about their role, fears, values, preferred tone (formal/casual, bullets/narrative, short/long), and what to avoid. Summarize what you captured before the next stakeholder.

When all stakeholders are done, install the skill. Save the stakeholder data in the skill file so the skill can reshape any message I paste later.
```

Answer Claude's questions. Refine as you go.

> **You're there when:** the skill is installed with 4-6 stakeholder profiles that ring true.

---

## Tune today's message for 3 stakeholders

Paste this:

```
/stakeholder-map Here is a draft I need to send:

[paste your real draft]

Give me three versions tuned for:
1. My boss
2. The CFO
3. The skeptical peer

Keep every fact identical. Only change emphasis, ordering, tone, and what gets said first. After the three versions, tell me in one line what the biggest difference was.
```

Read all three side by side. Push back if anything is off:

```
The CFO version still opens with context. Rewrite so the first sentence contains the cost, the timeframe, and the ask.
```

If a correction applies generally, ask Claude to update the stored profile:

```
Update the CFO profile in the skill so future drafts always open with cost, timeframe, and ask.
```

> **You're there when:** you have three versions with identical facts and clearly different framing.

---

## Generate the interactive HTML viewer

Paste this:

```
Build me a single self-contained HTML file called stakeholder-viewer.html that shows the tuned messages. Requirements:

- Header: source message title and date
- Row of stakeholder pill buttons. Click one to load that version below.
- Above each loaded version: a small card showing the stakeholder's profile (who they are, what they fear, what they value, preferred tone)
- Below: the tuned message with appropriate formatting
- A "Compare" toggle that shows two versions side by side
- A "Copy this version" button for each
- Clean modern styling: good typography, generous whitespace, soft palette

Inline CSS and vanilla JavaScript only.
```

Open `stakeholder-viewer.html`. Click through the pills. Hit compare to see two side by side.

> **You're there when:** the viewer renders and clicking stakeholder pills swaps the version instantly.

---

## Stress test on a second message

Pick a different message type (if the first was an update, try an ask). Run it through the skill. Regenerate the viewer.

Ask: _If I handed this skill to someone on my team, would they get useful drafts without me coaching them through what "my boss" means?_

> **You're done when:** two different message types both come out retuned in ways you would actually send.

---

## What You Just Did

You did four things most managers never formalize:

1. **Named** the stakeholders whose reactions actually shape your work.
2. **Captured** their fears, values, and communication preferences in one place.
3. **Retuned** a real message multiple ways without compromising facts.
4. **Built** an interactive viewer that swaps framing in one click.

The skill compounds. Every message next quarter gets easier because the stakeholder map already knows who is reading.

## What Not to Do

1. **Do not use made-up stakeholders.** Real people or real archetypes only.
2. **Do not let Claude soften facts to make a version land better.** Retuning is reordering, not editing the truth.
3. **Do not stop at three stakeholders.** 4-6 is the useful range.
4. **Do not treat the first profile draft as final.** Refine over weeks as you notice how people actually react.
5. **Do not share the viewer broadly if it contains sensitive characterizations.** Real-name profiles are private.

## Next Steps

When you have used the map for a couple of weeks:

- **Reviewing Hard Feedback** (medium) — Pressure-test feedback for clarity and kindness.
- **Practicing a Coaching Conversation** (medium) — Rehearse a hard 1:1 before it happens.
- **Build Your First Skill** (easy) — If you skipped it, the foundational pattern.

## Reference

- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview of how skills work
- [Good Prompting](/docs/good-prompting) — patterns that make skill instructions actually work

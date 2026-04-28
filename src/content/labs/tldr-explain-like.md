---
title: "Audience-Tuned Summaries"
difficulty: easy
time: "20 minutes"
tags: ["summaries", "audience", "html"]
prerequisites:
  - "Claude Code is already open"
  - "A piece of long content you actually need to understand (an article, document, transcript, email chain, report, or policy)"
  - "A web browser for the visual artifact"
learn:
  - "How to get summaries tuned to specific audiences, not generic ones"
  - "How to reframe the same content for different readers in seconds"
  - "How to generate an interactive HTML summary viewer that lets you switch audiences"
  - "How to turn your favorite framing into a reusable skill"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/overview"
order: 7
---

## What You Are Building

An interactive HTML summary viewer for a real piece of long content. One source, multiple audience-tuned summaries, switchable with a single click. Pick "director," "skeptical stakeholder," "new hire," or "me next week" and the summary reshapes itself. Same facts. Different emphasis, different length, different tone.

You are not learning to code. You pick the content and the audiences. Claude generates all the summaries and builds the HTML switcher.

By the end you will have:

- An interactive HTML file with your content summarized for 3-4 different audiences
- A reusable skill you can run on any long document
- A stronger instinct for how to frame any communication before sending

> **At work, this comes up when you're...**
>
> - reading a long document you did not write and do not have time for
> - catching up on a meeting or thread you missed
> - translating technical detail for a stakeholder who needs the headline
> - preparing briefings for multiple people who all need different things from the same source
> - reading dense policy or contracts and needing to know what matters

## Why This Matters

Most people summarize the wrong way. They ask for a summary, get something generic, and then have to do the real translation themselves. Framing the audience first skips that step. Claude decides what to keep and what to cut based on who is reading, not based on some abstract notion of "importance."

The interactive HTML viewer is the upgrade. Instead of four separate summaries in four chat windows, you get one file where a click swaps the framing. Perfect for pre-meeting prep when you know three stakeholders will ask three different questions.

---

## Pick the content and the audiences

> **Hint:** _The audiences matter more than the content. Vague audiences equal generic summaries. Specific audiences equal sharp ones._

Pick a real piece of long content. Then pick 3-4 specific audiences you want summaries for:

- "A director who has 3 minutes and will ask one question"
- "A new hire on my team who does not know this program"
- "A skeptical stakeholder who thinks this is a waste of money"
- "Me, next week, when I have to reference this in a meeting"
- "A peer in another department who needs just enough to help"

Each one should have a one-sentence description of what they care about.

> **You're there when:** you have the content and 3-4 specific audience profiles ready.

---

## Ask Claude to generate audience-tuned summaries

Paste this:

```
I am going to share a piece of content. Produce 3-4 summaries of it, one per audience.

For each audience, I will give you:
- Who the reader is (one sentence)
- What they care about (2-3 things)
- How much time they have (sentence, paragraph, page)
- Format they want (bullets, narrative, one-liner, decision memo)

For each summary, keep the facts identical. Only change emphasis, ordering, tone, and what gets said first.

After all summaries, tell me in one line what the biggest difference was between them.

Audiences:
1. [paste first audience profile]
2. [paste second]
3. [paste third]
4. [paste fourth if you have one]

Content:
[paste the content, or describe it if it is too long]
```

Claude will produce N summaries. Read them side by side.

> **You're there when:** you have 3-4 distinct summaries of the same content.

---

## Interrogate the differences

> **Hint:** _Compare side by side. If two summaries read the same, the framing is not doing enough work._

Read them as each audience would. For each, ask:

- Would this reader actually want to read this?
- Does it open with what they care about?
- Is anything here they would not care about?

Push back:

```
The director version still opens with context. Rewrite it so the first sentence has the headline finding, not the setup.
```

```
The skeptical stakeholder version reads too defensively. Lead with the financial impact, not an apology.
```

> **You're there when:** each summary reads differently and each one fits its audience.

---

## Generate the interactive HTML viewer

Paste this:

```
Now build me a single self-contained HTML file called summary-viewer.html that presents all the audience-tuned summaries. Requirements:

- Header: title of the source content and date
- A row of audience pill buttons at the top (one per audience). Clicking a pill swaps the summary displayed below.
- The current audience's profile shows as a small card above the summary (who they are, what they care about, time budget, preferred format)
- The summary itself renders cleanly with appropriate styling for its format (bullets get bullet styling, narrative gets prose styling, decision memo gets clear sections)
- A "Compare" toggle that shows two summaries side by side for quick contrast
- A "Print this view" link that prints only the currently displayed summary
- Clean modern styling: good typography, generous whitespace, soft palette

Use only inline CSS and vanilla JavaScript.
```

Open `summary-viewer.html` in your browser. Click through the audience pills. Hit the compare toggle to see two side by side.

> **You're there when:** the viewer renders, audience switching works instantly, and compare mode shows two summaries side by side.

---

## Save as a skill

Paste this:

```
Turn this into a reusable Claude Code skill called "audience-summaries". It should:

- Take any piece of content I paste
- Ask me for 3-4 audience profiles (who, what they care about, time, format)
- Generate audience-tuned summaries with identical facts
- Produce the summary-viewer.html file as the final artifact

Install at ~/.claude/skills/audience-summaries/SKILL.md.
```

> **You're done when:** the skill is installed and the viewer renders for multiple audiences.

---

## What You Just Did

You proved that summarization is really an audience problem, not a content problem:

1. **Named real audiences** with specific concerns, not "me" or "a stakeholder."
2. **Generated parallel summaries** with identical facts but different emphasis.
3. **Built an interactive viewer** that swaps framing with one click.
4. **Captured the pattern** so future summaries take 5 minutes across N audiences.

## What Not to Do

1. **Do not ask for a summary without an audience.** Generic summaries are generic.
2. **Do not describe the audience as "me."** Name the actual person or role.
3. **Do not ship the first draft.** One round of audience-specific refinement makes a big difference.
4. **Do not re-paste content.** Claude has it from the earlier turn. Just ask for the reframe.
5. **Do not use this for short content.** This lab is for long content or multi-audience needs.

## Next Steps

Once you have run this on three different documents:

- **Tuning Messages for Stakeholders** (medium) — Apply the same audience-tuning instinct to outgoing messages, not just summaries.
- **Build Your First Skill** (easy) — Turn your best "explain it like I'm..." pattern into a reusable skill.
- **Claude as a Thought Partner** (easy) — Flip the mode and use Claude to probe your thinking.

## Reference

- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn your best framing into a reusable tool

---
title: "TLDR: Explain It Like I'm..."
difficulty: easy
time: "15 minutes"
tags: ["summaries", "foundational", "reading"]
prerequisites:
  - "Claude Code is already open"
  - "A piece of long content you actually need to understand (an article, document, transcript, email chain, report, or policy)"
  - "No coding experience needed."
learn:
  - "How to get a summary tuned to your actual audience, not a generic one"
  - "Why naming the audience changes what gets kept and what gets cut"
  - "How to re-run the same summary for different audiences without re-reading the source"
  - "How to turn your favorite framing into a reusable skill"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/overview"
order: 4
---

## What You Are Building

A summary of a real piece of content, tuned to the audience who actually needs to understand it. By the end of this lab you will know how to frame a summary in three or four different ways depending on who is reading it, without re-reading the source each time.

This is the difference between "summarize this" (which gives you something generic) and "explain this like I'm the board of directors" (which gives you something usable). The audience framing changes everything.

> **At work, this comes up when you're...**
>
> - trying to understand a long document you did not write and do not have time to read in full
> - catching up on a meeting or thread you missed
> - translating technical detail for a stakeholder who needs the headline, not the weeds
> - preparing a briefing for a specific person and need to filter what they will care about
> - reading dense policy or contract language and need to know what matters

## Why This Matters

Most people summarize the wrong way. They ask for a summary, get something generic, and then have to do the real translation work themselves. Framing the audience first skips that step. Claude decides what to keep and what to cut based on who the reader is, not based on some abstract idea of "importance."

The second win: once you have the source loaded in the conversation, you can re-run the summary for different audiences in seconds. Same content, four different briefings for four different people. That is time compounding into your week.

---

## Pick the content and the reader

> **Hint:** _The reader matters more than the content. Vague reader, generic summary. Specific reader, sharp summary._

Pick a real piece of content you actually need to understand. It can be pasted in, linked to, or described. Anything works.

Then pick the reader. Not "me." Be specific. Examples:

- "A director who has three minutes and will ask one question"
- "A new hire on my team who does not know this program yet"
- "A skeptical stakeholder who thinks this is a waste of money"
- "A peer in another department who needs just enough to help"
- "Me, a week from now, when I have to reference this in a meeting"

The reader frame is doing the real work. Spend 20 seconds picking it carefully.

> **You're there when:** you have the content and a one-sentence description of who the summary is for.

---

## Ask for the framed summary

> **Hint:** _Claude is better when you tell it the reader AND what the reader cares about. Do not make Claude guess._

In your Claude Code window, paste this prompt and fill in the parts in brackets:

```
I am going to share a piece of content. Summarize it for this specific reader:

Reader: [describe the reader in one sentence]
What this reader cares about: [list 2 or 3 things]
How much time they have: [a sentence, a paragraph, a page]
Format they want: [bullets, narrative, one-liner, decision memo, etc.]

Here is the content:
[paste the content, or describe it if it is too long]
```

Send it. Claude will produce a summary shaped to the reader.

> **You're there when:** you have a summary in hand that is framed for your specific reader.

---

## Read it as the reader

> **Hint:** _Do not read it as yourself. Read it pretending to be the reader you described. The mismatches will jump out._

Read the summary like you are the person you named. Ask yourself:

- Would this reader actually want to read this?
- Would they know what to do next after reading it?
- Is there anything a reader like them would ask that is not answered?
- Is anything here that they would not care about?

If something is off, tell Claude:

```
The summary is too long for a three-minute read. Cut it in half. Keep the part about [X] because that is what this reader will ask about.
```

or

```
This reader is skeptical about the spend. Lead with the financial impact, not the timeline.
```

Iterate until the summary fits the reader. Usually one or two passes is enough.

> **You're there when:** the summary would land well with the specific reader you named.

---

## Re-run it for a different reader

> **Hint:** _This is the magic move. Same content, different audience, seconds apart._

Tell Claude to reframe the same content for a different reader:

```
Now give me the same summary, but for a new hire on my team who is reading this to understand what their first 30 days might involve. One page max, written in plain language.
```

Notice that Claude does not need you to paste the content again. It has it from the earlier turn. You just changed the audience.

Try one more reader if you want. Each reframe takes ten seconds and produces a genuinely different summary. Same facts. Different filter.

> **You're there when:** you have the same content summarized for at least two different readers and can see how the framing changed the output.

---

## What You Just Did

You just proved that summarization is really an audience problem, not a content problem. The same text produces completely different useful summaries depending on who you aim it at.

You also unlocked a pattern: once the source is in the conversation, you can produce N different briefings for N different people in the time it takes to drink a coffee. That is a real workflow, not a trick.

## What Not to Do

1. **Do not ask for a summary without a reader.** Generic summaries are generic. Every time.
2. **Do not describe the reader as "me."** You are not your own audience. Name the actual person or role.
3. **Do not ship the first draft.** Read it as the reader. Push back. One round of refinement makes a big difference.
4. **Do not re-paste content.** Claude already has it from the earlier turn. Just ask for the reframe.
5. **Do not use this for short content.** If you can read it in two minutes, read it. This lab is for long content or multi-audience needs.

## Next Steps

When you have done this three or four times with different content and audiences, turn your favorite framing into a reusable skill:

- **Build Your First Skill** (easy) — Turn your best "explain it like I'm..." pattern into a skill you can invoke any time with `/tldr-for-director` or whatever name you pick.
- **Claude as a Thought Partner** (easy) — Flip the mode and use Claude to probe your thinking instead of summarizing content.
- **Planning with Claude** (easy) — Summaries help you understand. Planning helps you act on what you understood.

## Reference

- [Claude Code overview (official docs)](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Build Your First Skill](/labs/build-your-first-skill) — turn your best framing into a reusable tool

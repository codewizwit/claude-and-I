---
title: "Building a Voice Guide"
difficulty: medium
time: "35 minutes"
tags: ["writing", "voice", "html"]
prerequisites:
  - "Claude Code is already open"
  - "5-10 pieces of your own writing you would be happy to have Claude imitate"
  - "A web browser for the visual artifact"
learn:
  - "How to extract the patterns that make your writing sound like you"
  - "How to turn those patterns into a reusable Voice Guide skill"
  - "How to generate an interactive HTML voice fingerprint showing sentence rhythm, signature phrases, and tone range"
  - "How to test drafts for voice drift and correct in plain English"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 18
---

## What You Are Building

A Voice Guide skill tuned to how you actually write, plus an interactive HTML voice fingerprint that visualizes your patterns: sentence length distribution as a chart, signature phrases as a tag cloud, opener moves as a list, words you avoid as a red-flagged list, and tone range from casual to formal with real sample sentences. Open the fingerprint and see your own voice, written down for the first time.

You are not learning to code. You paste your samples, Claude extracts the patterns and builds the skill, and Claude generates the visual fingerprint.

By the end you will have:

- A Voice Guide skill installed that Claude can call when drafting
- An HTML voice fingerprint you can share with a chief of staff or EA
- A voice-tuned draft of something you need to send this week

> **At work, this comes up when you're...**
>
> - writing Slack messages, emails, or status updates at volume and watching your voice flatten
> - asking Claude for a first draft and getting something generic you rewrite from scratch
> - onboarding a teammate who needs to send things "in your name"
> - sending announcements or all-hands notes and worrying they sound robotic
> - ghostwriting for your boss or stakeholder and trying to hit their voice, not yours

## Why This Matters

Most people believe "sounds like me" is vague and untrainable. It is not. Your voice is a short list of habits: sentence length, opener moves, signature phrases, words you avoid, rhythm. Once those habits are written down, Claude can imitate them, and so can anyone else you share the guide with.

The fingerprint is the upgrade. Text profiles get skimmed once. A visual fingerprint with a sentence-rhythm chart and a phrase cloud is something you refer back to and share.

---

## Collect your samples

> **Hint:** _Pick writing that sounds like you on a normal day. The middle of your range is where your real voice lives._

Pull together 5-10 pieces:

- Slack messages to your team or a peer
- Emails to a stakeholder or direct report
- Short docs or memos
- Status updates, retro notes
- A LinkedIn post or two if you write them

Variety matters. A couple casual, a couple formal, a couple explaining something. Strip confidential content.

> **You're there when:** you have 5-10 real samples ready.

---

## Ask Claude to find your patterns

Paste this, then paste samples:

```
I want to build a Voice Guide. I will paste 5-10 samples. Read them carefully and pull out the patterns that make my voice mine.

Tell me:
- Average sentence length and what I do with short vs long sentences
- How I open (messages, emails, docs)
- How I close
- Signature phrases I use (words or phrases that show up multiple times)
- Words and phrases I clearly avoid
- Tone range, casual to formal, with real examples
- Rhythm or punctuation habits worth naming

Be specific. Quote me. If something is only in one sample, say so.
```

Paste samples. Let Claude read.

Push back if anything is off:

```
You said I use exclamation points often. I almost never use them. Look again.
```

```
You missed that I always open with a one-sentence summary. Add that.
```

> **You're there when:** Claude's pattern list feels like a mirror, not a guess.

---

## Turn patterns into a Voice Guide skill

Paste:

```
Turn the pattern list into a Claude Code skill called voice-guide. Include:
- When to use it (any time I am drafting in my own voice)
- Sentence length and rhythm rules
- Opener and closer moves
- Signature phrases
- Words to avoid
- Tone range with examples
- A "Do not" section

Explain each section. Install at ~/.claude/skills/voice-guide/SKILL.md.
```

The description line is critical. If it is vague, sharpen:

```
Rewrite the description to name exactly when I would want this skill to kick in.
```

> **You're there when:** the skill is installed and each section reads like you.

---

## Generate the interactive HTML voice fingerprint

Paste this:

```
Build me a single self-contained HTML file called voice-fingerprint.html. Requirements:

- Header: "Voice Guide — [my name]"
- Section 1: Sentence rhythm. A histogram (Chart.js via CDN) showing distribution of sentence lengths across my samples. Brief text: average, median, range.
- Section 2: Signature phrases. A styled tag cloud. Bigger text for phrases that appear more often. Hover shows sample sentence using that phrase.
- Section 3: Opener moves. Numbered list of my common openers with one real sample for each.
- Section 4: Closer moves. Same treatment.
- Section 5: Words I avoid. Red-flagged list.
- Section 6: Tone range. A horizontal slider bar from casual to formal with 3-4 anchor points, each with a real sample sentence.
- Footer: "How to use this Voice Guide" with the /voice-guide invocation and a link to share with an EA or chief of staff.
- Clean modern styling, calm palette, good typography.
```

Open `voice-fingerprint.html`. Hover the phrases. Check the histogram.

> **You're there when:** the fingerprint renders and you can see your own voice on a page for the first time.

---

## Test on something you need to write

Pick something real you need to send. Paste:

```
/voice-guide Draft a short update to my team about [what you need to say]. Under 150 words.
```

Read the output. Ask: if a colleague saw this with no name, would they guess it was me? Push back where it drifts:

```
The draft opened with "I hope you're all doing well." I do not write that. Update the skill so it never opens with a pleasantry.
```

Test across three formats: a casual Slack, a formal stakeholder update, a longer doc. Voice should stay steady.

> **You're done when:** three different kinds of writing all pass the "no seam" test.

---

## What You Just Did

You turned a fuzzy idea ("my voice") into a concrete reusable tool:

1. **Collected evidence** of how you actually write.
2. **Extracted patterns** with Claude as a careful reader.
3. **Packaged the patterns** into a skill.
4. **Visualized the voice** as a fingerprint anyone can read.
5. **Stress-tested** across formats until voice stayed steady.

## What Not to Do

1. **Do not skip the sample collection.** Samples are where the truth lives.
2. **Do not accept vague pattern descriptions.** Specific or push back.
3. **Do not combine voice with task-specific instructions.** Separate skills.
4. **Do not test on made-up scenarios.** Real writing only.
5. **Do not forget the "Do not" section.** Half the value.

## Next Steps

Once your Voice Guide feels steady:

- **Recurring Weekly Updates** (easy) — An update skill that calls your Voice Guide.
- **Reverse-Outlining a Document** (easy) — Audit structure of longer writing.
- **Build Your First Skill** (easy) — Foundational skill-building.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview

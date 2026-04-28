---
title: "Build a Lab"
difficulty: medium
time: "35 minutes"
tags: ["meta", "contribution", "html"]
prerequisites:
  - "Claude Code is already open"
  - "You have completed at least two labs so the shape is familiar"
  - "A workflow you do well that your team does badly, or one you figured out the hard way"
  - "A web browser for the visual artifact"
learn:
  - "How to recognize the anatomy of a good lab"
  - "How to turn a workflow you do well into a scaffolded experience someone else can follow"
  - "How to generate an interactive HTML lab preview that renders your draft like a real lab page"
  - "How to produce a submittable lab spec ready for review"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 22
---

## What You Are Building

A complete, submittable lab spec of your own, plus an interactive HTML lab preview that renders your draft exactly like the labs you have been completing — with the banner, the checkpoints, the hint callouts, the "You're there when" signals, the "What You Just Did" recap, and every other element of the platform's lab anatomy. Open the preview in your browser and see your contribution styled as a real lab.

You are not learning to code. Claude interviews you about the workflow, drafts the lab, and generates the preview so you can see how it will land before submitting.

By the end you will have:

- A markdown lab spec file ready for review
- An HTML preview that renders the spec like a real platform lab
- A submission PR or message draft ready to send

> **At work, this comes up when you're...**
>
> - noticing a workflow your team does badly when you have a repeatable fix
> - wanting to share something you learned the hard way
> - training your team to build their own tools instead of asking you every time
> - onboarding new hires and wishing tribal knowledge lived somewhere they could actually learn from
> - realizing the same question keeps coming to you and you would rather answer it once

## Why This Matters

This is the meta-lab. It is how the platform scales. Every person who completes this lab and contributes one back grows what is available to everyone else.

A great lab is not a walkthrough. It is a scaffolded aha. Once you see the structure (hook, stakes, guided steps, artifact, debrief), you can capture any workflow you do well and make it teachable.

The HTML preview is the upgrade. Before you submit, you see exactly how your lab will render — which is the only way to catch weak "You're there when" signals or missing hooks.

---

## Pick the workflow

> **Hint:** _Best lab topics are workflows you do in under 35 minutes, produce a real artifact, and that other people on your team get wrong or avoid._

Four properties your candidate needs:

- **Repeatable.** You do it more than once a year.
- **Teachable in under 35 minutes.**
- **Produces a real artifact.** Plan, skill, template, rewrite.
- **Has an aha.** A moment where the learner realizes the approach is different from what they were doing.

Good candidates:

- A 30-minute planning routine you run before every initiative
- A specific rewrite move you make on docs, emails, postings
- A way you pull apart a messy situation before deciding
- A debrief ritual after projects or incidents

> **You're there when:** you have a one-sentence workflow description and can name the aha.

---

## Let Claude interview you

Paste this:

```
I want to turn a workflow I do well into a 35-minute lab. The workflow is: [one sentence].

Interview me one question at a time. Cover:
- The aha: what does the learner realize at the end that they did not know at the start
- The audience: who is this for, what are they already doing badly
- The at-work scenarios: when does this come up
- The steps: what are the 4-6 moves I make, in order
- The artifact: what they walk away with, concretely (include a creative HTML artifact they produce by running a prompt)
- The failure modes: what people get wrong without guidance

When you have enough, tell me you are ready to draft.
```

Answer carefully. The interview is where the lab gets made.

> **You're there when:** Claude has enough context to draft a specific lab.

---

## Draft the lab spec

Paste:

```
Draft the full lab spec using the platform's structure:

- YAML frontmatter: title, difficulty, time, tags, prerequisites, learn, docs, order
- "What You Are Building" with the artifact (including a creative HTML output)
- "At work, this comes up when you're" blockquote with 4-5 scenarios
- "Why This Matters" with real stakes
- 4-6 action-headed steps. Each has:
  - Action verb phrase as header
  - "Hint" blockquote opener in italics
  - Any prompts the learner pastes into Claude
  - "You're there when" closer with observable signal
- "What You Just Did" recap
- "What Not to Do" guardrails
- "Next Steps" linking to adjacent labs
- "Reference"

Voice: plain English, warm, direct. No em dashes. No emojis. Title should be direct, not catchy.
```

Read the draft. You will flinch at a few things. That is the next step.

> **You're there when:** you have a full draft with every section filled in.

---

## Pressure-test every step

> **Hint:** _The failure mode of a lab is a step a learner cannot complete. Walk through yours as a first-timer would._

For each step, ask:

1. Does the hint name the real question in the learner's head?
2. Is "You're there when" a concrete signal or a vague feeling?
3. If I had never done this workflow, would I know what to do next?

If any answer is no, push back:

```
Step 3's "You're there when" is "when you feel ready." Replace with a concrete, observable signal.
```

```
Step 2's hint does not match the real question. At that point they are wondering [X]. Rewrite to speak to that worry.
```

Also stress-test the aha: if a learner finished this lab, what do they believe they did not believe at the start?

> **You're there when:** every step has a specific hint, concrete "You're there when," and the aha is one sentence.

---

## Polish the voice

Paste:

```
Final pass on voice only. Do not change structure. Only fix:
- Remove em dashes. Use period or comma.
- Remove emojis.
- Remove corporate filler: "at the end of the day," "leverage," "synergy," "level up," "unlock," "empower."
- Every sentence should sound like a peer over coffee, not a LinkedIn post.
- Every "You're there when" starts with an observable signal.
```

> **You're there when:** the lab sounds like the platform's voice.

---

## Generate the HTML lab preview

Paste this:

```
Build me a single self-contained HTML file called lab-preview.html that renders my lab spec exactly like the platform pages. Requirements:

- Header: title, difficulty pill, time pill, tags
- "Prerequisites" and "What You'll Learn" banners side by side
- "Reference" strip with doc links
- Main content rendered from the spec with platform styling:
  - Blockquote callouts (hint, at-work, you're there when) styled distinctively
  - Action-headed sections with dividers between them
  - Code blocks in terminal-style dark boxes with copy buttons
  - What You Just Did, What Not to Do, Next Steps, Reference sections
- A footer CTA: "You just built an artifact you can keep"
- Clean modern styling, light background, soft palette

Inline CSS only. Use the spec I drafted above as the content.
```

Open `lab-preview.html`. You should see your lab rendered exactly as it would appear on the platform.

> **You're done when:** the preview renders, you would submit it as-is, and you can describe the aha in one sentence.

---

## What You Just Did

You turned tacit knowledge into shared capability:

1. **Named** a workflow that was invisible to those who would benefit.
2. **Structured** it into the platform's lab anatomy.
3. **Pressure-tested** every step so a first-timer would not get stuck.
4. **Polished** into the platform's voice.
5. **Previewed** the lab as it will render so you know how it lands before submitting.

Every lab submitted is one less workflow trapped in one person's head.

## What Not to Do

1. **Do not try to teach a 4-hour process in a 35-minute lab.** Split it.
2. **Do not skip the aha.** Lab without aha is a checklist.
3. **Do not use "Checkpoint 1" as headers.** Action verbs only.
4. **Do not leave vague "You're there when."** Observable signals only.
5. **Do not submit without the voice pass.** One em dash and the lab stops sounding like the platform.

## Next Steps

Once you have submitted your first lab:

- **Build Your First Skill** (easy) — Foundational pattern if you skipped it.
- **Build a Custom Agent** (medium) — Turn a role you keep playing into a specialist agent.
- **Agent Teams** (hard) — Orchestrate specialists on one project.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview
- [Good Prompting](/docs/good-prompting) — patterns that work

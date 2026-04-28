---
title: "Rewriting a Job Description"
difficulty: easy
time: "30 minutes"
tags: ["hiring", "writing", "html"]
prerequisites:
  - "Claude Code is already open"
  - "An old job description for a role you are hiring for, replacing, or rewriting"
  - "A web browser for the visual artifact"
learn:
  - "How to pull apart a JD into what matters vs cultural noise"
  - "How to use Claude to stress-test every requirement so only real ones survive"
  - "How to generate an interactive HTML before/after comparison showing what was cut, kept, and added"
  - "How to save the moves as a reusable skill for every future role"
docs:
  - "https://code.claude.com/docs/en/skills"
  - "/docs/what-is-a-skill"
order: 17
---

## What You Are Building

A clean, shippable job description for a real role, plus an interactive HTML before/after comparison that visualizes what was cut, kept, reframed, or added. Hover over a requirement in the old JD to see why it was cut or how it was reworded in the new one. Share with HR or the hiring panel to explain the rebuild.

You are not learning to code. You paste the old JD, Claude sorts it into three buckets, you challenge the must-haves, Claude generates the new posting and the comparison.

By the end you will have:

- A rebuilt JD you would post today
- An HTML comparison file showing what changed and why
- A reusable "jd-template" skill for every future role

> **At work, this comes up when you're...**
>
> - opening a new role and staring at a blank doc or stale template
> - replacing someone who left and inheriting a JD nobody trusts
> - trying to figure out why a role keeps attracting the wrong candidates
> - cleaning up a posting HR wrote in a language your team does not speak
> - sitting on five drafts with conflicting feedback from three stakeholders

## Why This Matters

Most JDs are wishlists glued together by HR. They collect requirements from everyone who touched the role in the last three years. The result is a posting that filters out strong candidates and tells people who apply nothing true about the job.

When you force Claude to challenge every requirement, half the items turn out to be cultural signaling. Another chunk are legacy preferences. What is left is the actual job.

The HTML comparison is the upgrade. When you explain to HR why you cut "5+ years of experience" and rewrote "strong communication" as "writes clearly under deadline pressure for a non-technical audience," a visual before/after is far more persuasive than a text debate.

---

## Find the JD to fix

> **Hint:** _Start from whatever posting, template, or draft already exists, even if terrible._

Grab:

- A posting you are about to publish
- A template HR uses for this level
- The old version from the last time you hired this role
- A competitor's posting if that is all you have

> **You're there when:** you have the full text ready.

---

## Ask Claude to pull it apart

Paste this, then paste the JD:

```
I want to rebuild this JD from scratch. Before rewriting, sort every requirement, responsibility, and qualification into three buckets:

1. MUST HAVE: person cannot do this job without it
2. NICE TO HAVE: helps but is trainable or optional
3. CODE FOR SOMETHING ELSE: cultural signaling, legacy preference, or proxy for a real need we should name directly

For each item in bucket 3, tell me what you think the real underlying need is.

[paste JD]
```

Read through. Notice where you flinch. Those flinches are the honest signal.

> **You're there when:** you have the three-bucket sort and have answered the bucket-3 questions.

---

## Challenge the must-haves

Paste:

```
Now challenge every item in MUST HAVE. For each, ask:
- Has a successful person in this role ever not had this?
- Is it the thing we need, or an outcome it produces?
- If removed, what is the worst thing that happens?

One at a time. Wait for my response.
```

Answer honestly. You will usually find 2-3 of your "must haves" are actually nice-to-haves, and 1 nice-to-have is actually a must-have.

Watch for: years-of-experience as a proxy for judgment, degrees as a proxy for skill, tools as a proxy for capability, "strong communication" as a proxy for specific writing or meeting style.

Rewrite each as the actual thing. "Writes clearly under deadline pressure for a non-technical audience" beats "excellent communication skills."

> **You're there when:** every surviving must-have is something you would defend to a skeptical peer.

---

## Rebuild the posting

Paste:

```
Rebuild the JD using only what survived. Keep my voice, not corporate HR voice. Include:

- One paragraph on what this person will do in the first 90 days
- Must-haves as plain capabilities
- Nice-to-haves labeled as optional
- What it is like to work here, honestly, not sold
- What success looks like six months in

No buzzwords. No "rockstar," "ninja," "self-starter," "wears many hats." Do not invent things I did not say. Ask if unclear.
```

Read it. Three checks:

1. Would I say this out loud to a candidate on a first call?
2. Would a strong candidate who is outside the box still apply?
3. Would a weak candidate who matches surface keywords be screened out?

Push back:

```
The 90-days paragraph is vague. Rewrite with three concrete things this person will ship or own.
```

```
This still reads like HR. Make it sound like how I talk about this team in a 1:1.
```

> **You're there when:** you would read this posting out loud to a candidate without cringing.

---

## Generate the interactive HTML before/after

Paste this:

```
Build me a single self-contained HTML file called jd-compare.html. Requirements:

- Two columns: Original JD on the left, Rebuilt JD on the right
- Every line in the original is color-coded:
  - Green: kept as-is in the rebuild
  - Yellow: reworded (hover shows the new wording)
  - Orange: cultural signaling, flagged with the real underlying need
  - Red: cut entirely, with reasoning
- Every line in the rebuild is color-coded:
  - Purple: net-new addition, with reasoning for why added
  - Green: carried from original
  - Blue: reworded from original
- Hover any line in either column to see the connection to the other side
- Header shows stats: total lines in original, total in rebuild, lines cut, lines reframed
- A "Change log" panel at the bottom summarizing the 3-5 biggest changes and why
- Clean modern styling, soft palette

Inline CSS and vanilla JS only.
```

Open `jd-compare.html`. Hover lines. See the story of the rebuild.

> **You're there when:** the comparison renders and hovering shows connections between old and new.

---

## Save as a skill

Paste:

```
Turn this into a reusable Claude Code skill called "jd-template". It should:

- Take any JD I paste plus a one-line note about the role and team
- Run the three-bucket sort
- Challenge must-haves one at a time
- Rebuild the posting in my voice
- Refuse buzzwords like "rockstar," "ninja," "self-starter"
- Generate jd-compare.html as the artifact

Install at ~/.claude/skills/jd-template/SKILL.md.
```

Test on a second real JD. If it drifts, name what was off.

> **You're done when:** you can run the skill on a fresh JD in a new conversation and get a clean posting and comparison.

---

## What You Just Did

You did four things most hiring managers never do:

1. **Separated** real requirements from cultural signaling.
2. **Challenged** every must-have until only defensible ones survived.
3. **Rewrote** the posting in a voice that attracts the right people.
4. **Visualized** the change so HR and the hiring panel can see why.
5. **Captured** the process as a skill for future roles.

## What Not to Do

1. **Do not skip the three-bucket sort.** That is where the insight lives.
2. **Do not defend the original.** Let Claude challenge you.
3. **Do not let buzzwords sneak back in.** Every one is a capability in disguise.
4. **Do not ship the first draft.** Read out loud.
5. **Do not skip the skill.** The second role should take 20 minutes.

## Next Steps

Once the skill has survived two postings:

- **Build a 30/60/90 Onboarding Plan** (medium) — Turn the hire into a real onboarding plan.
- **Build Your First Skill** (easy) — Foundational skill-building.
- **Build a Lab** (medium) — Capture a workflow and turn it into a teachable lab.

## Reference

- [Official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [What is a Skill?](/docs/what-is-a-skill) — plain-language overview

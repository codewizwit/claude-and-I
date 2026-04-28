---
title: "Agent Teams"
difficulty: hard
time: "40 minutes"
tags: ["agents", "orchestration", "configuration"]
prerequisites:
  - "You have completed Build Your First Skill and Build a Custom Agent"
  - "You have at least 2-3 sub-agents already installed in ~/.claude/agents/"
  - "Claude Code is open and working"
  - "A real multi-part project on your plate this week (research plus writing, drafting plus review, planning plus stakeholder comms)"
  - "A web browser for the visual artifact"
learn:
  - "The real Claude Code agent team configuration, file structure, and invocation patterns"
  - "How to use plan mode to review a team orchestration before any work fires"
  - "How main Claude dispatches work to specialists running in parallel context windows"
  - "How to generate a visual HTML team map that shows the full orchestration at a glance"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/sub-agents"
  - "https://docs.anthropic.com/en/docs/claude-code/interactive-mode"
  - "/docs/agent-catalog"
order: 3
---

## What You Are Building

A real multi-part project tackled by a team of sub-agents working in parallel, plus an interactive HTML team map that visualizes the orchestration: who did what, what ran in parallel, what depended on what, and how the outputs aggregated into the final deliverable.

You are not learning to code. Your main Claude Code conversation acts as a manager. It decomposes the project, routes pieces to the right specialists, waits for them to finish, and assembles the result. The specialists each run in their own context window so they stay focused.

By the end you will have:

- A completed real project (briefing doc, launch plan, strategic memo, meeting prep, retrospective — whatever you chose)
- An HTML team map file you can open in a browser showing the orchestration visually
- A one-page dispatch playbook: which agent to use for which kind of work in the future

> **At work, this comes up when you're...**
>
> - staring at a project that needs research + analysis + writing + review and wishing you could split it across four smart people
> - planning a launch with multiple workstreams that need different lenses
> - drafting a strategic document that needs a skeptic's pass, a clarity edit, and stakeholder versions
> - prepping for a big meeting with attendee research, talking points, and anticipated questions all needed in parallel
> - hitting the limit of what one Claude conversation can do cleanly without losing focus

## Why This Matters

A single conversation is one thread of thinking. It can do one thing well at a time. When you ask one conversation to research a company, draft a brief, critique the brief, and translate it for three audiences, the context gets noisy, voice drifts, and quality flattens.

A team of agents is a set of specialists, each with its own focus and its own fresh context. They run in parallel. Their outputs come back clean because each one only had to hold its own job in its head. Your main conversation does the highest-value thinking: what needs to happen, who should do what, how the pieces fit.

## The Actual Configuration

Your agent team lives in two places:

```
~/.claude/agents/              <- personal agents, available across all projects
<project>/.claude/agents/      <- project-specific agents (override personal agents by same name)
```

Each file is a markdown document with YAML frontmatter. Here is a minimal example from a three-agent team:

```yaml
# ~/.claude/agents/researcher.md
---
name: researcher
description: Gathers context and recent news on a company, person, or topic. Returns a one-page summary with sources. Use when I need background before a meeting, decision, or document.
model: sonnet
tools: Read, Write, WebSearch, WebFetch
---
You are a research specialist. Gather recent, relevant context and return a clean one-page summary.
(system prompt continues...)
```

```yaml
# ~/.claude/agents/writer.md
---
name: writer
description: Takes research notes or rough inputs and produces a clean draft in my voice. Use when I have raw material and need a polished first draft.
model: sonnet
tools: Read, Write
---
You are a writing specialist. Produce drafts in my voice. Do not invent new information.
(system prompt continues...)
```

```yaml
# ~/.claude/agents/skeptic.md
---
name: skeptic
description: Stress-tests a draft by playing hostile reviewer and surfacing what a stakeholder will push back on. Use when I have a draft that needs to survive scrutiny.
model: sonnet
tools: Read
---
You are a skeptic. Read drafts and surface the weakest claims, hidden assumptions, and unanswered questions. Do not rewrite.
(system prompt continues...)
```

Three patterns matter for orchestration:

- **Invocation by name:** `@researcher`, `@writer`, `@skeptic` routes work directly.
- **Auto-routing via description:** Main Claude reads every agent's description and dispatches work automatically when a task matches.
- **Parallel execution:** Main Claude can call multiple agents simultaneously. Each runs in its own context window.

The `tools` field is key for team safety. A Researcher needs web access. A Skeptic is read-only. A Writer can write but should not run shell commands. Narrow tools equal predictable behavior.

---

## Pick one real project for the team

> **Hint:** _Not a hypothetical. Something on your calendar this week that feels like more than one kind of work._

Good candidates:

- A briefing doc that needs research, drafting, and a skeptic's pass
- A launch plan with market research, a draft plan, a risk review, and a stakeholder summary
- A strategic memo that needs a first draft, a critique, and two audience-specific versions
- Prep for a high-stakes meeting: attendee research, talking points, anticipated questions, and a one-pager

Pick one you would otherwise do yourself, the long way.

> **You're there when:** you can describe the project in two sentences and name at least three distinct kinds of work inside it.

---

## Confirm your team exists

> **Hint:** _Before you orchestrate, make sure the specialists are installed. A team with missing players cannot run._

In a terminal, check:

```
ls ~/.claude/agents/
```

You should see your agent files. If you are missing a specialist the project needs (researcher, writer, skeptic, translator, editor), ask Claude to build them before continuing. In plain English:

```
For the project I am about to run I need a @skeptic agent. Build one that reads drafts and surfaces the weakest claims, hidden assumptions, and unanswered questions. It should be read-only (no Write tool). Save it to ~/.claude/agents/skeptic.md.
```

Claude will write and install the file. Verify with `ls ~/.claude/agents/` again.

> **You're there when:** the agents you need for this project all appear in `~/.claude/agents/`.

---

## Use plan mode before the team fires

> **Hint:** _Agent teams fan out fast. Plan mode lets you see the orchestration before any work happens._

Turn on plan mode by pressing **Shift+Tab** twice in your Claude Code window. The indicator at the bottom should read **plan mode on**.

Now paste this prompt:

```
I want to tackle this project as a team, not a single conversation.

The project: [describe in 2-4 sentences]

Available specialists: @researcher, @writer, @skeptic (and any others you have)

Before doing any work, propose an orchestration plan:
1. Decompose the project into distinct pieces of work.
2. Map each piece to the right specialist.
3. Identify which pieces can run in parallel and which must run in sequence.
4. Describe how the specialist outputs aggregate into the final deliverable.
5. Flag anything that should stay in the main conversation instead of being delegated.

Present the plan for my review. Do not execute until I approve.
```

Claude will propose something like:

```
Orchestration plan:

Parallel (can run now):
- @researcher: pull recent context on Acme Corp (news, leadership, funding)
- @researcher: pull recent context on key attendees (LinkedIn bios, recent posts)

Sequential (after research):
- @writer: draft a one-page briefing using both research summaries
- @skeptic: critique the draft, surface 3 weak claims

In main conversation:
- Review skeptic's critique, decide which issues to address
- @writer: revise draft incorporating selected fixes

Final aggregation in main conversation: read-through and ship.
```

Read the plan. Push back if something is off:

```
Move the skeptic pass to happen on the FIRST draft, not the revised one. I want pushback before I commit to revisions.
```

> **You're there when:** you have a plan you believe, with specialists mapped to real pieces of work.

---

## Run the team

> **Hint:** _Approve the plan. Watch what happens. Notice how clean your main conversation stays._

When the plan is right, approve it. Claude will dispatch to the specialists.

Three things to notice while it runs:

1. **Parallel specialists finish in parallel.** Research on Acme and research on attendees complete at roughly the same time, not one after another.
2. **Each specialist returns a clean summary.** You see what they produced, not the noisy process they went through to produce it.
3. **Main conversation stays uncluttered.** The research searching, the drafting iteration, the critique reasoning all live inside the specialists' context windows.

When the run completes, read the aggregated output. Ask the hard question: _is this better than what I would have produced in one conversation?_

If yes, the team model just paid off. If no, common failures:

- A specialist role was too broad (split it)
- The decomposition missed a piece (add a specialist or step)
- The aggregation step was weak (push back and re-aggregate)

Push back:

```
The writer produced a good first draft, but the skeptic's critique did not get folded into the revision. Re-run the revision step incorporating the skeptic's three specific pushbacks.
```

> **You're there when:** you have a final deliverable you would ship, and you can point to which specialist contributed which part.

---

## Generate the visual team map

> **Hint:** _The team map is the artifact that makes orchestration legible. Open it in your browser and you see the whole run at a glance._

Paste this:

```
Now build me a single self-contained HTML file called team-map.html that visualizes the orchestration we just ran. Include:

- A header with the project name and date
- A "Team" section showing each specialist as a card (name, role, tools, one-line purpose)
- A flow diagram showing the run: which agents ran in parallel (side by side), which ran in sequence (arrows between them), and where the main conversation aggregated results
- For each specialist, a small "output preview" that quotes one key finding or sentence they contributed
- A "Dispatch notes" section at the bottom: what worked, what would I change next time, which specialists I would call again

Use clean modern styling: good typography, generous whitespace, soft colors. Inline CSS only so the file is standalone.

Save to my working directory.
```

Open `team-map.html` in your browser. You should see a visual map of the run — agent cards, arrows showing flow, parallel vs sequential clearly differentiated, and previews of what each specialist produced.

This is the artifact that turns "I ran an agent team" into "look at how this actually worked."

> **You're there when:** the team map renders in your browser and tells the story of the run without you having to narrate it.

---

## Write a dispatch playbook

> **Hint:** _The real value is not this one project. It is the mental model you take into next week._

Paste this:

```
Based on this run, help me write a one-page "dispatch playbook" I can use when a messy project lands on my desk. For each of the 3-4 kinds of work I face most often in my role, include:

- Which specialist to call
- What input that specialist needs
- What output to expect back
- What NOT to hand to that specialist (role boundaries)
- Whether to chain it sequentially or run it in parallel with others

Append the playbook to team-map.html as a "Playbook" section at the bottom.
```

Save the updated file. Now the team map is not just a record of one run — it is a field guide for future orchestration.

> **You're done when:** team-map.html has both the orchestration visualization and the dispatch playbook, and you can name one project on your calendar where you would already know how to dispatch it.

---

## What You Just Did

You just ran Claude Code as a manager, not as an assistant.

1. **Decomposed** a real project into pieces different specialists could own.
2. **Delegated** those pieces to agents with narrow, well-defined roles.
3. **Orchestrated** the run with plan mode so you saw the game plan before anything fired.
4. **Aggregated** the specialist outputs into a stronger deliverable than any single pass.
5. **Visualized** the orchestration as an HTML team map anyone can read.
6. **Captured** the pattern in a playbook so future projects dispatch themselves.

This is the jump most Claude Code users never make. Better prompts have a ceiling. Better teams do not.

## What Not to Do

1. **Do not skip plan mode.** Teams fan out fast. Review before execute.
2. **Do not broaden specialists.** One role per agent. Narrow wins.
3. **Do not delegate judgment.** Specialists do the legwork. The final call on what ships stays with you.
4. **Do not run with flaky specialists.** If one agent is unreliable solo, it will be unreliable in a team. Fix it first.
5. **Do not stop after one project.** Two or three runs and the playbook earns its keep.

## Next Steps

Once team orchestration feels natural:

- **Build a Lab** (medium) — Turn your dispatch playbook into a shareable lab for your team.
- **Build a Custom Agent** (medium) — Add one or two more specialists to your bench as you notice new recurring roles.
- **Running a Pre-Mortem** (easy) — Use the same decomposition instinct on risk surfacing, not just project execution.

## Reference

- [Official Claude Code sub-agents documentation](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [Interactive mode (plan mode)](https://docs.anthropic.com/en/docs/claude-code/interactive-mode)
- [Agent Catalog](/docs/agent-catalog) — real examples of agent teams in use

---
title: "Build a Custom Agent"
difficulty: medium
time: "30 minutes"
tags: ["agents", "delegation", "configuration"]
prerequisites:
  - "You have completed Build Your First Skill"
  - "Claude Code is open and working"
  - "One role you keep wishing you had a specialist for (researcher, reviewer, translator, recap writer, anything recurring)"
  - "A web browser for the visual artifact"
learn:
  - "The actual Claude Code agent configuration (file paths, frontmatter, system prompt)"
  - "How to describe a role so Claude writes the agent file for you"
  - "How to invoke an agent by name and how description-driven auto-routing works"
  - "How to build a visual agent card in HTML so the agent's role is obvious at a glance"
docs:
  - "https://docs.anthropic.com/en/docs/claude-code/sub-agents"
  - "/docs/agent-catalog"
order: 2
---

## What You Are Building

A real custom sub-agent installed in your Claude Code environment, plus an interactive HTML "agent card" that renders your agent's name, description, tools, and when it should fire. You open the card in your browser and it looks like a trading card for a specialist on your team. You will use the card to show teammates (or future-you) exactly what the agent does.

You are not learning to code. You describe the role in plain English, Claude writes the agent configuration file and saves it to the right location, and Claude also generates the HTML card that visualizes the agent.

By the end you will have:

- A working agent file at `~/.claude/agents/<your-agent-name>.md`
- A visual HTML card you can open in a browser to see the agent at a glance
- A clear understanding of the four configuration fields that shape any agent's behavior

> **At work, this comes up when you're...**
>
> - playing the same role repeatedly (the researcher, the reviewer, the translator, the recap writer) and wishing you could hand it off
> - tackling a task too big for a single skill but too recurring to reinvent every time
> - wanting a specific perspective on demand (a skeptic, a clarity editor, a data auditor)
> - noticing your main Claude conversation gets noisy because one thread mixes research, drafting, and review

## Why This Matters

Skills scale prompts. Agents scale roles. Once you have a small bench of agents, your Claude Code environment stops feeling like a tool and starts feeling like a team.

There is a second benefit that is easy to miss. Every sub-agent gets its own fresh context window when you invoke it. Research noise stays inside the researcher. Draft iteration stays inside the writer. Your main conversation stays clean, and you can run specialists in parallel without them tripping over each other.

## The Actual Configuration

Before you build anything, know what you are building. A Claude Code sub-agent is a markdown file that lives in one of two places:

```
~/.claude/agents/<name>.md          <- your personal agents, available everywhere
<project>/.claude/agents/<name>.md  <- project-specific agents
```

The file has two parts: YAML frontmatter at the top, and a system prompt in markdown below. Here is what a real one looks like.

```yaml
---
name: research-agent
description: Specialist who researches a company before a sales call. Pulls recent news, leadership moves, funding activity, and recent product announcements. Use when the user asks to prep for a meeting or mentions a company by name.
model: sonnet
tools: Read, Write, WebSearch, WebFetch
---

You are a research specialist. Your job is to prepare the user for a meeting by gathering and summarizing the most relevant recent context on a company or person.

## How you work
1. Confirm the company name and the meeting context.
2. Search for news from the last 90 days.
3. Identify current leadership and any recent changes.
4. Check for recent funding, product launches, or strategic moves.
5. Summarize in one page. Lead with what matters most for the meeting.

## Output format
- Headline: one sentence on the most important recent development
- Recent news: 3-5 bullets with dates and sources
- Leadership: current CEO and any notable recent changes
- Signals: anything likely to come up in the meeting
- Questions to consider asking

## What you do not do
- Do not speculate or invent sources
- Do not write the meeting agenda
- Do not touch files outside the research notes
```

Four fields shape behavior:

- **`name`** becomes the invocation. `name: research-agent` gives you `@research-agent` to call it directly.
- **`description`** is the routing trigger. Claude reads every agent's description and routes tasks automatically when one matches. Specific descriptions get used. Vague ones sit on the shelf.
- **`tools`** restricts what the agent can do. Fewer tools equals more predictable behavior.
- **`model`** picks the engine. Default to Sonnet unless the role needs deeper reasoning (Opus) or speed at scale (Haiku).

Everything below the second `---` is the system prompt: the agent's actual instructions.

---

## Pick your specialist

> **Hint:** _What role do I keep playing this week that I wish I could hand off? That is your agent._

You are picking a role, not a task. Good candidates for non-technical professionals:

- **Research Agent** — company prep before a meeting
- **Meeting Autopsy Agent** — turns raw transcripts into decision logs
- **Stakeholder Translator** — reshapes one message for different audiences
- **Skeptic** — pressure-tests drafts with the questions a stakeholder will ask
- **Clarity Editor** — tightens long writing without changing voice

Pick one you would genuinely use this week.

> **You're there when:** you can name the role in one sentence.

---

## Ask Claude to build the agent with you

> **Hint:** _You do not have to write the file yourself. Claude knows the format. Describe the specialist, answer the questions, and Claude saves the file to the right location._

Paste this prompt. Swap the bracketed part for your role.

```
I want to build a custom Claude Code sub-agent. The specialist I want is: [one or two sentences describing the role].

Before writing the file, ask me 4 to 6 clarifying questions one at a time. Cover:
- When I want this agent to activate (what situations should trigger it)
- What output format I want back
- What tools the agent should and should not have access to
- What voice and style to use
- Anything else that would make this agent genuinely useful

After my answers, write the agent file to ~/.claude/agents/<name>.md, explain each of the four frontmatter fields in plain English, and show me how to invoke it.
```

Claude will ask its questions. Answer specifically. If you do not know what tools the agent needs, say so. Claude will propose.

When Claude writes the file, it will actually save it at `~/.claude/agents/<name>.md`. You can verify with `ls ~/.claude/agents/` in a new terminal.

> **You're there when:** the file exists at `~/.claude/agents/<your-agent-name>.md` and Claude has explained each frontmatter field.

---

## Sharpen the description (the only field that routes work)

> **Hint:** _The description field is where auto-routing lives. If Claude never pulls the agent in on its own, the description is too vague._

Look at your agent's description. It should name the input, the output, and the trigger.

| Vague (do not ship)                | Specific (ships)                                                                                                                                                       |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `description: Does research`       | `description: Specialist who researches a company before a sales call. Use when the user asks to prep for a meeting or mentions a company by name.`                    |
| `description: Helps with meetings` | `description: Turns raw meeting transcripts or notes into a structured decision log with Decisions, Open Questions, Owners, Risks. Use when I paste meeting material.` |
| `description: Reviews drafts`      | `description: Stress-tests a draft by playing hostile reviewer, skeptical board member, and red team. Use when I paste a draft and ask for a critique.`                |

If yours looks like the left column, ask:

```
Rewrite the description so it names the input, the output, and the trigger. Be specific about when Claude should route to this agent automatically.
```

> **You're there when:** the description clearly names when the agent should fire.

---

## Generate the visual agent card

> **Hint:** _The agent card is how you and your team see the agent at a glance. It turns a config file into something shareable._

Paste this:

```
Now build me a single self-contained HTML file called agent-card.html that visualizes the agent I just installed. It should look like a trading card for a specialist. Include:

- The agent's name as a clear header
- A short tagline (rewrite the description as one punchy sentence)
- A "When to call me" section with 3-4 example trigger situations
- A "Tools I use" row with the tools as small pills
- A "Model" indicator
- A "How to invoke" section with the @agent-name syntax and one example call
- A "What I do not do" section to set boundaries
- Clean modern styling: good typography, generous whitespace, soft colors

Save it to my working directory. Use only inline CSS so the file works standalone.
```

Claude will write the file. Open `agent-card.html` in your browser. You should see a visually clean card that tells any teammate (or future-you) exactly what this agent does.

> **You're there when:** the HTML card renders in your browser and you would be comfortable sharing it with a teammate.

---

## Test the agent on real work

> **Hint:** _One good run is a coincidence. Three different inputs is a reliable specialist._

Try the agent two ways on real work:

**By name:**

```
@research-agent Prep me for a meeting with Acme Corp tomorrow. I am going in as a potential partner.
```

**By situation (auto-routed):**

```
I have a meeting with Acme Corp tomorrow and I want to be ready.
```

If the second invocation does not route to your agent, the description is too vague. Tell Claude:

```
I described a meeting prep situation but you did not route to the research agent. Update the description so that request would have triggered it.
```

Now run the agent on three different inputs. Different companies, different meeting types, different briefing styles. Read the outputs side by side. Ask yourself: _would I trust a teammate to use this agent without me standing next to them?_

If yes, the agent is ready. If no, name what drifted and ask Claude to tighten the system prompt.

> **You're done when:** three different real inputs all produce output you would trust a teammate to use without explanation.

---

## What You Just Did

You just promoted yourself from skill builder to agent manager. Specifically:

1. **Named a role**, not a task. That is the shift from skill thinking to agent thinking.
2. **Configured a real sub-agent** with name, description, tools, and model, installed in the right directory.
3. **Tuned the description** so Claude auto-routes work, not just when you call by name.
4. **Generated a shareable HTML card** so the agent is legible at a glance.
5. **Validated with real inputs** the way you would evaluate a new hire.

Every time you notice yourself playing the same role twice in one week, you now have a move. Turn the role into an agent. Main conversation stays clean. The specialist owns the work.

## What Not to Do

1. **Do not build an agent that does five jobs.** One role per agent. Split if it drifts.
2. **Do not give every agent every tool.** Narrow tools equal predictable behavior.
3. **Do not skip the description.** A vague description is a shelved agent.
4. **Do not confuse agents with skills.** One repeatable task equals a skill. A whole role equals an agent.
5. **Do not ship after one run.** Three real inputs before you trust it.

## Next Steps

When your first agent has earned its spot for a week:

- **Agent Teams** (hard) — Orchestrate multiple agents on one project.
- **Build a Lab** (medium) — Turn a workflow you do well into a shareable lab.
- **Build Your First Skill** (easy) — If you skipped it, this is the foundation.

## Reference

- [Official Claude Code sub-agents documentation](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [Agent Catalog](/docs/agent-catalog) — real examples of installed agents
- [What is a Skill?](/docs/what-is-a-skill) — the foundation under every agent

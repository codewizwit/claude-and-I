# Claude Code Playbook

A documentation-only repo — no source code, no builds, no tests. Everything is markdown.

## Structure

- `starters/` — Role-based CLAUDE.md templates. One per role. Each is a standalone file users copy to `~/.claude/CLAUDE.md`.
- `docs/` — Explainer pages. Practical, not tutorial-style. Each doc covers one topic and cross-links to related docs.
- `.claude/skills/` — Reusable skills (prompts in markdown with YAML frontmatter). Each skill lives in its own directory with a `SKILL.md`.
- `.claude/hooks/` — Shell scripts triggered by Claude Code events. Referenced by `.claude/settings.json`.
- `.claude/settings.json` — Project-level permissions, tool rules, and hook configuration.

## Conventions

- All content is markdown. No other file types except shell scripts in `.claude/hooks/` and JSON in `.claude/settings.json`.
- Starters use `[PLACEHOLDER]` syntax for values users need to fill in.
- Docs link to each other with relative paths (`what-is-a-skill.md` from within `docs/`, `docs/what-is-a-skill.md` from README).
- Skills use YAML frontmatter (`name`, `description`, `allowed-tools`, etc.) followed by markdown instructions.
- Hooks are bash scripts, executable (`chmod +x`), and use `$HOME/.claude/hooks/` as the install path in settings.json.
- The README is the entry point. Every new doc, skill, or hook must be linked from the README.
- Don't repeat content across files. If something is explained in a doc, the README links to it — it doesn't restate it.

## Voice

- Practical and direct. Write like you're explaining to a colleague, not writing a textbook.
- No jargon without context. If a term needs explanation, explain it inline or link to a doc that does.
- The audience ranges from non-technical (product owners, managers) to senior engineers. Default to accessible, add depth in dedicated docs.

## When Making Changes

- If you add a new starter, add a row to the README's role table.
- If you add a new skill, add a row to the README's skill table and ensure the skill directory is under `.claude/skills/`.
- If you add a new doc, add it to the README's Learn More section.
- If you add a new hook, add it to the README's settings table and update the install instructions.
- Keep docs cross-linked. If a new doc relates to an existing one, add a link in the Further Reading section of both.

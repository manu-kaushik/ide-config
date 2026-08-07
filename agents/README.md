# Agents

Agent configuration for Cursor: slash commands and skills for SOURCE.md and AGENTS.md.

## Commands

| Command   | File                 | Description |
| --------- | -------------------- | ----------- |
| `/source` | `commands/source.md` | Ensure SOURCE.md exists; optionally sync AGENTS.md and/or CLAUDE.md |

## Skills

| Skill    | Path             | Description |
| -------- | ---------------- | ----------- |
| `source` | `skills/source/` | Maintain SOURCE.md; sync AGENTS.md and/or CLAUDE.md per scope |

### source

| File        | Role |
| ----------- | ---- |
| `SOURCE.md` | **Required** — project facts |
| `AGENTS.md` | Agent workflow |
| `CLAUDE.md` | Claude Code guidance |

Run `/source`, `/source agents`, or `/source claude`. SOURCE.md is always included; omitting scope creates all guidance files.

## Setup: source

**1. Command** — copy `commands/source.md` to `~/.cursor/commands/`.

**2. Skill** — copy `skills/source/` to `~/.cursor/skills/source/`.

**3. Run** — open a project and invoke:

| Invocation | Creates in project root |
| ---------- | ----------------------- |
| `/source` | `SOURCE.md`, `AGENTS.md`, `CLAUDE.md` |
| `/source agents` | `SOURCE.md`, `AGENTS.md` |
| `/source claude` | `SOURCE.md`, `CLAUDE.md` |

Re-runs refresh SOURCE.md and prepend SOURCE pointers to existing files without erasing content.

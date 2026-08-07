# Agents

Agent configuration for Cursor: commands and skills for SOURCE.md and AGENTS.md.

## Commands

| Command           | File                         | Description |
| ----------------- | ---------------------------- | ----------- |
| `/commit-message` | `commands/commit-message.md` | Generate a conventional commit message for staged changes (does not commit) |

## Skills

| Skill    | Path             | Description |
| -------- | ---------------- | ----------- |
| `source` | `skills/source/` | SOURCE.md carries project truth across all chats; agents update it when facts change |

### source

SOURCE.md is the **persistent project record** — decisions, architecture, deferrals, focus. Chats are temporary; SOURCE.md is not. AGENTS.md and CLAUDE.md enforce read-first / update-when-changed behavior.

| File        | Role |
| ----------- | ---- |
| `SOURCE.md` | **Required** — whole project on disk |
| `AGENTS.md` | Agent workflow |
| `CLAUDE.md` | Claude Code guidance |

Run `/source`, `/source agents`, or `/source claude`. SOURCE.md is always included; omitting scope creates all guidance files.

## Setup: source

**1. Skill** — copy `skills/source/` to `~/.cursor/skills/source/`.

**2. Run** — open a project and invoke `/source`:

| Invocation | Creates in project root |
| ---------- | ----------------------- |
| `/source` | `SOURCE.md`, `AGENTS.md`, `CLAUDE.md` |
| `/source agents` | `SOURCE.md`, `AGENTS.md` |
| `/source claude` | `SOURCE.md`, `CLAUDE.md` |

Re-runs bootstrap from the repo, merge durable project knowledge, and prepend SOURCE pointers without erasing content. During normal work, agents update SOURCE.md when project facts change — not only when `/source` runs.

## Setup: commit-message

Copy `commands/commit-message.md` to `~/.cursor/commands/`.

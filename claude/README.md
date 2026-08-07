# Claude

Slash commands and skills for Claude Code.

## Commands

| Command           | File                         | Description |
| ----------------- | ---------------------------- | ----------- |
| `/commit-message` | `commands/commit-message.md` | Generate a conventional commit message for staged changes (does not commit) |
| `/source`         | `commands/source.md`         | Ensure SOURCE.md exists as the persistent project record; sync guidance files |

## Skills

| Skill    | Path             | Description |
| -------- | ---------------- | ----------- |
| `source` | `skills/source/` | SOURCE.md carries project truth across all chats; agents update it when facts change |

SOURCE.md is the **persistent project record** — decisions, architecture, deferrals, focus. Chats are temporary; SOURCE.md is not.

Run `/source`, `/source agents`, or `/source claude`. SOURCE.md is always included; omitting scope creates all guidance files.

## Setup: source

**1. Command** — copy `commands/source.md` to `~/.claude/commands/`.

**2. Skill** — copy `skills/source/` to `~/.claude/skills/source/`.

**3. Run** — open a project and invoke:

| Invocation | Creates in project root |
| ---------- | ----------------------- |
| `/source` | `SOURCE.md`, `AGENTS.md`, `CLAUDE.md` |
| `/source agents` | `SOURCE.md`, `AGENTS.md` |
| `/source claude` | `SOURCE.md`, `CLAUDE.md` |

Re-runs bootstrap from the repo, merge durable project knowledge, and prepend SOURCE pointers without erasing content. During normal work, agents update SOURCE.md when project facts change — not only when `/source` runs.

## Setup: commit-message

Copy `commands/commit-message.md` to `~/.claude/commands/`.

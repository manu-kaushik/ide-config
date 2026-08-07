# Claude

Slash commands and skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and Cursor.

## Commands

| Command           | File                         | Description |
| ----------------- | ---------------------------- | ----------- |
| `/commit-message` | `commands/commit-message.md` | Generate a conventional commit message for staged changes (does not commit) |
| `/source`         | `commands/source.md`         | Ensure SOURCE.md exists and AGENTS.md / CLAUDE.md point to it |

## Skills

| Skill    | Path             | Description |
| -------- | ---------------- | ----------- |
| `source` | `skills/source/` | Maintain SOURCE.md and sync AGENTS.md / CLAUDE.md (never erases existing content) |

### source

| File        | Role |
| ----------- | ---- |
| `SOURCE.md` | Project facts: stack, commands, architecture, decisions |
| `AGENTS.md` | Agent workflow and boundaries (Cursor, Codex, others) |
| `CLAUDE.md` | Claude Code guidance; imports SOURCE.md via `@SOURCE.md` |

Reference files in this directory. Copy to your environment when needed.

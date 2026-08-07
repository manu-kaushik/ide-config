Ensure `SOURCE.md` is the project source of truth and that `AGENTS.md` and `CLAUDE.md` exist and point to it.

| File        | Role |
| ----------- | ---- |
| `SOURCE.md` | **Primary** — stack, commands, architecture, decisions |
| `AGENTS.md` | Agent workflow; must prioritize SOURCE.md (Cursor, Codex, others) |
| `CLAUDE.md` | Claude guidance; must prioritize SOURCE.md via `@SOURCE.md` |

Templates: `claude/skills/source/templates/` (relative to this repository).

## Rules

1. **Never erase existing content.**
2. **SOURCE.md first** — create if missing; prepend marker if absent; append missing sections; fill empty fields from codebase inspection only.
3. **AGENTS.md / CLAUDE.md** — create if missing; prepend `*.prepend.md` if marker absent; preserve all existing content below.
4. **Facts in SOURCE.md only** — guidance files point to it, do not duplicate it.
5. **Idempotent** — skip if `source:` marker already present.
6. Summarize: created, updated, unchanged, and SOURCE.md sections still needing input.

Read `claude/skills/source/SKILL.md` for the full workflow.

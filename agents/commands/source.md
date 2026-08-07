Ensure `SOURCE.md` is the project source of truth. Optionally sync `AGENTS.md` and/or `CLAUDE.md` based on scope.

**Scope.** SOURCE.md is always included.

| Invocation | Also creates / updates |
| ---------- | ---------------------- |
| `/source` | `AGENTS.md` + `CLAUDE.md` |
| `/source agents` | `AGENTS.md` |
| `/source claude` | `CLAUDE.md` |

## Templates

All templates are in the source skill's `templates/` directory (included when copying `skills/source/`).

## Rules

1. **Never erase existing content.**
2. **SOURCE.md always** — create if missing; prepend marker if absent; append missing sections; fill empty fields from codebase inspection only.
3. **AGENTS.md** — when scope is omitted or `agents`.
4. **CLAUDE.md** — when scope is omitted or `claude`.
5. **Facts in SOURCE.md only** — guidance files point to it, do not duplicate it.
6. **Idempotent** — skip if `source:` marker already present.
7. Summarize: scope applied, files created/updated/unchanged, SOURCE.md sections still needing input.

Read the source skill's `SKILL.md` for the full workflow.

Ensure SOURCE.md exists as the **persistent project record** for this repository. Optionally sync AGENTS.md and/or CLAUDE.md so every chat reads SOURCE.md first.

SOURCE.md carries project truth across all chats — not chat history, not session summaries.

**Scope.** SOURCE.md is always included.

| Invocation | Also creates / updates |
| ---------- | ---------------------- |
| `/source` | `AGENTS.md` + `CLAUDE.md` |
| `/source agents` | `AGENTS.md` |
| `/source claude` | `CLAUDE.md` |

## Rules

1. **Never erase existing SOURCE.md content.**
2. **Bootstrap** — fill empty fields from the repo (README, manifests, layout). Do not overwrite non-empty values.
3. **Merge durable knowledge** — append Decisions, Deferred, Architecture from current context; rewrite Current focus only when focus shifted. Skip chat noise.
4. **Guidance files** — create or prepend SOURCE pointer when scope includes them; preserve existing content.
5. **Facts in SOURCE.md only** — AGENTS.md and CLAUDE.md enforce behavior, not duplicate facts.
6. **Idempotent** — skip if `source:` marker already present.
7. Summarize briefly (≤5 lines): scope, one-line status per project file, SOURCE.md gaps still needing input.

Read the source skill's `SKILL.md` for the full workflow.

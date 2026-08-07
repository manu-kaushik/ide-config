---
name: source
description: Ensure SOURCE.md exists and is current; create or update AGENTS.md and/or CLAUDE.md to point to it. Use when the user runs /source, asks to init or sync SOURCE.md, or set up project context. Optional scope is agents or claude; omit scope for all files. SOURCE is always required.
---

# Source

Maintain the project's source-of-truth doc and optionally keep agent guidance files aligned with it.

| File        | Role | Scope | Tools |
| ----------- | ---- | ----- | ----- |
| `SOURCE.md` | **Required** — stack, commands, architecture, decisions | always | all |
| `AGENTS.md` | Agent workflow and boundaries | default, `agents` | Cursor, Codex, others |
| `CLAUDE.md` | Claude-specific guidance | default, `claude` | Claude Code |

## Scope

**SOURCE.md is always included.**

| Invocation | Action |
| ---------- | ------ |
| `/source` | SOURCE.md + AGENTS.md + CLAUDE.md |
| `/source agents` | SOURCE.md + AGENTS.md |
| `/source claude` | SOURCE.md + CLAUDE.md |

Parse scope from the prompt or command argument. No scope means all guidance files.

## Templates

All templates live in [templates/](templates/).

| File | Template |
| ---- | -------- |
| `SOURCE.md` | `templates/SOURCE.md` |
| `AGENTS.md` | `templates/AGENTS.md` |
| `CLAUDE.md` | `templates/CLAUDE.md` |

## Workflow

1. **Confirm target directory** — workspace root unless the user specifies another path.

2. **Determine scope** — no argument → all files; `agents` → AGENTS.md only; `claude` → CLAUDE.md only. SOURCE.md always runs.

3. **Resolve filenames** — prefer `SOURCE.md`, `AGENTS.md`, `CLAUDE.md`. Treat lowercase variants as the same file; do not create duplicates.

4. **SOURCE.md** (always)
   - **Missing** → create from [templates/SOURCE.md](templates/SOURCE.md).
   - **Exists** → never erase or replace content. Prepend [templates/SOURCE.prepend.md](templates/SOURCE.prepend.md) if marker `source:` is absent. Append template sections not already present. Fill empty table cells and placeholders from codebase inspection only.

5. **Populate SOURCE.md** — inspect the repository and update empty or placeholder sections:
   - `README.md`, manifests, `Makefile`, CI configs
   - Directory layout and scripts
   - Do not invent facts; use `<!-- TODO: confirm -->` when uncertain
   - Do not overwrite non-empty values

6. **AGENTS.md** (when scope is default or `agents`)
   - **Missing** → create from [templates/AGENTS.md](templates/AGENTS.md).
   - **Exists** → preserve all content. Prepend [templates/AGENTS.prepend.md](templates/AGENTS.prepend.md) if marker absent.

7. **CLAUDE.md** (when scope is default or `claude`)
   - **Missing** → create from [templates/CLAUDE.md](templates/CLAUDE.md).
   - **Exists** → preserve all content. Prepend [templates/CLAUDE.prepend.md](templates/CLAUDE.prepend.md) if marker absent.

8. **Separation of concerns** — facts live in SOURCE.md only. Guidance files prioritize SOURCE.md; do not duplicate facts.

9. **Idempotent** — skip prepending when marker is present. Report created / updated / unchanged / skipped per file.

10. **Summarize** — scope applied, files touched, SOURCE.md sections filled vs needing input.

## Maintenance

Project facts change → update **SOURCE.md**. Re-run `/source` to refresh. Agent behavior changes → edit AGENTS.md or CLAUDE.md directly.

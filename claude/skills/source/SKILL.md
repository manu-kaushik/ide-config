---
name: source
description: Ensure SOURCE.md exists and is current; create or update AGENTS.md and CLAUDE.md to point to it. Use when the user runs /source, asks to init or sync SOURCE.md, or set up project context for Cursor and Claude Code.
---

# Source

Maintain the project's source-of-truth doc and keep agent guidance files aligned with it.

| File        | Role | Cursor | Claude Code |
| ----------- | ---- | ------ | ----------- |
| `SOURCE.md` | **Primary** — stack, commands, architecture, decisions | Linked from guidance files | `@SOURCE.md` import |
| `AGENTS.md` | Agent workflow and boundaries; points to SOURCE.md | Read at project root | Fallback when no CLAUDE.md |
| `CLAUDE.md` | Claude-specific guidance; points to SOURCE.md | Read at project root | Primary instructions file |

Templates: [templates/](templates/) in this skill directory. Prepend snippets: `*.prepend.md`.

## Workflow

Run on every invocation — create missing files, sync existing ones, never erase content.

1. **Confirm target directory** — workspace root unless the user specifies another path.

2. **Resolve filenames** — prefer `SOURCE.md`, `AGENTS.md`, `CLAUDE.md`. Treat lowercase variants as the same file; do not create duplicates.

3. **SOURCE.md** (always first)
   - **Missing** → create from [templates/SOURCE.md](templates/SOURCE.md).
   - **Exists** → never erase or replace content. Prepend [templates/SOURCE.prepend.md](templates/SOURCE.prepend.md) if marker `source:` is absent. Append template sections not already present. Fill empty table cells and placeholders from codebase inspection only.

4. **Populate SOURCE.md** — inspect the repository and update empty or placeholder sections:
   - `README.md`, manifests (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`), `Makefile`, CI configs
   - Directory layout and scripts
   - Do not invent facts; use `<!-- TODO: confirm -->` when uncertain
   - Do not overwrite non-empty values

5. **AGENTS.md** — ensure it exists and points to SOURCE.md
   - **Missing** → create from [templates/AGENTS.md](templates/AGENTS.md).
   - **Exists** → preserve all content. Prepend [templates/AGENTS.prepend.md](templates/AGENTS.prepend.md) if marker absent.

6. **CLAUDE.md** — ensure it exists and points to SOURCE.md
   - **Missing** → create from [templates/CLAUDE.md](templates/CLAUDE.md).
   - **Exists** → preserve all content. Prepend [templates/CLAUDE.prepend.md](templates/CLAUDE.prepend.md) if marker absent.

7. **Separation of concerns** — facts live in SOURCE.md only. AGENTS.md and CLAUDE.md hold agent workflow and boundaries; they must prioritize SOURCE.md, not duplicate it.

8. **Idempotent** — skip prepending when marker is present. Report created / updated / unchanged per file.

9. **Summarize** — what was created or updated, SOURCE.md sections filled vs still needing input, and whether guidance files now point to SOURCE.md.

## Maintenance

Project facts change → update **SOURCE.md**. Re-run `/source` to refresh inferred sections and verify guidance files still point here. Agent behavior changes → edit AGENTS.md or CLAUDE.md directly.

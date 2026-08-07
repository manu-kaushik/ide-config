# Claude

Instructions for Claude Code (and compatible tools) in this repository.

## Project context

@SOURCE.md

Read [SOURCE.md](SOURCE.md) for project facts. Prefer SOURCE.md over this file or codebase inference when they conflict.

## Agent behavior

- Stay aligned with [AGENTS.md](AGENTS.md) for workflow and code-change expectations.
- Prefer editing existing files over creating new ones unless the task requires it.
- Ask before destructive git operations or credential-related changes.

## Claude-specific

<!-- Optional: slash commands, skills, MCP servers, tool permissions -->

| Item     | Location                                      |
| -------- | --------------------------------------------- |
| Commands | `.claude/commands/` or `~/.claude/commands/`  |
| Skills   | `.claude/skills/` or `~/.cursor/skills/`      |

## Boundaries

See AGENTS.md. Add Claude-only overrides below if needed.

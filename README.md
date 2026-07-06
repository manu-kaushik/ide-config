# IDE Config

Editor and tooling configuration for VS Code, Cursor, and Claude Code.

| Tool    | Contents                               | Documentation                    |
| ------- | -------------------------------------- | -------------------------------- |
| VS Code | `code/profiles/`, `code/settings.json` | [code/README.md](code/README.md) |
| Cursor  | `cursor/profiles/`                     | [cursor/README.md](cursor/README.md) |
| Claude  | `claude/commands/`                     | [claude/README.md](claude/README.md) |

## Usage

**VS Code profiles:** `Ctrl+Shift+P` → **Profiles: Import Profile** → select a file from `code/profiles/`.

**VS Code user settings:** Apply [code/settings.json](code/settings.json) via `Ctrl+Shift+P` → **Preferences: Open User Settings (JSON)**.

**Cursor profiles:** `Ctrl+Shift+P` → **Profiles: Import Profile** → select a file from `cursor/profiles/`.

**Claude commands:** Install command files from `claude/commands/` to `~/.claude/commands/` (global) or `.claude/commands/` (project).

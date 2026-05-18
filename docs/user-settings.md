# User Settings

Global settings stored in `settings.json`. These apply to **every profile** as the base layer. Profile-specific settings override these where they conflict.

**File:** `settings.json`

---

## Setting Reference

### Window & Workbench

| Setting | Value | Reason |
|---------|-------|--------|
| `window.commandCenter` | `true` | Shows the command palette search bar in the title bar |
| `window.newWindowProfile` | `"Default"` | New windows open with the Default profile |
| `terminal.integrated.defaultProfile.windows` | `"Git Bash"` | Uses Git Bash instead of PowerShell/CMD |
| `workbench.iconTheme` | `"material-icon-theme"` | Material Design file icons |
| `workbench.editor.highlightModifiedTabs` | `true` | Modified (unsaved) tabs show a dot indicator |

### Files & Git

| Setting | Value | Reason |
|---------|-------|--------|
| `files.autoSave` | `"afterDelay"` | Auto-saves after a short delay |
| `git.openRepositoryInParentFolders` | `"never"` | Prevents VSCode from walking up to find a git repo in parent directories |

### Editor Intelligence

| Setting | Value | Reason |
|---------|-------|--------|
| `editor.stickyScroll.enabled` | `true` | Keeps the current class/function signature pinned at the top while scrolling |
| `editor.bracketPairColorization.enabled` | `true` | Colors matching bracket pairs (built-in, no extension needed) |
| `editor.guides.bracketPairs` | `"active"` | Draws a vertical line for the active bracket pair |
| `editor.inlayHints.enabled` | `"on"` | Shows inline type hints and parameter names |
| `editor.suggest.preview` | `true` | Previews the selected completion inline before accepting |

### Formatting & Code Actions

| Setting | Value | Reason |
|---------|-------|--------|
| `editor.formatOnSave` | `true` | Runs the file's configured formatter on every save |
| `editor.codeActionsOnSave` | `source.fixAll` + `source.organizeImports` | Auto-fixes linting errors and sorts imports on save (no-op for languages that don't support it) |

### Language-Specific Defaults

| Language | Setting | Value |
|----------|---------|-------|
| Markdown | `editor.wordWrap` | `"on"` — wraps long lines |
| Markdown | `editor.quickSuggestions` | Enabled for text, off for comments/strings |
| YAML | `editor.tabSize` | `2` |
| YAML | `editor.formatOnSave` | `true` |
| JSON | `editor.defaultFormatter` | VSCode built-in |
| JSONC | `editor.defaultFormatter` | Prettier |

### Claude Code

| Setting | Value | Reason |
|---------|-------|--------|
| `claudeCode.preferredLocation` | `"sidebar"` | Claude Code docks to the sidebar instead of the panel |

---

## Notes

- **Settings vs Profile settings**: If you want a setting to apply everywhere unconditionally, put it here. If it should only apply within a specific language or project type, put it in the relevant profile's `[language]` block instead.
- **How to edit**: `Ctrl+Shift+P → Preferences: Open User Settings (JSON)` opens the live file. Changes here take effect immediately without reloading.
- **Windsurf**: `settings.json` inside the `windsurf/` folder disables Windsurf agent features (ACP, Devin). Merge into your user settings if using Windsurf for inline completion.

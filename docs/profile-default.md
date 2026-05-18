# Profile: Default

General-purpose profile for miscellaneous projects, config editing, scripting, or anything that doesn't fit a specific profile. Also the profile used when VSCode opens a new window (`window.newWindowProfile: "Default"`).

**File:** `profiles/Default.code-profile`

---

## Extensions (14)

### Universal Tools
| Extension | ID | Purpose |
|-----------|----|---------|
| GitLens | `eamodio.gitlens` | Git blame, history, diff, PR integration |
| Error Lens | `usernamehw.errorlens` | Inline errors/warnings on the same line |
| Todo Tree | `gruntfuggly.todo-tree` | Scans for TODO/FIXME/HACK and shows them in a tree |
| Path Intellisense | `christian-kohler.path-intellisense` | Autocomplete file paths in code |
| Code Spell Checker | `streetsidesoftware.code-spell-checker` | Spell check across code, strings, and comments |
| Image Preview | `kisstkondoros.vscode-gutter-preview` | Shows image preview in the gutter |
| Color Highlight | `naumovs.color-highlight` | Highlights color values inline |
| Material Icon Theme | `pkief.material-icon-theme` | File/folder icons |

### Markdown & YAML
| Extension | ID | Purpose |
|-----------|----|---------|
| Markdown All in One | `yzhang.markdown-all-in-one` | Preview, shortcuts, auto TOC, list formatting |
| YAML | `redhat.vscode-yaml` | Schema validation, autocomplete for YAML |

### Containers & Remote
| Extension | ID | Purpose |
|-----------|----|---------|
| Dev Containers | `ms-vscode-remote.remote-containers` | Run VSCode fully inside a Docker container |
| WSL | `ms-vscode-remote.remote-wsl` | Develop inside Windows Subsystem for Linux |
| Docker | `ms-azuretools.vscode-docker` | Dockerfile/compose support, container management |
| Container Tools | `ms-azuretools.vscode-containers` | Extended container management UI |

---

## Settings

```json
{
  "window.commandCenter": true,
  "window.newWindowProfile": "Default",
  "terminal.integrated.defaultProfile.windows": "Git Bash",
  "workbench.iconTheme": "material-icon-theme",
  "files.autoSave": "afterDelay",
  "git.openRepositoryInParentFolders": "never",
  "editor.stickyScroll.enabled": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": "active",
  "editor.inlayHints.enabled": "on",
  "editor.suggest.preview": true,
  "workbench.editor.highlightModifiedTabs": true,
  "[markdown]": {
    "editor.wordWrap": "on",
    "editor.quickSuggestions": { "other": true, "comments": false, "strings": false }
  },
  "[yaml]": {
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.formatOnSave": true
  }
}
```

---

## Keybindings

| Key | Command | Description |
|-----|---------|-------------|
| `Alt+C` | `claude-vscode.sidebar.open` | Open Claude Code in sidebar |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal |

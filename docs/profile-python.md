# Profile: Python

Python development — scripts, web backends (Django/FastAPI/Flask), data work, and Jupyter notebooks. Ruff handles both formatting and linting in one tool.

**File:** `profiles/Python.code-profile`

---

## Extensions (19)

### Python Core
| Extension       | ID                         | Purpose                                                         |
| --------------- | -------------------------- | --------------------------------------------------------------- |
| Python          | `ms-python.python`         | Python language support, virtual env management, test discovery |
| Pylance         | `ms-python.vscode-pylance` | Fast type checker and IntelliSense (replaces Pyright)           |
| Python Debugger | `ms-python.debugpy`        | `launch.json`-based debugging, breakpoints, watch variables     |

### Formatting & Linting
| Extension | ID                   | Purpose                                                                 |
| --------- | -------------------- | ----------------------------------------------------------------------- |
| Ruff      | `charliermarsh.ruff` | All-in-one linter + formatter. Replaces flake8, black, isort, pyupgrade |

> Ruff runs on save and also auto-organizes imports. No need for separate Black, isort, or flake8 extensions.

### Notebooks
| Extension | ID                   | Purpose                                                               |
| --------- | -------------------- | --------------------------------------------------------------------- |
| Jupyter   | `ms-toolsai.jupyter` | Run `.ipynb` notebooks inline, cell-by-cell output, variable explorer |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

---

## Settings

### Python formatting (PEP 8 / Ruff defaults)
```json
{
  "[python]": {
    "editor.tabSize": 4,
    "editor.insertSpaces": true,
    "editor.formatOnSave": true,
    "editor.rulers": [88],
    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.codeActionsOnSave": {
      "source.organizeImports": "explicit",
      "source.fixAll": "explicit"
    }
  }
}
```

| Setting          | Value    | Reason                                              |
| ---------------- | -------- | --------------------------------------------------- |
| Indent           | 4 spaces | PEP 8                                               |
| Line limit       | 88 chars | Black/Ruff default (slightly wider than PEP 8's 79) |
| Format on save   | Yes      | Ruff formats and fixes on every save                |
| Organize imports | On save  | Ruff sorts and deduplicates imports                 |

### Editor
```json
{
  "editor.stickyScroll.enabled": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": "active",
  "editor.inlayHints.enabled": "on",
  "editor.suggest.preview": true,
  "workbench.editor.highlightModifiedTabs": true
}
```

---

## Keybindings

| Key        | Command                           | Description                 |
| ---------- | --------------------------------- | --------------------------- |
| `Alt+C`    | `claude-vscode.sidebar.open`      | Open Claude Code in sidebar |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal          |

---

## Notes

- **Virtual environments**: Python extension auto-detects `.venv`, `venv`, `env` folders. Select the interpreter with `Ctrl+Shift+P → Python: Select Interpreter`.
- **Ruff vs Black**: Ruff is a superset — it formats like Black and lints like flake8/isort combined, but runs ~100x faster. No need to install Black or isort separately.
- **Jupyter**: Works with any kernel the Python extension manages. Cell output renders inline; variables are inspectable via the Jupyter Variables panel.
- **Dockerized projects**: Use Dev Containers to attach to the Python container. Pylance and Ruff will then see the container's installed packages, not your host's.
- **Type checking strictness**: Pylance type checking mode defaults to `basic`. Change to `strict` per-project in `.vscode/settings.json` with `"python.analysis.typeCheckingMode": "strict"`.

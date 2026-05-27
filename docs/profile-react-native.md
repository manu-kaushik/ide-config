# Profile: React Native

Cross-platform mobile development with React Native. Covers bare workflow and Expo, with NativeWind (Tailwind) for styling.

**File:** `profiles/ReactNative.code-profile`

---

## Extensions (21)

### React Native Core
| Extension | ID | Purpose |
|-----------|----|---------|
| React Native Tools | `msjsdiag.vscode-react-native` | Run, debug, and inspect React Native apps |
| Expo Tools | `expo.vscode-expo-tools` | Expo config autocomplete, app.json support |

### Frontend Tooling
| Extension | ID | Purpose |
|-----------|----|---------|
| ES7+ React Snippets | `dsznajder.es7-react-js-snippets` | React/JSX snippets (`rfc`, `rafce`, hooks) |
| ESLint | `dbaeumer.vscode-eslint` | JS/TS linting via project `.eslintrc` |
| Prettier | `esbenp.prettier-vscode` | Formatter for JS, TS, JSX, TSX |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss` | Class autocomplete for NativeWind |
| Auto Rename Tag | `formulahendry.auto-rename-tag` | Renames matching JSX closing tag |
| npm Intellisense | `christian-kohler.npm-intellisense` | Autocomplete npm package names in imports |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

---

## Settings

### Per-language formatting

All JS/TS family files use **Prettier**, **2 spaces** indent, **100 char** line limit.

| Language | Indent | Line limit | Formatter |
|----------|--------|-----------|-----------|
| JavaScript | 2 spaces | 100 chars | Prettier |
| TypeScript | 2 spaces | 100 chars | Prettier |
| JSX | 2 spaces | 100 chars | Prettier |
| TSX | 2 spaces | 100 chars | Prettier |

### TypeScript
```json
{
  "javascript.updateImportsOnFileMove.enabled": "always"
}
```

---

## Keybindings

| Key | Command | Description |
|-----|---------|-------------|
| `Alt+C` | `claude-vscode.sidebar.open` | Open Claude Code in sidebar |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal |

---

## Notes

- **Bare vs Expo**: Both workflows are supported. React Native Tools handles bare workflow debugging; Expo Tools handles Expo-managed projects.
- **NativeWind**: Tailwind CSS IntelliSense works with NativeWind class autocomplete in JSX/TSX files.
- **Debugging**: React Native Tools requires a `launch.json` for device/emulator debugging. Use `Ctrl+Shift+P → Debug: Open launch.json` to create one.
- **Dockerized Metro**: Use Dev Containers to run the Metro bundler inside a container if your project requires a specific Node version.

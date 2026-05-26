# Profile: Frontend

JavaScript/TypeScript frontend development. Covers React, Vue, Svelte, Astro, and plain TS/JS. Prettier handles all formatting; ESLint handles linting.

**File:** `profiles/Frontend.code-profile`

---

## Extensions (25)

### Language Servers & Linting
| Extension                       | ID                                 | Purpose                                                       |
| ------------------------------- | ---------------------------------- | ------------------------------------------------------------- |
| ESLint                          | `dbaeumer.vscode-eslint`           | JS/TS linting, integrates with project's `.eslintrc`          |
| JavaScript & TypeScript Nightly | `ms-vscode.vscode-typescript-next` | Latest TypeScript compiler for cutting-edge TS features       |
| Svelte for VS Code              | `svelte.svelte-vscode`             | Svelte language server — completions, diagnostics, formatting |
| Astro                           | `astro-build.astro-vscode`         | Astro file support — `.astro` syntax, components              |

### Formatting
| Extension | ID                       | Purpose                                   |
| --------- | ------------------------ | ----------------------------------------- |
| Prettier  | `esbenp.prettier-vscode` | Formatter for JS, TS, JSX, TSX, CSS, JSON |

### Productivity
| Extension                 | ID                                  | Purpose                                               |
| ------------------------- | ----------------------------------- | ----------------------------------------------------- |
| ES7+ React Snippets       | `dsznajder.es7-react-js-snippets`   | `rfc`, `rafce`, `useState`, hooks snippets            |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss`         | Class autocomplete, hover preview, sorting            |
| Auto Rename Tag           | `formulahendry.auto-rename-tag`     | Renames matching HTML/JSX closing tag                 |
| HTML CSS Support          | `ecmel.vscode-html-css`             | CSS class/id autocomplete in HTML files               |
| npm Intellisense          | `christian-kohler.npm-intellisense` | Autocomplete npm package names in `import` statements |
| Import Cost               | `wix.vscode-import-cost`            | Shows the bundle size of each import inline           |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

---

## Settings

### Per-language formatting

All JS/TS family files use **Prettier** as the formatter, **2 spaces** indent, **100 char** line limit.

| Language   | Indent   | Line limit | Formatter       |
| ---------- | -------- | ---------- | --------------- |
| JavaScript | 2 spaces | 100 chars  | Prettier        |
| TypeScript | 2 spaces | 100 chars  | Prettier        |
| JSX        | 2 spaces | 100 chars  | Prettier        |
| TSX        | 2 spaces | 100 chars  | Prettier        |
| CSS        | 2 spaces | —          | Prettier        |
| HTML       | 2 spaces | —          | —               |
| JSON       | —        | —          | VSCode built-in |
| JSONC      | —        | —          | Prettier        |

Format on save is enabled globally for this profile (`"editor.formatOnSave": true`).

### TypeScript
```json
{
  "javascript.updateImportsOnFileMove.enabled": "always",
  "svelte.enable-ts-plugin": true
}
```
> `updateImportsOnFileMove` automatically fixes all imports when you move or rename a file — equivalent to WebStorm's import tracking.

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

- **Prettier config**: Prettier reads from `prettier.config.js` / `.prettierrc` in the project root. Profile settings are overridden by project config.
- **ESLint config**: ESLint reads from the project's `.eslintrc.*`. The extension just surfaces the results — rules come from the project.
- **Import Cost**: Shows gzipped bundle size next to each import. Grayed-out means the package was not found locally (run `npm install` first).
- **Svelte**: `svelte.enable-ts-plugin: true` enables full TypeScript support inside `.svelte` files.
- **Dockerized projects**: Use Dev Containers to run the Node.js/Bun/Deno LSP inside the container so it sees the exact `node_modules` and runtime version.

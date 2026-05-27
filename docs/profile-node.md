# Profile: Node

Backend JavaScript/TypeScript development. Covers Express, Fastify, NestJS, and similar Node.js frameworks. Includes ORM support and environment file handling.

**File:** `profiles/Node.code-profile`

---

## Extensions (20)

### Language & Linting
| Extension | ID | Purpose |
|-----------|----|---------|
| ESLint | `dbaeumer.vscode-eslint` | JS/TS linting via project `.eslintrc` |
| JavaScript & TypeScript Nightly | `ms-vscode.vscode-typescript-next` | Latest TypeScript compiler for cutting-edge TS features |

### Formatting
| Extension | ID | Purpose |
|-----------|----|---------|
| Prettier | `esbenp.prettier-vscode` | Formatter for JS and TS files |

### Productivity
| Extension | ID | Purpose |
|-----------|----|---------|
| npm Intellisense | `christian-kohler.npm-intellisense` | Autocomplete npm package names in imports |
| Import Cost | `wix.vscode-import-cost` | Shows bundle size of each import inline |
| DotENV | `mikestead.dotenv` | Syntax highlighting for `.env` files |
| Prisma | `prisma.prisma` | Prisma schema syntax, formatting, and autocomplete |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

---

## Settings

### Per-language formatting

| Language | Indent | Line limit | Formatter |
|----------|--------|-----------|-----------|
| JavaScript | 2 spaces | 100 chars | Prettier |
| TypeScript | 2 spaces | 100 chars | Prettier |

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

- **Prisma**: Extension handles `.prisma` schema files — formatting, autocomplete, and jump-to-definition for models. Run `npx prisma generate` from the terminal to sync the client.
- **Dockerized Node**: Use Dev Containers to attach VSCode to the Node container. The language server will then resolve `node_modules` from inside the container.
- **NestJS**: Works well out of the box — TypeScript Nightly gives full decorator support, ESLint handles NestJS-specific rules if configured in the project.

# Cursor Profiles

Profiles for [Cursor IDE](https://cursor.com) — each bundles extensions, settings, and keybindings for a specific project type. Switch profiles from the bottom-left avatar icon or via `Ctrl+Shift+P → Profiles: Switch Profile`.

For VS Code, see [VS Code Profiles](code-profiles.md).

**Import:** `Ctrl+Shift+P` → **Profiles: Import Profile** → select a file from `cursor-profiles/`.

---

## Profiles

| Profile      | File                                     | Purpose                                              |
| ------------ | ---------------------------------------- | ---------------------------------------------------- |
| Default      | `cursor-profiles/Default.code-profile`     | Catch-all for misc projects                          |
| Laravel      | `cursor-profiles/Laravel.code-profile`     | PHP · Laravel · Livewire · Inertia/React             |
| Flutter      | `cursor-profiles/Flutter.code-profile`     | Dart · Flutter · Android (Java/Kotlin) · iOS (Swift) |
| Frontend     | `cursor-profiles/Frontend.code-profile`    | React · Vue · Svelte · Astro · TypeScript            |
| React Native | `cursor-profiles/ReactNative.code-profile` | React Native · Expo · NativeWind                     |
| Node         | `cursor-profiles/Node.code-profile`        | Node.js · Express · NestJS · Prisma                  |
| Python       | `cursor-profiles/Python.code-profile`      | Python · Ruff · Cursor Pyright                       |

---

## Default

General-purpose profile for miscellaneous projects, config editing, and scripting. Also used when opening a new window (`window.newWindowProfile: "Default"`).

### Extensions (13)

**Formatting:** Prettier

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, DotENV, Docker, Container Tools

### Settings highlights

- Git Bash as default terminal on Windows
- Format on save with Prettier for JS/TS/HTML/CSS/JSON
- Sticky scroll, bracket pair colorization, inlay hints
- YAML: 2-space indent, format on save
- Markdown: word wrap, quick suggestions

---

## Python

Python development — scripts, web backends (Django/FastAPI/Flask), and data work. Ruff handles formatting and linting; Cursor Pyright provides the language server.

### Extensions (15)

**Python:** Cursor Pyright, Ruff

**Formatting:** Prettier (for JS/TS files in mixed projects)

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, DotENV, Docker, Container Tools

### Settings highlights

- Python: 4-space indent, 88-char ruler, Ruff as formatter, organize imports on save
- `python.languageServer: "None"` — uses Cursor Pyright for IntelliSense

---

## Node

Backend JavaScript/TypeScript development. Covers Express, Fastify, NestJS, and similar Node.js frameworks.

### Extensions (17)

**Language & linting:** ESLint

**Formatting:** Prettier

**Productivity:** npm Intellisense, Import Cost, Prisma, DotENV

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, Docker, Container Tools

### Settings highlights

- Format on save with Prettier for JS/TS
- ESLint fix-all and organize imports on save

---

## Laravel

Full-stack Laravel development — PHP backend, Blade templates, Livewire components, and Inertia.js with React on the frontend.

### Extensions (25)

**PHP & Laravel:** Intelephense, Laravel, Laravel Blade, PHP Debug, PHP CS Fixer, PHP DocBlocker, PHP Namespace Resolver, Better PHPUnit

**Frontend:** ES7+ React Snippets, Tailwind CSS IntelliSense, Prettier, Auto Rename Tag, HTML CSS Support

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, DotENV, Docker, Container Tools

### Settings highlights

- Intelephense configured for PHP 8.2 and Laravel stubs
- PHP formatted with PHP CS Fixer on save
- Prettier for JS/JSX/CSS in Inertia/React files

---

## Flutter

Cross-platform mobile development with Dart, Flutter, and native platform code (Kotlin, Swift, Java).

### Extensions (20)

**Flutter & Dart:** Dart, Flutter, Awesome Flutter Snippets

**Native platforms:** Kotlin, Swift, Java (Red Hat), Gradle

**Formatting:** Prettier

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Image Preview, DotENV, Docker, Container Tools

---

## Frontend

JavaScript/TypeScript frontend development. Covers React, Vue, Svelte, Astro, and plain TS/JS.

### Extensions (22)

**Languages:** ESLint, Svelte, Astro

**Formatting:** Prettier

**Productivity:** ES7+ React Snippets, Tailwind CSS IntelliSense, Auto Rename Tag, HTML CSS Support, npm Intellisense, Import Cost

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, DotENV, Docker, Container Tools

### Settings highlights

- JS/TS/JSX/TSX: 2-space indent, 100-char rulers, Prettier formatter
- Svelte TypeScript plugin enabled
- Organize imports on file move

---

## React Native

React Native and Expo development with TypeScript, Tailwind (NativeWind), and ESLint.

### Extensions (19)

**React Native:** Expo Tools, ES7+ React Snippets, ESLint, Tailwind CSS IntelliSense, Auto Rename Tag

**Formatting:** Prettier

**Productivity:** npm Intellisense, DotENV

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown All in One, YAML, Material Icon Theme, Color Highlight, Image Preview, Docker, Container Tools

### Settings highlights

- JS/TS/JSX/TSX: 2-space indent, 100-char rulers, Prettier formatter
- Format on save enabled

---

## Keybindings

| Key        | Command                           | Description      |
| ---------- | --------------------------------- | ---------------- |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal |

---

## Shared across all profiles

Every profile includes these tools:

| Extension                             | Purpose                                |
| ------------------------------------- | -------------------------------------- |
| `usernamehw.errorlens`                | Inline error/warning display           |
| `eamodio.gitlens`                     | Git blame, history, diff               |
| `christian-kohler.path-intellisense`  | File path autocomplete                 |
| `yzhang.markdown-all-in-one`          | Markdown preview, shortcuts, TOC       |
| `redhat.vscode-yaml`                  | YAML language support                  |
| `gruntfuggly.todo-tree`               | TODO/FIXME tree view                   |
| `pkief.material-icon-theme`           | File icons                             |
| `naumovs.color-highlight`             | Inline CSS color swatches              |
| `kisstkondoros.vscode-gutter-preview` | Image preview in gutter                |
| `ms-azuretools.vscode-docker`         | Docker management                      |
| `ms-azuretools.vscode-containers`     | Container tools                        |
| `mikestead.dotenv`                    | `.env` file syntax highlighting        |

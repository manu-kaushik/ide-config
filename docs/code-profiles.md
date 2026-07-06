# VS Code Profiles

Profiles for VS Code — each bundles extensions, settings, and keybindings for a specific project type. Switch profiles from the bottom-left avatar icon or via `Ctrl+Shift+P → Profiles: Switch Profile`.

**Import:** `Ctrl+Shift+P` → **Profiles: Import Profile** → select a file from `profiles/`.

Each `.code-profile` file contains its own **extensions**, **settings**, and **keybindings**. Profile settings layer on top of user settings — profile wins on conflicts. Extensions are **isolated per profile** — installing an extension in one profile does not affect others.

For Cursor IDE, see [Cursor Profiles](cursor-profiles.md).

---

## Profiles

| Profile      | File                             | Purpose                                              |
| ------------ | -------------------------------- | ---------------------------------------------------- |
| Default      | `profiles/Default.code-profile`      | Catch-all for misc projects                          |
| Laravel      | `profiles/Laravel.code-profile`      | PHP · Laravel · Livewire · Inertia/React             |
| Flutter      | `profiles/Flutter.code-profile`      | Dart · Flutter · Android (Java/Kotlin) · iOS (Swift) |
| Frontend     | `profiles/Frontend.code-profile`     | React · Vue · Svelte · Astro · TypeScript            |
| React Native | `profiles/ReactNative.code-profile`  | React Native · Expo · NativeWind                     |
| Node         | `profiles/Node.code-profile`         | Node.js · Express · NestJS · Prisma                  |
| Python       | `profiles/Python.code-profile`       | Python · Jupyter · Data work                         |

---

## User Settings

Global settings in [`settings.json`](../settings.json). These apply to **every profile** as the base layer. Profile-specific settings override these where they conflict.

**Edit:** `Ctrl+Shift+P → Preferences: Open User Settings (JSON)`

### Window & Workbench

| Setting                                      | Value                   |
| -------------------------------------------- | ----------------------- |
| `window.commandCenter`                       | `true`                  |
| `window.newWindowProfile`                    | `"Default"`             |
| `terminal.integrated.defaultProfile.windows` | `"Git Bash"`            |
| `workbench.iconTheme`                        | `"material-icon-theme"` |
| `workbench.editor.highlightModifiedTabs`     | `true`                  |
| `workbench.startupEditor`                    | `"none"`                |

### Files & Git

| Setting                             | Value          |
| ----------------------------------- | -------------- |
| `git.openRepositoryInParentFolders` | `"never"`      |
| `files.autoSave`                    | `"afterDelay"` |

### Editor Intelligence

| Setting                                  | Value      |
| ---------------------------------------- | ---------- |
| `editor.stickyScroll.enabled`            | `true`     |
| `editor.bracketPairColorization.enabled` | `true`     |
| `editor.guides.bracketPairs`             | `"active"` |
| `editor.inlayHints.enabled`              | `"on"`     |
| `editor.suggest.preview`                 | `true`     |

### Formatting & Code Actions

| Setting                    | Value                                      |
| -------------------------- | ------------------------------------------ |
| `editor.formatOnSave`      | `true`                                     |
| `editor.defaultFormatter`  | `esbenp.prettier-vscode`                   |
| `editor.codeActionsOnSave` | `source.fixAll` + `source.organizeImports` |

### Language-Specific Defaults

| Language         | Formatter                                   |
| ---------------- | ------------------------------------------- |
| JavaScript / JSX | Prettier                                    |
| TypeScript / TSX | Prettier                                    |
| HTML             | Prettier                                    |
| CSS / SCSS       | Prettier                                    |
| JSON             | VS Code built-in                            |
| JSONC            | Prettier                                    |
| YAML             | 2-space indent, format on save              |
| Markdown         | Word wrap on, quick suggestions enabled     |

Language-specific formatters for PHP, Python, and Dart are set in their respective profiles.

### Privacy & Telemetry

| Setting                      | Value   |
| ---------------------------- | ------- |
| `chat.disableAIFeatures`     | `true`  |
| `telemetry.feedback.enabled` | `false` |

### Claude Code

| Setting                        | Value       |
| ------------------------------ | ----------- |
| `claudeCode.preferredLocation` | `"sidebar"` |

---

## Default

General-purpose profile for miscellaneous projects, config editing, scripting, or anything that doesn't fit a specific profile. Also used when VS Code opens a new window (`window.newWindowProfile: "Default"`).

**File:** `profiles/Default.code-profile`

### Extensions (14)

**Universal Tools**

| Extension           | ID                                    | Purpose                                            |
| ------------------- | ------------------------------------- | -------------------------------------------------- |
| GitLens             | `eamodio.gitlens`                     | Git blame, history, diff, PR integration           |
| Error Lens          | `usernamehw.errorlens`                | Inline errors/warnings on the same line            |
| Todo Tree           | `gruntfuggly.todo-tree`               | Scans for TODO/FIXME/HACK and shows them in a tree |
| Path Intellisense   | `christian-kohler.path-intellisense`  | Autocomplete file paths in code                    |
| Image Preview       | `kisstkondoros.vscode-gutter-preview` | Shows image preview in the gutter                  |
| Color Highlight     | `naumovs.color-highlight`             | Highlights color values inline                     |
| Material Icon Theme | `pkief.material-icon-theme`           | File/folder icons                                  |
| DotENV              | `mikestead.dotenv`                    | Syntax highlighting for `.env` files               |

**Markdown & YAML**

| Extension           | ID                           | Purpose                                       |
| ------------------- | ---------------------------- | --------------------------------------------- |
| Markdown All in One | `yzhang.markdown-all-in-one` | Preview, shortcuts, auto TOC, list formatting |
| YAML                | `redhat.vscode-yaml`         | Schema validation, autocomplete for YAML      |

**Containers & Remote**

| Extension       | ID                                   | Purpose                                          |
| --------------- | ------------------------------------ | ------------------------------------------------ |
| Dev Containers  | `ms-vscode-remote.remote-containers` | Run VS Code fully inside a Docker container      |
| WSL             | `ms-vscode-remote.remote-wsl`        | Develop inside Windows Subsystem for Linux       |
| Docker          | `ms-azuretools.vscode-docker`        | Dockerfile/compose support, container management |
| Container Tools | `ms-azuretools.vscode-containers`    | Extended container management UI                 |

### Settings highlights

- Git Bash as default terminal on Windows
- Sticky scroll, bracket pair colorization, inlay hints
- YAML: 2-space indent, format on save
- Markdown: word wrap, quick suggestions

---

## Python

Python development — scripts, web backends (Django/FastAPI/Flask), data work, and Jupyter notebooks. Ruff handles formatting and linting.

**File:** `profiles/Python.code-profile`

### Extensions (20)

**Python Core**

| Extension       | ID                         | Purpose                                                         |
| --------------- | -------------------------- | --------------------------------------------------------------- |
| Python          | `ms-python.python`         | Python language support, virtual env management, test discovery |
| Pylance         | `ms-python.vscode-pylance` | Type checker and IntelliSense                                   |
| Python Debugger | `ms-python.debugpy`        | `launch.json`-based debugging, breakpoints, watch variables     |

**Formatting & Linting**

| Extension | ID                   | Purpose                                              |
| --------- | -------------------- | ---------------------------------------------------- |
| Ruff      | `charliermarsh.ruff` | All-in-one linter + formatter                        |

**Notebooks**

| Extension | ID                   | Purpose                                          |
| --------- | -------------------- | ------------------------------------------------ |
| Jupyter   | `ms-toolsai.jupyter` | Run `.ipynb` notebooks inline, cell-by-cell output |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

### Settings highlights

- Python: 4-space indent, 88-char ruler, Ruff as formatter, organize imports on save
- Virtual environments auto-detected (`.venv`, `venv`, `env`) — select via `Python: Select Interpreter`

---

## Node

Backend JavaScript/TypeScript development. Covers Express, Fastify, NestJS, and similar Node.js frameworks.

**File:** `profiles/Node.code-profile`

### Extensions (20)

**Language & Linting**

| Extension                       | ID                                 | Purpose                                                 |
| ------------------------------- | ---------------------------------- | ------------------------------------------------------- |
| ESLint                          | `dbaeumer.vscode-eslint`           | JS/TS linting via project `.eslintrc`                   |
| JavaScript & TypeScript Nightly | `ms-vscode.vscode-typescript-next` | Latest TypeScript compiler for cutting-edge TS features |

**Formatting**

| Extension | ID                       | Purpose                          |
| --------- | ------------------------ | -------------------------------- |
| Prettier  | `esbenp.prettier-vscode` | Formatter for JS and TS files    |

**Productivity**

| Extension        | ID                                  | Purpose                                      |
| ---------------- | ----------------------------------- | -------------------------------------------- |
| npm Intellisense | `christian-kohler.npm-intellisense` | Autocomplete npm package names in imports    |
| Import Cost      | `wix.vscode-import-cost`            | Shows bundle size of each import inline      |
| DotENV           | `mikestead.dotenv`                  | Syntax highlighting for `.env` files         |
| Prisma           | `prisma.prisma`                     | Prisma schema syntax, formatting, autocomplete |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

### Settings highlights

- JS/TS: 2-space indent, 100-char rulers, Prettier formatter
- `javascript.updateImportsOnFileMove.enabled: "always"`
- Prisma: run `npx prisma generate` to sync the client

---

## Laravel

Full-stack Laravel development — PHP backend, Blade templates, Livewire components, and Inertia.js with React on the frontend.

**File:** `profiles/Laravel.code-profile`

### Extensions (27)

**PHP & Laravel Core**

| Extension              | ID                                     | Purpose                                              |
| ---------------------- | -------------------------------------- | ---------------------------------------------------- |
| PHP Intelephense       | `bmewburn.vscode-intelephense-client`  | PHP language server — completions, go-to-def, refactor |
| Laravel                | `laravel.vscode-laravel`               | Route resolution, view/config/component navigation   |
| Laravel Blade          | `onecentlin.laravel-blade`             | Blade syntax highlighting and snippets               |
| PHP Debug              | `xdebug.php-debug`                     | Xdebug integration for step debugging                |
| PHP CS Fixer           | `junstyle.php-cs-fixer`                | Auto-format PHP files on save (PSR-12)              |
| PHP DocBlocker         | `neilbrayfield.php-docblocker`         | Generate PHPDoc blocks for functions/classes         |
| PHP Namespace Resolver | `mehedidracula.php-namespace-resolver` | Auto-import and resolve PHP namespaces               |
| Better PHPUnit         | `calebporzio.better-phpunit`           | Run PHPUnit tests from the editor                    |

**Frontend (Inertia/React/Tailwind)**

| Extension                 | ID                                | Purpose                              |
| ------------------------- | --------------------------------- | ------------------------------------ |
| ES7+ React Snippets       | `dsznajder.es7-react-js-snippets` | React/JSX component snippets         |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss`       | Tailwind class autocomplete          |
| Prettier                  | `esbenp.prettier-vscode`          | Format JS/JSX/CSS files              |
| Auto Rename Tag           | `formulahendry.auto-rename-tag`   | Renames matching HTML/JSX closing tag |
| HTML CSS Support          | `ecmel.vscode-html-css`           | CSS class autocomplete in HTML/Blade |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

### Settings highlights

- Intelephense configured for PHP 8.2 with Laravel and PHPUnit stubs
- PHP: 4-space indent, 120-char limit, PHP CS Fixer on save
- JS/JSX: 2-space indent, 100-char limit, Prettier on save
- Xdebug requires `xdebug.mode=debug` in `php.ini` and a `launch.json`

---

## Flutter

Cross-platform mobile development with Flutter/Dart. Includes native Android tooling (Java, Kotlin, Gradle) and native iOS tooling (Swift).

**File:** `profiles/Flutter.code-profile`

### Extensions (22)

**Flutter & Dart**

| Extension                | ID                              | Purpose                                              |
| ------------------------ | ------------------------------- | ---------------------------------------------------- |
| Flutter                  | `dart-code.flutter`             | Hot reload, device picker, flutter run/test          |
| Dart                     | `dart-code.dart-code`           | Dart language server — completions, diagnostics, pub |
| Awesome Flutter Snippets | `nash.awesome-flutter-snippets` | Snippets for widgets, providers, etc.                |

**Android (Java / Kotlin / Gradle)**

| Extension                 | ID                      | Purpose                                    |
| ------------------------- | ----------------------- | ------------------------------------------ |
| Language Support for Java | `redhat.java`           | Java language server                       |
| Kotlin                    | `fwcd.kotlin`           | Kotlin syntax, diagnostics, run/debug      |
| Gradle for Java           | `vscjava.vscode-gradle` | Gradle task runner, build scripts          |

**iOS (Swift)**

| Extension | ID                       | Purpose                              |
| --------- | ------------------------ | ------------------------------------ |
| Swift     | `swiftlang.swift-vscode` | Swift language server, completions   |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

### Settings highlights

- Dart: 2-space indent, 80-char ruler, format on save and on type, organize imports on save
- Java/Kotlin/Swift: 4-space indent, 120-char rulers
- Hot reload: `r` in terminal during `flutter run`, or via the Flutter toolbar
- Device picker in the bottom status bar

---

## Frontend

JavaScript/TypeScript frontend development. Covers React, Vue, Svelte, Astro, and plain TS/JS.

**File:** `profiles/Frontend.code-profile`

### Extensions (26)

**Language Servers & Linting**

| Extension                       | ID                                 | Purpose                              |
| ------------------------------- | ---------------------------------- | ------------------------------------ |
| ESLint                          | `dbaeumer.vscode-eslint`           | JS/TS linting via project `.eslintrc` |
| JavaScript & TypeScript Nightly | `ms-vscode.vscode-typescript-next` | Latest TypeScript compiler           |
| Svelte for VS Code              | `svelte.svelte-vscode`             | Svelte language server               |
| Astro                           | `astro-build.astro-vscode`         | Astro file support                   |

**Formatting**

| Extension | ID                       | Purpose                                   |
| --------- | ------------------------ | ----------------------------------------- |
| Prettier  | `esbenp.prettier-vscode` | Formatter for JS, TS, JSX, TSX, CSS, JSON |

**Productivity**

| Extension                 | ID                                  | Purpose                               |
| ------------------------- | ----------------------------------- | ------------------------------------- |
| ES7+ React Snippets       | `dsznajder.es7-react-js-snippets`   | React/JSX snippets                    |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss`         | Class autocomplete, hover preview     |
| Auto Rename Tag           | `formulahendry.auto-rename-tag`     | Renames matching HTML/JSX closing tag |
| HTML CSS Support          | `ecmel.vscode-html-css`             | CSS class/id autocomplete in HTML     |
| npm Intellisense          | `christian-kohler.npm-intellisense` | Autocomplete npm package names        |
| Import Cost               | `wix.vscode-import-cost`            | Shows bundle size of each import      |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons, DotENV.

### Settings highlights

- JS/TS/JSX/TSX: 2-space indent, 100-char rulers, Prettier formatter, format on save
- `javascript.updateImportsOnFileMove.enabled: "always"`
- `svelte.enable-ts-plugin: true` for TypeScript inside `.svelte` files
- Prettier and ESLint read from project config files in the repo root

---

## React Native

Cross-platform mobile development with React Native. Covers bare workflow and Expo, with NativeWind (Tailwind) for styling.

**File:** `profiles/ReactNative.code-profile`

### Extensions (21)

**React Native Core**

| Extension          | ID                             | Purpose                                    |
| ------------------ | ------------------------------ | ------------------------------------------ |
| React Native Tools | `msjsdiag.vscode-react-native` | Run, debug, and inspect React Native apps  |
| Expo Tools         | `expo.vscode-expo-tools`       | Expo config autocomplete, app.json support |

**Frontend Tooling**

| Extension                 | ID                                  | Purpose                              |
| ------------------------- | ----------------------------------- | ------------------------------------ |
| ES7+ React Snippets       | `dsznajder.es7-react-js-snippets`   | React/JSX snippets                   |
| ESLint                    | `dbaeumer.vscode-eslint`            | JS/TS linting                        |
| Prettier                  | `esbenp.prettier-vscode`            | Formatter for JS, TS, JSX, TSX       |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss`         | Class autocomplete for NativeWind    |
| Auto Rename Tag           | `formulahendry.auto-rename-tag`     | Renames matching JSX closing tag     |
| npm Intellisense          | `christian-kohler.npm-intellisense` | Autocomplete npm package names       |

**Universal:** GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

### Settings highlights

- JS/TS/JSX/TSX: 2-space indent, 100-char rulers, Prettier formatter
- `javascript.updateImportsOnFileMove.enabled: "always"`
- React Native Tools requires a `launch.json` for device/emulator debugging
- Tailwind CSS IntelliSense works with NativeWind class autocomplete in JSX/TSX

---

## Keybindings

All VS Code profiles share these keybindings:

| Key        | Command                           | Description                 |
| ---------- | --------------------------------- | --------------------------- |
| `Alt+C`    | `claude-vscode.sidebar.open`      | Open Claude Code in sidebar |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal          |

---

## Shared Extensions

Every profile includes these tools:

| Extension                             | Purpose                                |
| ------------------------------------- | -------------------------------------- |
| `usernamehw.errorlens`                | Inline error/warning display           |
| `eamodio.gitlens`                     | Git blame, history, diff               |
| `christian-kohler.path-intellisense`  | File path autocomplete                 |
| `yzhang.markdown-all-in-one`          | Markdown preview, shortcuts, TOC       |
| `redhat.vscode-yaml`                  | YAML language support                  |
| `ms-vscode-remote.remote-containers`  | Dev Containers                         |
| `ms-vscode-remote.remote-wsl`         | WSL integration                        |
| `gruntfuggly.todo-tree`               | TODO/FIXME tree view                   |
| `pkief.material-icon-theme`           | File icons                             |
| `naumovs.color-highlight`             | Inline CSS color swatches              |
| `kisstkondoros.vscode-gutter-preview` | Image preview in gutter                |
| `ms-azuretools.vscode-docker`         | Docker management                      |
| `ms-azuretools.vscode-containers`     | Container tools                        |
| `mikestead.dotenv`                    | `.env` file syntax highlighting        |

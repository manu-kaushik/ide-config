# VSCode IDE Config

Single VSCode installation configured to act as a specialized IDE per project type using **Profiles**. Switch profiles from the bottom-left avatar icon or via `Ctrl+Shift+P → Profiles: Switch Profile`.

## Profiles

| Profile | File | Purpose |
|---------|------|---------|
| [Default](docs/profile-default.md) | `profiles/Default.code-profile` | Catch-all for misc projects |
| [Laravel](docs/profile-laravel.md) | `profiles/Laravel.code-profile` | PHP · Laravel · Livewire · Inertia/React |
| [Flutter](docs/profile-flutter.md) | `profiles/Flutter.code-profile` | Dart · Flutter · Android (Java/Kotlin) · iOS (Swift) |
| [Frontend](docs/profile-frontend.md) | `profiles/Frontend.code-profile` | React · Vue · Svelte · Astro · TypeScript |
| [Python](docs/profile-python.md) | `profiles/Python.code-profile` | Python · Jupyter · Data work |

## User Settings

[User Settings](docs/user-settings.md) — global settings applied on top of every profile (`settings.json`).

## How Profiles Work

- Each `.code-profile` file contains its own **extensions**, **settings**, and **keybindings**
- Profile settings layer on top of user settings — profile wins on conflicts
- Extensions are **isolated per profile** — installing an extension in one profile does not affect others
- To import a profile: `Ctrl+Shift+P → Profiles: Import Profile` → select the `.code-profile` file

## Common Keybindings (all profiles)

| Key | Action |
|-----|--------|
| `Alt+C` | Open Claude Code in sidebar |
| `Numpad -` | Clear terminal |

## Shared Extensions (every profile includes these)

| Extension | Purpose |
|-----------|---------|
| `usernamehw.errorlens` | Inline error/warning display |
| `eamodio.gitlens` | Git blame, history, diff |
| `christian-kohler.path-intellisense` | File path autocomplete |
| `streetsidesoftware.code-spell-checker` | Spell check in code and comments |
| `yzhang.markdown-all-in-one` | Markdown preview, shortcuts, TOC |
| `redhat.vscode-yaml` | YAML language support |
| `ms-vscode-remote.remote-containers` | Dev Containers — run LSP inside Docker |
| `ms-vscode-remote.remote-wsl` | WSL integration |
| `gruntfuggly.todo-tree` | TODO/FIXME tree view |
| `pkief.material-icon-theme` | File icons |
| `naumovs.color-highlight` | Inline CSS color swatches |
| `kisstkondoros.vscode-gutter-preview` | Image preview in gutter |
| `ms-azuretools.vscode-docker` | Docker management |
| `ms-azuretools.vscode-containers` | Container tools |

## Windsurf Settings

`settings.json` inside the `windsurf/` folder disables Windsurf agent features (ACP, Devin). Merge into your VSCode user settings if using Windsurf for inline completion.

## Claude Commands

`/commit-message` — generates a conventional commit message for staged changes without committing. The command file is `commit-message.md` inside the `.claude/commands/` folder. Place it there at the project level (as it is here) to scope it to this repo, or in `~/.claude/commands/` to make it available globally across all projects.

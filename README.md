# VSCode IDE Config

Single VSCode installation configured to act as a specialized IDE per project type using **Profiles**. Switch profiles from the bottom-left avatar icon or via `Ctrl+Shift+P → Profiles: Switch Profile`.

## Profiles

| Profile                              | File                             | Purpose                                              |
| ------------------------------------ | -------------------------------- | ---------------------------------------------------- |
| [Default](docs/code-profiles.md#default)           | `profiles/Default.code-profile`      | Catch-all for misc projects                          |
| [Laravel](docs/code-profiles.md#laravel)           | `profiles/Laravel.code-profile`      | PHP · Laravel · Livewire · Inertia/React             |
| [Flutter](docs/code-profiles.md#flutter)           | `profiles/Flutter.code-profile`      | Dart · Flutter · Android (Java/Kotlin) · iOS (Swift) |
| [Frontend](docs/code-profiles.md#frontend)         | `profiles/Frontend.code-profile`     | React · Vue · Svelte · Astro · TypeScript            |
| [React Native](docs/code-profiles.md#react-native) | `profiles/ReactNative.code-profile`  | React Native · Expo · NativeWind                     |
| [Node](docs/code-profiles.md#node)                 | `profiles/Node.code-profile`         | Node.js · Express · NestJS · Prisma                  |
| [Python](docs/code-profiles.md#python)             | `profiles/Python.code-profile`       | Python · Jupyter · Data work                         |

See [VS Code Profiles](docs/code-profiles.md) for user settings, extensions, and keybindings.

## Cursor Profiles

Profiles for Cursor IDE — same project-type split as above.

| Profile                              | File                                        | Purpose                                              |
| ------------------------------------ | ------------------------------------------- | ---------------------------------------------------- |
| [Default](docs/cursor-profiles.md#default) | `cursor-profiles/Default.code-profile`      | Catch-all for misc projects                          |
| [Laravel](docs/cursor-profiles.md#laravel) | `cursor-profiles/Laravel.code-profile`      | PHP · Laravel · Livewire · Inertia/React             |
| [Flutter](docs/cursor-profiles.md#flutter) | `cursor-profiles/Flutter.code-profile`      | Dart · Flutter · Android (Java/Kotlin) · iOS (Swift) |
| [Frontend](docs/cursor-profiles.md#frontend) | `cursor-profiles/Frontend.code-profile`     | React · Vue · Svelte · Astro · TypeScript            |
| [React Native](docs/cursor-profiles.md#react-native) | `cursor-profiles/ReactNative.code-profile`  | React Native · Expo · NativeWind                     |
| [Node](docs/cursor-profiles.md#node) | `cursor-profiles/Node.code-profile`         | Node.js · Express · NestJS · Prisma                  |
| [Python](docs/cursor-profiles.md#python) | `cursor-profiles/Python.code-profile`       | Python · Ruff · Cursor Pyright                       |

See [Cursor Profiles](docs/cursor-profiles.md) for extensions, settings, and import instructions.

## Claude Commands

`/commit-message` — generates a conventional commit message for staged changes without committing. The command file is `commit-message.md` inside the `.claude/commands/` folder. Place it there at the project level (as it is here) to scope it to this repo, or in `~/.claude/commands/` to make it available globally across all projects.

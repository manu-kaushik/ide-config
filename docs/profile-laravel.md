# Profile: Laravel

Full-stack Laravel development — PHP backend, Blade templates, Livewire components, and Inertia.js with React on the frontend.

**File:** `profiles/Laravel.code-profile`

---

## Extensions (26)

### PHP & Laravel Core
| Extension | ID | Purpose |
|-----------|----|---------|
| PHP Intelephense | `bmewburn.vscode-intelephense-client` | PHP language server — completions, go-to-def, refactor, diagnostics |
| Laravel | `laravel.vscode-laravel` | Route resolution, view/config/component navigation |
| Laravel Blade | `onecentlin.laravel-blade` | Blade syntax highlighting and snippets |
| PHP Debug | `xdebug.php-debug` | Xdebug integration for step debugging |
| PHP CS Fixer | `junstyle.php-cs-fixer` | Auto-format PHP files on save (PSR-12, 4 spaces, 120 char limit) |
| PHP DocBlocker | `neilbrayfield.php-docblocker` | Generate PHPDoc blocks for functions/classes |
| PHP Namespace Resolver | `mehedidracula.php-namespace-resolver` | Auto-import and resolve PHP namespaces |
| Better PHPUnit | `calebporzio.better-phpunit` | Run PHPUnit tests by clicking next to the test method |

### Frontend (Inertia/React/Tailwind)
| Extension | ID | Purpose |
|-----------|----|---------|
| ES7+ React Snippets | `dsznajder.es7-react-js-snippets` | React/JSX component snippets (`rfc`, `rafce`, etc.) |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss` | Tailwind class autocomplete, hover preview |
| Prettier | `esbenp.prettier-vscode` | Format JS/JSX/CSS files |
| Auto Rename Tag | `formulahendry.auto-rename-tag` | Renames matching HTML/JSX closing tag |
| HTML CSS Support | `ecmel.vscode-html-css` | CSS class autocomplete in HTML/Blade |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

---

## Settings

### PHP
```json
{
  "php.validate.enable": false,
  "intelephense.environment.phpVersion": "8.2",
  "intelephense.diagnostics.undefinedFunctions": false,
  "intelephense.diagnostics.undefinedConstants": false
}
```
> `php.validate.enable: false` disables VSCode's built-in PHP validator which conflicts with Intelephense and causes false positives. The two `intelephense.diagnostics` settings suppress false errors for Laravel helper functions (`route()`, `config()`, etc.) and constants that Intelephense can't statically resolve.

Intelephense stubs are configured to include `laravel` and `phpunit` on top of all standard PHP extensions.

### Per-language formatting

| Language | Indent | Line limit | Formatter | Format on save |
|----------|--------|-----------|-----------|---------------|
| PHP | 4 spaces | 120 chars | PHP CS Fixer | Yes |
| Blade | 4 spaces | — | — | No (Blade formatter support is limited) |
| JavaScript / JSX | 2 spaces | 100 chars | Prettier | Yes |

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

| Key | Command | Description |
|-----|---------|-------------|
| `Alt+C` | `claude-vscode.sidebar.open` | Open Claude Code in sidebar |
| `Numpad -` | `workbench.action.terminal.clear` | Clear the terminal |

---

## Notes

- **Livewire**: Blade + Intelephense cover most Livewire work. Livewire component attributes (`wire:model`, `wire:click`) are treated as HTML attributes with Blade syntax — no dedicated extension needed currently.
- **Dockerized projects**: Use Dev Containers (`ms-vscode-remote.remote-containers`) to attach VSCode to the PHP container. Intelephense will then see the actual PHP runtime and `vendor/` inside the container.
- **Xdebug setup**: PHP Debug extension requires `xdebug.mode=debug` in your `php.ini` and a `launch.json` in the project.

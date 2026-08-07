# Source

Persistent project record. This file is the single source of truth for the whole project — not chat history, not summaries. Any agent in any chat reads and updates this file. Keep it accurate.

## Overview

A public collection of editor profiles and user settings for VS Code and Cursor. Each profile bundles extensions, settings, and keybindings tuned for a specific kind of project — Laravel, Flutter, frontend, Node, Python, and others.

The goal is to give developers a ready-made starting point instead of rebuilding the same editor setup on every machine or project. Users clone or download the repo and import what they need; nothing runs or installs from here automatically.

## Current focus

Keep VS Code and Cursor profiles accurate and documented for each supported project type.

## Stack

| Layer      | Choice | Notes |
| ---------- | ------ | ----- |
| Language   | JSON   | `.code-profile` files, `settings.json` |
| Framework  | —      | No application runtime |
| Database   | —      | — |
| Hosting    | —      | Static files in a public repository |

## Repository layout

```
/
├── README.md           # Entry point and import instructions
├── code/               # VS Code profiles and user settings
│   ├── profiles/       # Seven .code-profile files
│   ├── settings.json   # Base user settings (all profiles)
│   └── README.md       # Profile documentation
└── cursor/             # Cursor IDE profiles
    ├── profiles/       # Seven .code-profile files
    └── README.md       # Profile documentation
```

## Commands

| Task    | Command |
| ------- | ------- |
| Install | Clone repo; import profiles via VS Code / Cursor UI |
| Dev     | — |
| Test    | — |
| Lint    | — |
| Build   | — |

## Configuration

Profiles are imported via `Ctrl+Shift+P` → **Profiles: Import Profile**. VS Code user settings are applied via **Preferences: Open User Settings (JSON)** from `code/settings.json`.

No environment variables or secrets. Profile files are self-contained JSON.

## Architecture

Two parallel trees share the same seven profile names:

- **`code/`** — VS Code profiles using the full Microsoft marketplace, including remote development extensions where relevant.
- **`cursor/`** — Cursor profiles using Open VSX–compatible extensions, extension UUIDs for reliable import, and settings adapted for Cursor's runtime.

Profile settings layer on top of user settings; profile wins on conflicts. Extensions are isolated per profile.

## Conventions

- Profile names: Default, Laravel, Flutter, Frontend, ReactNative, Node, Python.
- Documentation describes what each profile provides.
- One consolidated README per editor (`code/README.md`, `cursor/README.md`).

## Constraints

- Reference-only: users copy or import what they need.
- Cursor profiles must remain importable without Microsoft-proprietary extensions.

## External services

- VS Code Marketplace / Open VSX (extensions referenced inside profile files)

## Decisions

- **Separate trees per editor** — VS Code and Cursor profiles are maintained independently because extension availability and import behavior differ between the two.
- **Seven profiles by project type** — one catch-all (Default) plus six stack-specific profiles cover the common workflows this collection targets.
- **User settings as a base layer** — `code/settings.json` holds shared editor preferences; profile-specific settings override where they conflict.

## Deferred

- Review whether `code/settings.json` still contains keys that no longer apply to this collection.

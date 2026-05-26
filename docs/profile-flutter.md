# Profile: Flutter

Cross-platform mobile development with Flutter/Dart. Includes native Android tooling (Java, Kotlin, Gradle) and native iOS tooling (Swift) for platform-specific code.

**File:** `profiles/Flutter.code-profile`

---

## Extensions (21)

### Flutter & Dart
| Extension | ID | Purpose |
|-----------|----|---------|
| Flutter | `dart-code.flutter` | Hot reload, device picker, flutter run/test, widget inspector |
| Dart | `dart-code.dart-code` | Dart language server — completions, diagnostics, formatting, pub |
| Awesome Flutter Snippets | `nash.awesome-flutter-snippets` | Snippets for StatelessWidget, StatefulWidget, providers, etc. |

> Dart extension handles pub package management natively (no separate pub extension needed).

### Android (Java / Kotlin / Gradle)
| Extension | ID | Purpose |
|-----------|----|---------|
| Language Support for Java | `redhat.java` | Java language server — completions, go-to-def, refactor |
| Kotlin | `fwcd.kotlin` | Kotlin syntax, diagnostics, run/debug |
| Gradle for Java | `vscjava.vscode-gradle` | Gradle task runner, build scripts, dependencies |

### iOS (Swift)
| Extension | ID | Purpose |
|-----------|----|---------|
| Swift | `sswg.swift-lang` | Swift language server (sourcekit-lsp), completions, diagnostics |

### Universal (shared with all profiles)
GitLens, Error Lens, Todo Tree, Path Intellisense, Markdown, YAML, Dev Containers, WSL, Docker, Color Highlight, Image Preview, Material Icons.

---

## Settings

### Dart (from Dart style guide)
```json
{
  "[dart]": {
    "editor.formatOnSave": true,
    "editor.formatOnType": true,
    "editor.rulers": [80],
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.selectionHighlight": false,
    "editor.tabCompletion": "onlySnippets",
    "editor.wordBasedSuggestions": "off",
    "editor.codeActionsOnSave": {
      "source.fixAll": "explicit",
      "source.organizeImports": "explicit"
    }
  }
}
```
> These are the settings recommended in the official Dart/Flutter docs. `selectionHighlight: false` is required because Dart's semantic highlighting conflicts with VSCode's word-match highlighting.

### Native language formatting

| Language | Indent | Line limit | Notes |
|----------|--------|-----------|-------|
| Dart | 2 spaces | 80 chars | `dart format` standard |
| Java | 4 spaces | 120 chars | Google Java style |
| Kotlin | 4 spaces | 120 chars | Kotlin coding conventions |
| Swift | 4 spaces | 120 chars | Swift style guide |
| Groovy | 4 spaces | — | Gradle build scripts |

### Debugging
```json
{
  "debug.internalConsoleOptions": "openOnSessionStart",
  "diffEditor.ignoreTrimWhitespace": false
}
```

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

- **Hot reload**: `r` in the terminal when `flutter run` is active, or via the Flutter toolbar that appears in the editor.
- **Device picker**: Bottom status bar shows the connected device/emulator. Click to switch.
- **Android emulator**: Start via Android Studio AVD Manager, then VSCode picks it up automatically. The Kotlin/Java/Gradle extensions are for editing `android/` native code, not for running Android Studio features.
- **iOS simulator**: Requires macOS. On Windows/Linux, iOS builds require a Mac build server.
- **Dockerized Flutter**: Use Dev Containers to develop inside a container with the Flutter SDK pre-installed.

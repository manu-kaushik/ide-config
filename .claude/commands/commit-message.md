Generate a commit message for the currently staged changes. Do NOT run `git commit` or any write git command — only output the message.

1. Run `git diff --cached`. If nothing is staged, run `git status`, inform the user, and stop.

2. Analyze the full diff. No matter how large the diff, produce a single concise conventional commit message:
   - First line: imperative mood, ≤72 chars, no trailing period (e.g. `feat: add dark mode toggle`)
   - If needed, a blank line followed by a short bullet-list body (one line per logical group of changes) explaining *why*, not *what*
   - Use conventional commit prefixes: `feat`, `fix`, `refactor`, `chore`, `docs`, `test`, `style`, `perf`

3. Print the commit message in a code block, then stop. Do not commit, do not ask to commit.

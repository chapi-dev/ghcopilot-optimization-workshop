# Challenge 02 · Repo custom instructions (15 pts)

**Goal:** make Copilot follow a repo-wide rule you write, and a path-specific rule.

Background: [docs/03-context-and-prompting.md](../docs/03-context-and-prompting.md)

## Part A — Repo-wide (8 pts)

1. Open [`.github/copilot-instructions.md`](../.github/copilot-instructions.md).
2. Add one new team rule, e.g.:
   > "When asked for a shell command, provide the PowerShell version first (Windows team)."
3. Start a **new chat** and ask something that triggers it (e.g. "how do I list files?").
4. Confirm Copilot honoured your rule.

## Part B — Path-specific (7 pts)

1. Create `.github/instructions/tests.instructions.md` with front matter:

   ```md
   ---
   applyTo: "**/*.test.*"
   ---
   - Use Arrange-Act-Assert. One behaviour per test. No snapshot tests.
   ```

2. Open (or create) a `*.test.*` file and ask Copilot to add a test.
3. Confirm the rule applied only for that file type.

## Done when

- [ ] A repo-wide rule you wrote changes Copilot's answers.
- [ ] A path-specific rule applies only to matching files.

## ⭐ Stretch (+5)

Run **Chat Customizations Evaluations: Analyze** on your instructions file and fix one flagged
issue (ambiguity/contradiction).

**Points:** 15 (+5 stretch)

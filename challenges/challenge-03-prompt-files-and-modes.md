# Challenge 03 · Prompt files & chat modes (20 pts)

**Goal:** stop retyping prompts. Build a reusable prompt file and a chat mode.

Background: [docs/03-context-and-prompting.md](../docs/03-context-and-prompting.md)

## Part A — Prompt file (10 pts)

1. Create `.github/prompts/review-selection.prompt.md`:

   ```md
   ---
   mode: agent
   description: Review the current selection for bugs and clarity.
   ---
   Review the selected code. List only real issues (bugs, edge cases, unclear names).
   No style nitpicks. For each, give a one-line fix. Be terse.
   ```

2. Select some code, open Chat, run `/review-selection`.
3. Confirm it runs your saved prompt.

## Part B — Chat mode (10 pts)

1. Create `.github/chatmodes/explainer.chatmode.md`:

   ```md
   ---
   description: Explains code simply, no edits.
   tools: ['codebase', 'search']
   ---
   Explain clearly and briefly. Use an analogy only if it helps. Never edit files.
   ```

2. Switch to the **explainer** mode in the Chat dropdown and ask it to explain a file.
3. Confirm it explains but does **not** edit.

## Done when

- [ ] `/review-selection` runs your prompt file.
- [ ] Your custom **explainer** mode is selectable and behaves as specified.

## ⭐ Stretch (+5)

Compare token/verbosity of the same question in default Ask mode vs. the **Concise** mode. Note
the difference in your scoreboard entry.

**Points:** 20 (+5 stretch)

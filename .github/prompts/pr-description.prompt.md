---
mode: agent
description: Generate a concise pull request description from the current diff.
---

# PR description

Using the staged/committed changes on the current branch, write a pull request description.

Format:
- **What changed** — 3–6 bullets, imperative voice.
- **Why** — 1–2 bullets of motivation/context.
- **How to test** — the minimal commands or steps a reviewer runs.
- **Risk / rollout** — only if there is real risk; otherwise omit.

Rules:
- Base it strictly on the actual diff; do not invent changes.
- No marketing language. No restating file names that add nothing.
- Keep it under ~200 words.

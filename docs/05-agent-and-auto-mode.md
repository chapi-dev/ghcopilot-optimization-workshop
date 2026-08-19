# 05 · Agent mode & auto mode

Copilot Chat has different **modes**. Agent mode can read, edit, and run things across many steps.
That power is great for multi-file work — and expensive/risky if you let it run unchecked. This
doc is about using it **deliberately**.

## The modes

| Mode | What it does | Use when |
| --- | --- | --- |
| **Ask** | Answers questions; suggests edits you apply manually | Q&A, explanations, small snippets |
| **Edit** | Makes edits across the files you specify | You know the files to change |
| **Agent** | Plans, edits multiple files, runs tools/terminal, iterates | Multi-step tasks, unknown blast radius |

Switch modes with the dropdown at the bottom of the Chat view. Custom **chat modes** (this repo's
**Concise** and **Planner**) are built on top of these.

## "Auto mode" = tool auto-approval

In agent mode Copilot proposes **tool calls** (edit a file, run a terminal command, etc.). By
default it **asks for approval** each time. "Auto mode" means letting some or all of those run
**without** stopping to ask.

VS Code setting:

```jsonc
// .vscode/settings.json — keep OFF by default
"chat.tools.autoApprove": false
```

You can also approve a specific tool for the rest of the session from the approval prompt, or cap
how far agent mode runs before checking in:

```jsonc
"chat.agent.maxRequests": 25
```

## When to use auto mode

✅ **Reasonable to auto-approve** when:

- The workspace is under version control (you can `git diff` / revert).
- The task is well-scoped and low-risk (formatting, renames, docs, test scaffolding).
- Terminal commands are read-only or clearly safe (`ls`, `git status`, running tests).
- You're iterating fast and babysitting the run.

⛔ **Keep approvals ON (don't auto-approve)** when:

- Commands are destructive or irreversible (`rm -rf`, force-push, DB migrations, deploys).
- Anything touches secrets, credentials, or production.
- You're not watching the run.
- The repo isn't backed by git.

## Safe workflow for agent/auto mode

1. **Plan first.** Use **Planner** mode (or ask for a plan) before any edits. Approve the plan.
2. **Commit or stash** so you have a clean restore point.
3. Run agent mode. Auto-approve only the safe tool categories; keep terminal/destructive gated.
4. **Review the diff** before committing — never blind-merge agent output.
5. Keep runs **short**: a capped `maxRequests` avoids runaway loops that burn tokens.

## Token angle

Agent mode multiplies token usage (many turns, tool outputs re-read each step). To keep it in check:

- Give it a **tight scope** and a clear definition of done.
- Prefer **Planner → approve → Agent** over letting Agent explore from scratch.
- Cap `maxRequests`.
- Attach only the files it needs.

Next: [06 · Copilot across the lifecycle](06-lifecycle.md).

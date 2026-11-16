# 00 · Workshop agenda

Total: ~2 hours. **~30 min talk**, then **hands-on** in VS Code.

## Part 1 — Talk (~30 min)

| Topic | Notes |
|  --- | --- |
| Why token optimization matters | Cost, latency, context limits, answer quality. |
| The 3 configuration levels | Local CLI · versioned repo · cloud coding agent — see [02](02-configuration-levels.md). |
| Custom instructions, prompt files, chat modes | The reusable building blocks — [03](03-context-and-prompting.md). |
| Token optimization playbook | Context scoping, PDF→MD, concise mode — [04](04-token-optimization.md). |
| Agent mode & auto mode | When to let it run, when to gate it — [05](05-agent-and-auto-mode.md). |
| Copilot across the lifecycle | Not just code — [06](06-lifecycle.md). |

> **MCP note:** We are **not** using MCP in this workshop (company policy). It's mentioned only
> as future/optional material — [09](09-mcp-optional.md).

## Part 2 — Hands-on (rest of the session)

Work through the [challenges](../challenges/README.md) in VS Code. They're ordered and each
awards **points**. You don't need to finish all of them — pick the track that's useful to you.

Recommended order:

1. **Challenge 01** — Setup & recommended extensions.
2. **Challenge 02** — Repo custom instructions.
3. **Challenge 03** — Prompt files & chat modes.
4. **Challenge 04** — Token optimization (PDF → Markdown).
5. **Challenge 05** — Agent mode & auto approvals.
6. **Challenge 06** — Copilot across the lifecycle.
7. **Challenge 07** — Copilot CLI (bonus / future).

## What you need

- VS Code with the **GitHub Copilot** and **Copilot Chat** extensions (Challenge 01 covers this).
- An active GitHub Copilot license.
- Python 3 (only for the PDF→Markdown challenge).

## Ground rules

- Keep prompts **scoped**. Whole-repo context is rarely needed.
- Prefer the **prompt files** and **chat modes** already in this repo over retyping prompts.
- No MCP. If a challenge seems to need it, it doesn't — there's always an MCP-free path.

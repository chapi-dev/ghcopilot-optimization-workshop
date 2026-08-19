# 02 · The three configuration levels

Copilot is configured in **three different places**. Knowing which is which avoids a lot of
confusion. Same concepts (instructions, skills, MCP) exist at each level but live in different files.

```text
┌──────────────────────────────────────────────────────────────────────┐
│ 1. LOCAL  — Copilot CLI on THIS machine (just you)                     │
│    ~/.copilot/config.json, permissions-config.json, mcp-config.json,   │
│    skills/                                                              │
├──────────────────────────────────────────────────────────────────────┤
│ 2. REPO   — Versioned, shared with the team (committed to git)         │
│    .github/copilot-instructions.md, AGENTS.md, .github/instructions/,  │
│    .github/prompts/, .github/chatmodes/, .github/skills/,              │
│    .github/mcp.json (or .vscode/mcp.json), .vscode/settings.json       │
├──────────────────────────────────────────────────────────────────────┤
│ 3. CLOUD  — Copilot coding agent (the "Agents" tab on github.com)      │
│    Settings ▸ Copilot ▸ Coding agent (MCP box),                        │
│    .github/workflows/copilot-setup-steps.yml, `copilot` env secrets    │
└──────────────────────────────────────────────────────────────────────┘
```

## Level 1 — Copilot CLI (local, this machine)

Personal to you; **not** shared. On Windows these live under `C:\Users\<you>\.copilot\`.

| Concern | File |
| --- | --- |
| Settings | `~/.copilot/config.json` |
| Tool permissions | `~/.copilot/permissions-config.json` |
| MCP servers | `~/.copilot/mcp-config.json` |
| Skills | `~/.copilot/skills/<name>/SKILL.md` |

See [07 · Copilot CLI](07-copilot-cli.md). Templates: [`templates/`](../templates/).

## Level 2 — Repo (versioned, shared with the team)

Committed to git, so the **whole team** gets the same behaviour. This is where most of the
workshop happens.

| Concern | File |
| --- | --- |
| Repo-wide instructions | `.github/copilot-instructions.md` |
| Agent instructions | `AGENTS.md` (nearest one wins) |
| Path-specific instructions | `.github/instructions/*.instructions.md` (with `applyTo`) |
| Reusable prompts | `.github/prompts/*.prompt.md` |
| Custom chat modes | `.github/chatmodes/*.chatmode.md` |
| Skills | `.github/skills/<name>/SKILL.md` |
| Editor + Copilot settings | `.vscode/settings.json` |
| MCP servers | `.github/mcp.json` or `.vscode/mcp.json` |

This repo already contains working examples of every row above.

## Level 3 — Copilot coding agent (cloud, the "Agents" tab)

Runs on GitHub.com in its own container and opens pull requests.

| Concern | Where |
| --- | --- |
| MCP servers | Repo → **Settings ▸ Copilot ▸ Coding agent** → *MCP configuration* (JSON) |
| Environment / dependencies | `.github/workflows/copilot-setup-steps.yml` |
| Secrets | Repo → **Settings ▸ Environments** → environment named `copilot` |
| Instructions | Reuses the **repo** files above (`copilot-instructions.md`, `AGENTS.md`, …) |

> The cloud agent **shares** the Level-2 instruction files. Write good repo instructions once and
> all three levels benefit.

## Which one do I edit?

- "I want *my* CLI to behave a certain way" → **Level 1**.
- "I want *the team/this repo* to behave a certain way" → **Level 2** (commit it).
- "I want the *cloud agent's PRs* to build & follow our setup" → **Level 3** (+ Level 2 instructions).

Next: [03 · Context & prompting](03-context-and-prompting.md).

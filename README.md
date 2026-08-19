# GitHub Copilot Optimization Workshop

A hands-on, reusable workshop repository for getting the most out of **GitHub Copilot**
across the **whole product lifecycle** — not just writing code — while **spending as few
tokens as possible**.

This repo is designed to be:

- **A talk companion** — a ~30 minute intro deck/notes, then hands-on.
- **A hands-on lab** — driven from **Visual Studio Code** with challenges and points.
- **A reusable template** — copy the `.github/`, `.vscode/`, and `templates/` folders into
  any repo to get an optimized Copilot setup out of the box.

> **Workshop constraint:** For company/security reasons we **cannot use MCP servers** during
> this workshop. Everything here works **without MCP**. MCP is documented in
> [`docs/09-mcp-optional.md`](docs/09-mcp-optional.md) as an *optional, future* topic only.

---

## 🗺️ Quick map

| I want to… | Go to |
| --- | --- |
| See the workshop plan (talk + hands-on) | [`docs/00-agenda.md`](docs/00-agenda.md) |
| Set up my machine & VS Code | [`docs/01-setup.md`](docs/01-setup.md) |
| Understand the 3 places you configure Copilot | [`docs/02-configuration-levels.md`](docs/02-configuration-levels.md) |
| Write better prompts & manage context | [`docs/03-context-and-prompting.md`](docs/03-context-and-prompting.md) |
| **Spend fewer tokens** | [`docs/04-token-optimization.md`](docs/04-token-optimization.md) |
| Use agent / **auto mode** safely | [`docs/05-agent-and-auto-mode.md`](docs/05-agent-and-auto-mode.md) |
| Apply Copilot to the **whole lifecycle** | [`docs/06-lifecycle.md`](docs/06-lifecycle.md) |
| Learn the **Copilot CLI** (future) | [`docs/07-copilot-cli.md`](docs/07-copilot-cli.md) |
| Pick useful extensions (Caveman, etc.) | [`docs/08-extensions.md`](docs/08-extensions.md) |
| MCP (optional / not used today) | [`docs/09-mcp-optional.md`](docs/09-mcp-optional.md) |
| Do the challenges & earn points | [`challenges/README.md`](challenges/README.md) |
| Reuse config templates | [`templates/README.md`](templates/README.md) |
| Official docs & references | [`docs/99-resources.md`](docs/99-resources.md) |

---

## 📦 What's in this repo

```text
.
├── README.md                      # You are here
├── AGENTS.md                      # Agent guidance (works in VS Code, CLI & cloud agent)
├── .vscode/
│   ├── extensions.json            # Recommended extensions for the workshop
│   └── settings.json              # Token-friendly Copilot settings
├── .github/
│   ├── copilot-instructions.md    # Repo-wide custom instructions
│   ├── instructions/              # Path-specific instructions (*.instructions.md)
│   ├── prompts/                   # Reusable prompt files (*.prompt.md)
│   ├── chatmodes/                 # Custom chat modes (*.chatmode.md)
│   ├── skills/                    # Agent skills (SKILL.md)
│   ├── workflows/
│   │   └── copilot-setup-steps.yml# Env for the cloud coding agent
│   └── mcp.json                   # MCP config (documented, disabled for the workshop)
├── docs/                          # The workshop content (read in order)
├── challenges/                    # Hands-on challenges + scoreboard
└── templates/                     # Copy-paste, reusable config templates
```

---

## 🚀 60-second start

1. Open this folder in **VS Code**.
2. Accept the **recommended extensions** prompt (or run *Extensions: Show Recommended Extensions*).
3. Open **Copilot Chat** (`Ctrl+Alt+I`).
4. Read [`docs/00-agenda.md`](docs/00-agenda.md), then start [`challenges/README.md`](challenges/README.md).

The repo already ships with custom instructions, prompt files, and chat modes so Copilot
behaves in a **concise, token-aware** way from the first message.

---

## 🎯 Workshop goals

By the end you should be able to:

- Configure Copilot at **all three levels**: local CLI, versioned repo, and cloud coding agent.
- Write **custom instructions**, **prompt files**, and **chat modes** that are reusable across sessions.
- **Reduce token usage** with tighter context, scoping, and preprocessing (e.g. PDF → Markdown).
- Use **agent mode** and **auto/agent tool approvals** deliberately and safely.
- Apply Copilot beyond coding: planning, docs, review, testing, release, and ops.

> Everything here follows GitHub's official guidance. See [`docs/99-resources.md`](docs/99-resources.md)
> for the source links.

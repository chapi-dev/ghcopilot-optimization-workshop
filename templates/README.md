# ♻️ Reusable templates

Copy-paste starting points for an optimized Copilot setup in **any** repo or on your machine.
Each file has a header comment saying where it belongs. Replace `<PLACEHOLDERS>` before use.

## Repo-level (commit these)

| Template | Copy to | Purpose |
| --- | --- | --- |
| `copilot-instructions.template.md` | `.github/copilot-instructions.md` | Repo-wide rules |
| `AGENTS.template.md` | `AGENTS.md` | Agent guidance |
| `instructions.template.instructions.md` | `.github/instructions/<name>.instructions.md` | Path-specific rules |
| `prompt.template.prompt.md` | `.github/prompts/<name>.prompt.md` | Reusable prompt |
| `chatmode.template.chatmode.md` | `.github/chatmodes/<name>.chatmode.md` | Custom chat mode |
| `vscode-settings.template.json` | `.vscode/settings.json` | Token-friendly settings |
| `mcp.template.json` | `.github/mcp.json` | MCP config (kept empty/disabled) |

## Local CLI (Level 1 — your machine, `~/.copilot/`)

| Template | Copy to | Purpose |
| --- | --- | --- |
| `cli-config.template.json` | `~/.copilot/config.json` | CLI settings |
| `cli-permissions-config.template.json` | `~/.copilot/permissions-config.json` | Tool approvals |
| `cli-mcp-config.template.json` | `~/.copilot/mcp-config.json` | MCP (reference only — disabled for the workshop) |

## How to reuse across all your projects

- **Per repo:** copy the repo-level templates into a new project and commit.
- **For every project you open:** put the concise/instruction-file settings in your **User**
  `settings.json` instead of per-workspace, so they apply everywhere.
- **For the CLI:** the `~/.copilot/*` files are global to your machine already.

> Verify setting/key names against [docs/99-resources.md](../docs/99-resources.md) — they evolve.

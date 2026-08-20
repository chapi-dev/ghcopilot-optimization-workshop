# ♻️ Reusable templates

Copy-paste starting points for an optimized Copilot setup in **any** repo or on your machine.
Every template starts with a header comment (`<!-- ... -->` or `//_` keys) explaining **where it
goes, how to use it, and the front-matter/schema options**. Most also include a **LIBRARY** of
ready-made variants at the bottom you can lift straight into their own files. Replace
`<PLACEHOLDERS>` before use.

## Repo-level (commit these)

| Template | Copy to | Purpose |
| --- | --- | --- |
| `copilot-instructions.template.md` | `.github/copilot-instructions.md` | Repo-wide rules (full project profile) |
| `AGENTS.template.md` | `AGENTS.md` | Agent guidance + guardrails |
| `instructions.template.instructions.md` | `.github/instructions/<name>.instructions.md` | Path-specific rules (+5 ready variants) |
| `prompt.template.prompt.md` | `.github/prompts/<name>.prompt.md` | Reusable prompts (+5 ready prompts) |
| `chatmode.template.chatmode.md` | `.github/chatmodes/<name>.chatmode.md` | Custom chat modes (+5 ready modes) |
| `vscode-settings.template.json` | `.vscode/settings.json` **or** User settings | Token-friendly settings (see below) |
| `mcp.template.json` | `.github/mcp.json` or `.vscode/mcp.json` | MCP config (kept empty/disabled) |

### Where does the VS Code settings template go?

`vscode-settings.template.json` has **two valid destinations** — pick based on scope:

| Scope | Destination | Effect |
| --- | --- | --- |
| **This repo only** (share with team) | `.vscode/settings.json` in the repo root, then commit | Everyone who opens the repo gets it |
| **All your projects** (just you) | Your **User** settings — Windows: `%APPDATA%\Code\User\settings.json` (or Command Palette → *Preferences: Open User Settings (JSON)*) | Applies in every workspace you open |

> Tip: keep team/style rules in `.vscode/settings.json` (committed) and personal preferences in
> your User settings.

## Local CLI (Level 1 — your machine, `~/.copilot/`)

| Template | Copy to | Purpose |
| --- | --- | --- |
| `cli-config.template.json` | `~/.copilot/config.json` | CLI config — **mostly auto-managed**; only seed `lastLoggedInUser` / `trustedFolders`. Editable settings live in `~/.copilot/settings.json`. |
| `cli-permissions-config.template.json` | `~/.copilot/permissions-config.json` | Per-folder tool approvals (real `locations → tool_approvals → kind` schema) |
| `cli-mcp-config.template.json` | `~/.copilot/mcp-config.json` | MCP (reference only — disabled for the workshop) |

## How to reuse across all your projects

- **Per repo:** copy the repo-level templates into a new project and commit.
- **For every project you open:** put the concise/instruction-file settings in your **User**
  `settings.json` instead of per-workspace, so they apply everywhere.
- **For the CLI:** the `~/.copilot/*` files are global to your machine already; scope
  `permissions-config.json` entries to specific folders and keep them tight.

> All JSON templates stay **strict-valid** (comments use `//_` string keys), so you can lint them.
> Verify evolving setting/key names against [docs/99-resources.md](../docs/99-resources.md).

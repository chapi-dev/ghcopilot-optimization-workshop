# 07 · Copilot CLI (future / bonus)

The workshop is hands-on in **VS Code**, but the **Copilot CLI** brings the same agent to your
terminal. Worth knowing for automation, scripting, and CI. This is a reference for later.

> The CLI is configured at **Level 1** (local, this machine) — see
> [02 · Configuration levels](02-configuration-levels.md).

## Install & run

```bash
# install (npm)
npm install -g @github/copilot

# start an interactive session in the current repo
copilot
```

Sign in with your GitHub account when prompted. Then just describe what you want; the CLI can
read files, propose edits, and run commands (with your approval).

## Where the CLI stores config (Windows: `C:\Users\<you>\.copilot\`)

| Concern | File |
| --- | --- |
| Settings | `~/.copilot/config.json` |
| Tool permissions / approvals | `~/.copilot/permissions-config.json` |
| MCP servers | `~/.copilot/mcp-config.json` (not used in this workshop) |
| Skills | `~/.copilot/skills/<name>/SKILL.md` |

Reusable starter versions live in [`templates/`](../templates/):

- `cli-config.template.json`
- `cli-permissions-config.template.json`
- `cli-mcp-config.template.json` (reference only — MCP disabled for the workshop)

## Approvals in the CLI (the CLI's "auto mode")

Like VS Code agent mode, the CLI asks before running tools. You can pre-approve categories in
`permissions-config.json` or per-session flags. Same rules as
[05 · Agent & auto mode](05-agent-and-auto-mode.md):

- Auto-approve safe, reversible actions in a git-backed repo.
- Never auto-approve destructive/irreversible commands or anything touching secrets/prod.

## Instructions & skills reuse

The CLI reads repo-level `AGENTS.md` and `.github` customization files too, so **the same repo
instructions you write for VS Code also steer the CLI**. Personal skills go under
`~/.copilot/skills/`.

## Why it matters (token + workflow)

- Scriptable: bake a `/token-diet`-style prompt into a shell alias or CI step.
- Same token discipline applies: scope inputs, keep sessions focused, preprocess big docs.
- Great for non-editor lifecycle tasks (release notes, triage, doc generation) from a terminal.

Next: [08 · Extensions](08-extensions.md).

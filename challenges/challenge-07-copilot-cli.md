# Challenge 07 · Copilot CLI (bonus, 15 pts)

**Goal:** run the same agent from your terminal and reuse repo instructions.

Background: [docs/07-copilot-cli.md](../docs/07-copilot-cli.md)

> Bonus/future track. Do this only if you can install the CLI on your machine.

## Steps

1. Install and launch:

   ```bash
   npm install -g @github/copilot
   copilot
   ```

2. In a session opened at this repo, ask it something that should honour `AGENTS.md`
   (e.g. "summarize what this repo is") and confirm the answer respects the repo's rules
   (English, concise, no MCP).
3. Inspect where local config lives on Windows: `C:\Users\<you>\.copilot\`
   (`config.json`, `permissions-config.json`, `skills/`).

## Done when

- [ ] A CLI session runs against this repo.
- [ ] The CLI answer reflects `AGENTS.md` / repo instructions.
- [ ] You located your local `~/.copilot` config files.

## ⭐ Stretch (+5)

Copy a template from [`templates/`](../templates/) (e.g. `cli-config.template.json`) into
`~/.copilot/`, adapt it, and note what changed.

**Points:** 15 (+5 stretch)

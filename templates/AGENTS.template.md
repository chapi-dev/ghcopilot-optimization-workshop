<!--
============================================================================
 TEMPLATE · Copy to: AGENTS.md  (repo root, or the nearest folder to the work)
 Read by autonomous agents: VS Code agent mode, Copilot CLI, and the cloud
 coding agent. The NEAREST AGENTS.md in the directory tree wins, so you can
 place folder-specific ones in subprojects of a monorepo.

 HOW TO USE
 1. Delete this comment block.
 2. Fill every <PLACEHOLDER>; delete what doesn't apply.
 3. Focus on what an agent needs to ACT safely: commands, layout, guardrails.
 4. Validate the build/test commands by actually running them before committing.
============================================================================
-->

# AGENTS.md — <PROJECT NAME>

## What this repo is
<Short description. Language(s), frameworks, entry points, how it's deployed.>

## Golden rules
1. Be concise; show only what changed.
2. Make the **smallest change** that fully solves the task; don't refactor unrelated code.
3. Always add/adjust tests when you change behaviour.
4. Never commit secrets; never touch <generated dirs, e.g. dist/, migrations/>.
5. Prefer scoped context; preprocess large inputs (PDF/DOCX → Markdown).
6. <Team-specific rule, e.g. "All content in English." / "No MCP dependencies.">

## Setup, build, test, run (validated commands)
```bash
# bootstrap (always run first)
<npm ci>
# build
<npm run build>
# test  (run the smallest relevant selection first)
<npm test -- <path>>
# lint / format / type-check (must all pass before you consider work done)
<npm run lint && npm run typecheck>
```
> If a command needs env vars or services (DB, etc.), state them here:
> `<e.g. requires a local Postgres; run `docker compose up -d db` first.>`

## Project layout (find things without searching)
- `<path/>` — <what lives here>
- `<path/>` — <what lives here>
- `<path/>` — <what lives here>

## Definition of done / validation
A change is complete only when:
- [ ] <lint> passes
- [ ] <type-check> passes
- [ ] <tests> for the touched area pass
- [ ] docs/README updated if behaviour changed

## Agent guardrails (auto/agent mode)
- Safe to run without asking: <read-only cmds, e.g. `git status`, running tests>.
- **Always ask first** before: <destructive/irreversible cmds — deletes, force-push,
  DB migrations, deploys, anything touching secrets or production>.
- Cap long runs; review the diff before committing.

## Gotchas / non-obvious facts
- <e.g. "The build fails on Node < 20." / "Generated client in src/api is created by `npm run gen`.">

<!-- Trust these instructions; only explore when they're incomplete or found to be wrong. -->

# 06 · Copilot across the whole lifecycle

Copilot isn't just autocomplete. It helps at **every stage** of the product lifecycle. This doc
maps stages → how Copilot helps → which reusable asset in this repo to use. The goal: consistent,
token-efficient help everywhere, not just in the editor.

## Lifecycle map

### 1. Plan & discovery

- Turn a rough idea or a spec PDF into structured requirements.
- **Token move:** convert the spec to Markdown first (`/doc-to-markdown`), then summarize.
- Use **Planner** chat mode to draft an approach before any code.

### 2. Design & architecture

- Ask for trade-offs between approaches; generate diagrams-as-code (Mermaid) in Markdown.
- Keep design notes in the repo so instructions/agents can reference them.

### 3. Implement

- Inline completions + **Edit/Agent** mode.
- Path-specific instructions (`.github/instructions/*.instructions.md`) keep code consistent per area.

### 4. Test

- Generate unit tests for a selection; ask for edge cases.
- A `tests.instructions.md` (via `applyTo: "**/*.test.*"`) can enforce your test conventions.

### 5. Review

- Copilot **code review** on pull requests (respects repo custom instructions).
- Use `/pr-description` to generate tight PR descriptions from the diff.
- Ask Copilot to review a diff locally before you push.

### 6. Document

- Generate/refresh READMEs, docstrings, changelogs from the actual diff.
- Keep docs concise — the repo's custom instructions already push for that.

### 7. Release

- Draft release notes and changelog entries from merged PRs/commits.
- Generate commit messages with your conventions (`commitMessageGeneration.instructions`).

### 8. Operate & support

- Explain logs/stack traces (paste the **relevant** lines, not the whole log — token discipline).
- Draft runbooks and incident summaries.
- Turn a recurring fix into a **prompt file** so the whole team runs it the same way.

### 9. Maintain & modernize

- Explain unfamiliar code, plan refactors (Planner mode), migrate patterns across files (Agent mode).

## Reusable assets by stage

| Stage | Reusable asset in this repo |
| --- | --- |
| Plan | `Planner` chat mode, `doc-to-markdown` prompt |
| Implement | `.github/instructions/*`, `copilot-instructions.md` |
| Test | path instructions with `applyTo` |
| Review | `pr-description` prompt, Copilot code review + repo instructions |
| Release | `commitMessageGeneration.instructions` in settings |
| Everywhere | `Concise` mode, `token-diet` prompt |

## The meta-point

For **any** repetitive lifecycle task: capture it once as an **instruction**, a **prompt file**, or
a **chat mode**, commit it, and the whole team gets consistent, token-efficient help. That's the
difference between "using Copilot" and "operationalizing Copilot".

Next: [07 · Copilot CLI](07-copilot-cli.md).

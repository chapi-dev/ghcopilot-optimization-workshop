# 03 · Context & prompting

Good prompting is mostly **context discipline**. The model can only be as good as what you feed
it — and what you feed it costs tokens. This doc covers the reusable building blocks and the
habits that make answers better *and* cheaper.

## The building blocks 

| Block | File | What it's for | Scope |
| --- | --- | --- | --- |
| **Custom instructions** | `.github/copilot-instructions.md` | Always-on rules for the whole repo | Every request |
| **Path instructions** | `.github/instructions/*.instructions.md` | Rules that apply only to matching files (`applyTo`) | Matching files |
| **Agent instructions** | `AGENTS.md` | Rules for agents (CLI, VS Code, cloud) | Agent runs |
| **Prompt files** | `.github/prompts/*.prompt.md` | Save a whole prompt; run with `/name` | On demand |
| **Chat modes** | `.github/chatmodes/*.chatmode.md` | A persona + allowed tools you switch into | While selected |

> This repo ships an example of each. Open them and adapt them — that's the point.

## Custom instructions

Good instructions are short, imperative, and testable. Example (already in this repo):

```md
- Answer directly. Don't restate the question or explain what you're about to do.
- Show only the changed lines when editing.
- All content in English. No MCP requirements.
```

Enable them in VS Code with:

```jsonc
"github.copilot.chat.codeGeneration.useInstructionFiles": true
```

## Context variables (spend tokens where they matter)

In Copilot Chat, **point at exactly what's relevant** instead of hoping the model finds it:

| You type | Copilot uses |
| --- | --- |
| `#file:src/auth.ts` | That specific file |
| Select code, then ask | Just the selection |
| `#selection` | Current selection |
| `#codebase` / "search the codebase" | Broader (expensive) search — use sparingly |
| `@workspace` (where available) | Workspace-aware answer |

**Rule of thumb:** start narrow (selection / one file). Widen only if the answer needs it. Every
extra file you attach is more tokens on **every** follow-up turn.

## Prompt files: stop retyping

Instead of pasting the same 10-line prompt, save it once and invoke it with `/`.

- `.github/prompts/pr-description.prompt.md` → run `/pr-description`
- `.github/prompts/token-diet.prompt.md` → run `/token-diet`
- `.github/prompts/doc-to-markdown.prompt.md` → run `/doc-to-markdown`

Enable with `"chat.promptFiles": true`.

## Chat modes: a persona you switch into

Pick a mode from the Chat mode dropdown. This repo ships:

- **Concise** — minimal, high-signal answers, restricted tools.
- **Planner** — plans first, edits nothing until you approve (saves wasted agent loops).

## Prompting habits that save tokens and improve quality

1. **One task per thread.** Long threads carry their whole history into every request. Start a
   **new chat** when you switch tasks (`Ctrl+L` / New Chat).
2. **Be specific about the output.** "Return only the diff" beats "fix this file".
3. **Give constraints up front** (language, framework, style) so you don't pay for wrong guesses.
4. **Prefer selections over whole files**; prefer files over whole-repo.
5. **Preprocess big inputs** (PDF/DOCX → trimmed Markdown) — see [04](04-token-optimization.md).
6. **Reuse** instructions/prompts/modes instead of re-explaining context each time.

Next: [04 · Token optimization](04-token-optimization.md).

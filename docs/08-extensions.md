# 08 · Useful extensions

Extensions extend Copilot Chat via `@participants` and `/commands`, or just make your editor
produce cleaner, cheaper-to-process code. Here's what's worth trying — and how to add them.

> **No MCP required.** Everything here works without MCP servers.

## Copilot Chat extensions (participants)

You invoke these in chat with `@name`. Install from the VS Code Marketplace; they then appear in
the chat participant list.

| Extension | Invoke | What it adds |
| --- | --- | --- |
| **Caveman** | `@caveman` | A fun, ultra-terse "caveman speak" participant. Great demo of how a custom participant changes tone/among the shortest possible outputs. Good icebreaker for the workshop. |
| Docs / framework participants | `@<name>` | Some libraries ship chat participants that answer with framework-specific knowledge. |

### Try Caveman (workshop icebreaker)

1. Marketplace → search **"Caveman"** → Install.
2. In Chat, type `@caveman explain what a closure is`.
3. Note how the persona compresses the answer. It's a lighthearted way to show that **who/what
   you talk to changes token usage and style** — the same idea behind our **Concise** chat mode,
   just serious instead of silly.

> Caveman is optional and just for fun/teaching. The "serious" equivalent you'll actually keep is
> the **Concise** chat mode in this repo.

## Productivity / token-hygiene extensions

These don't touch Copilot directly but reduce the tokens Copilot has to chew on:

| Extension | Why it helps tokens |
| --- | --- |
| `editorconfig.editorconfig` | Consistent formatting → smaller, predictable diffs. |
| `esbenp.prettier-vscode` | Auto-format → the model rewrites less. |
| `davidanson.vscode-markdownlint` | Clean Markdown → less noise in doc context. |
| `streetsidesoftware.code-spell-checker` | Fewer typo round-trips. |
| `ms-vscode.vscode-chat-customizations-evaluations` | Analyzes your instructions/prompts/skills and flags contradictions/ambiguity. |

## How to add an extension recommendation to a repo

Add its identifier to [`.vscode/extensions.json`](../.vscode/extensions.json) under
`recommendations`. Everyone who opens the repo gets prompted to install it — a zero-friction way
to standardize tooling across a team.

```jsonc
// .vscode/extensions.json
{ "recommendations": ["github.copilot", "github.copilot-chat", "your.extension-id"] }
```

## Custom participants vs. chat modes vs. prompt files

- **Extension participant** (`@caveman`) — third-party code, installed from Marketplace.
- **Chat mode** (`.chatmode.md`) — *your* persona + tools, versioned in the repo. No code needed.
- **Prompt file** (`.prompt.md`) — a saved prompt you run with `/name`.

For most team needs you want **chat modes + prompt files** (versioned, reviewable, no dependency),
and reach for extensions when you need real code/integration.

Next: [09 · MCP (optional)](09-mcp-optional.md).

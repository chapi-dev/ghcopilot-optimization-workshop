# Copilot instructions — GitHub Copilot Optimization Workshop

These repository-wide instructions are automatically added to Copilot Chat requests in this
workspace. They exist to make Copilot **concise, token-aware, and consistent**.

## About this project

This is a **documentation + configuration workshop**. There is no application code to build or
run. Contributions are Markdown docs, challenges, and reusable config templates.

## Response style (important — this saves tokens)

- Answer **directly**. Do **not** restate the question or explain what you are about to do.
- Prefer **short bullet points** over long prose.
- When editing files, show **only the changed lines/blocks**, not the whole file.
- Skip apologies, disclaimers, and "as an AI" phrasing.
- If a request is ambiguous, ask **one** targeted question instead of guessing broadly.

## Content rules

- All repository content is written in **English**.
- Do **not** introduce MCP requirements — the workshop runs with MCP disabled. MCP may only be
  referenced in `docs/09-mcp-optional.md` as optional/future material.
- Keep examples runnable **offline / in VS Code** without external services.

## Context & token discipline

- Prefer scoped context: reference specific files with `#file`, a selection, or `#` chat variables
  rather than dumping the whole repo.
- Preprocess large or binary inputs before sending them to the model (e.g. convert PDFs to
  Markdown with Microsoft's `markitdown`) — see `docs/04-token-optimization.md`.
- Reuse the prompt files in `.github/prompts/` and chat modes in `.github/chatmodes/` instead of
  re-typing long prompts.

## Style

- Numbered docs in `docs/` read in order; keep new docs consistent with that numbering.
- Markdown must lint cleanly (markdownlint).
- Config examples must be valid JSON/YAML and include a short header comment saying where the file goes.

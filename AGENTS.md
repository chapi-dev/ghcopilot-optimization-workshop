# AGENTS.md

Guidance for any AI agent working in this repository (VS Code Copilot, Copilot CLI, and the
cloud coding agent all read this file). Keep it short, factual, and task-agnostic.

## What this repo is

A **workshop** that teaches teams how to configure GitHub Copilot and **optimize token usage**
across the whole product lifecycle. It is primarily **Markdown documentation, configuration
templates, and challenges** — there is no application to build.

## Golden rules for agents here

1. **Be concise.** No restating the question, no filler, no "Here is what I'll do" preambles.
   Show only what changed.
2. **English only** for all repository content (docs, comments, file names).
3. **No MCP dependencies.** Everything must work with MCP disabled. MCP is documented as an
   *optional future* topic only — never make a challenge require it.
4. **Token-aware by default.** Prefer scoped context (specific files/selections) over whole-repo
   context. Preprocess large inputs (e.g. PDF → Markdown) before feeding them to the model.
5. **Keep it reusable.** Anything added under `.github/`, `.vscode/`, or `templates/` should be
   copy-pasteable into another repo with minimal edits.

## Conventions

- Docs live in `docs/` and are numbered so they read in order.
- Challenges live in `challenges/` and award **points** (see `challenges/README.md`).
- Reusable config lives in `templates/`; each template has a header comment explaining where it goes.
- Markdown should pass `markdownlint` (see `.vscode/extensions.json`).

## Validation

There is no build or test suite. "Validation" for this repo means:

- Links between docs/challenges resolve.
- Markdown lints cleanly.
- Every configuration example is valid JSON/YAML.

Trust these instructions; only search the repo when something here is incomplete or wrong.

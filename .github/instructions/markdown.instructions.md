---
description: Style rules for Markdown files in this workshop repo.
applyTo: "**/*.md"
---

# Markdown authoring rules

- Use ATX headings (`#`, `##`) and sentence case.
- Keep lines readable; wrap long prose. One idea per bullet.
- Prefer tables and bullet lists over long paragraphs (easier to scan, cheaper in tokens).
- Use fenced code blocks with a language tag (```json, ```yaml, ```bash).
- Relative links between docs must resolve (e.g. `docs/04-token-optimization.md`).
- Do not add MCP-dependent steps to any doc except `docs/09-mcp-optional.md`.
- Every config snippet must be valid and include a one-line comment stating the target file path.

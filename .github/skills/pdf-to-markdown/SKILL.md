---
name: pdf-to-markdown
description: Convert PDFs and other documents to clean Markdown to reduce token usage before using them as Copilot context.
---

# Skill: PDF → Markdown

Use this skill whenever a user wants to feed a **PDF, DOCX, PPTX, XLSX, or HTML** document to
Copilot as context. Converting to trimmed Markdown first dramatically reduces token usage and
improves answer quality.

## When to use

- The user pastes or references a large document.
- The user asks to "summarize this PDF", "use this spec", "extract requirements", etc.

## Procedure

1. Confirm the input file path.
2. Convert with Microsoft `markitdown`:
   ```bash
   pip install 'markitdown[all]'
   markitdown "<input>" -o "<output>.md"
   ```
3. Trim the result: drop headers/footers, page numbers, tables of contents, and any sections
   unrelated to the task.
4. Use only the trimmed Markdown as context. Report the before/after character count.

## Notes

- `markitdown` runs locally; no MCP or external service required.
- For scanned PDFs, OCR may be needed (`markitdown[all]` includes it).
- Keep the generated `.md` out of version control unless the user wants it committed.

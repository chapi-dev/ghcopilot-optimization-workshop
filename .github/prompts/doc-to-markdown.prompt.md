---
mode: agent
description: Turn a large document (PDF/DOCX/HTML) into clean Markdown to save tokens.
---

# Document → Markdown (token saver)

Goal: convert a bulky source document into **clean, minimal Markdown** so it can be used as
Copilot context cheaply, instead of pasting raw/binary content.

Steps:
1. Ask the user for the input file path if not provided.
2. Recommend Microsoft's `markitdown` (https://github.com/microsoft/markitdown):
   - `pip install 'markitdown[all]'`
   - `markitdown path/to/input.pdf -o output.md`
3. After conversion, **trim** the Markdown: remove repeated headers/footers, page numbers,
   navigation, and boilerplate. Keep only content relevant to the user's task.
4. Report the approximate size reduction (characters before/after) so the token saving is visible.

Do not paste the full raw document into chat; work from the trimmed Markdown.

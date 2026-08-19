# Challenge 04 · Token optimization — PDF → Markdown (25 pts)

**Goal:** feel the token difference between raw input and preprocessed Markdown.

Background: [docs/04-token-optimization.md](../docs/04-token-optimization.md)

## Setup

```bash
pip install "markitdown[all]"
```

Pick any PDF/DOCX you have (a spec, a README export, a slide deck). No sensitive documents.

## Steps

1. Convert it:
   ```bash
   markitdown "my-doc.pdf" -o "my-doc.md"
   ```
2. **Trim** `my-doc.md`: delete headers/footers, page numbers, table of contents, and any
   sections unrelated to a question you want to ask.
3. Compare sizes:
   ```powershell
   (Get-Item my-doc.pdf).Length; (Get-Content my-doc.md -Raw).Length
   ```
4. Attach the trimmed `my-doc.md` (`#file:my-doc.md`) and ask a focused question with the
   **Concise** mode or `/token-diet`.

## Done when

- [ ] You produced a trimmed Markdown version of a document.
- [ ] You asked a question using the Markdown as scoped context.
- [ ] You can state the approximate size reduction.

## ⭐ Stretch (+10)

Automate it: use the repo's `/doc-to-markdown` prompt (or the `pdf-to-markdown` skill) to do the
convert-and-trim flow end to end, and report the before/after character counts it gives you.

**Points:** 25 (+10 stretch)

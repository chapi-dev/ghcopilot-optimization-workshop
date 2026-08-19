# 04 · Token optimization playbook

The single highest-leverage skill in this workshop. Tokens = **cost + latency + context budget**.
Fewer, better-targeted tokens usually means **better** answers, not just cheaper ones.

## Where tokens go

Every chat request roughly costs:

```text
tokens ≈ system + custom instructions + attached context + conversation history + your prompt + the answer
```

You control most of these. The biggest wins, in order:

1. **Conversation history** — long threads resend everything each turn.
2. **Attached context** — whole files / whole repo when a selection would do.
3. **The answer** — verbose responses you didn't need.
4. **Raw documents** — pasting PDFs/spreadsheets instead of trimmed Markdown.

## The playbook

### 1. Start a new chat per task

History is resent on every turn. When you switch tasks, **New Chat** (`Ctrl+L`). Don't let a
50-message thread tax every new question.

### 2. Scope context tightly

- Select the code, then ask — the model sees only the selection.
- Use `#file:path` for one file instead of `#codebase`.
- Only reach for whole-repo search when you genuinely need cross-file reasoning.

### 3. Make answers concise (output tokens are real)

This repo already forces concise answers via custom instructions and the **Concise** chat mode.
For a one-off, run the `/token-diet` prompt file. The effect: no preamble, bullet points, only
changed code.

### 4. Preprocess big documents: PDF/DOCX → Markdown

Pasting a raw PDF is expensive and low quality. Convert first with Microsoft's open-source
[`markitdown`](https://github.com/microsoft/markitdown):

```bash
pip install "markitdown[all]"
markitdown big-spec.pdf -o big-spec.md
```

Then **trim** `big-spec.md` (remove headers/footers, page numbers, ToC, unrelated sections) and
feed only that. Typical result: a 40-page PDF → a few KB of relevant Markdown.

> This is exactly what [Challenge 04](../challenges/challenge-04-token-optimization.md) practises,
> and what the `doc-to-markdown` prompt file + `pdf-to-markdown` skill automate.

Related Microsoft tools you can mention:

- **markitdown** — files (PDF/DOCX/PPTX/XLSX/HTML/images) → Markdown.
- **MarkItDown** also ships a converter library if you want to script it.

### 5. Keep diffs small

`formatOnSave`, EditorConfig, and Prettier keep changes minimal and consistent. Smaller diffs
mean the model reads and rewrites less on every edit request.

### 6. Reuse, don't re-explain

Custom instructions, prompt files, and chat modes encode context **once**. Every time you reuse
one instead of re-typing background, you save the tokens of re-explaining.

### 7. Pick the right model for the job

Use a smaller/faster model for boilerplate, refactors, and Q&A; save the biggest models for hard
reasoning. The Chat model picker lets you switch per request.

### 8. Turn off what you don't need

- Disable inline suggestions in files where they don't help.
- Exclude `node_modules`, `dist`, build output from search (`search.exclude`) so they never enter
  context.

## Quick checklist

- [ ] New chat for a new task
- [ ] Selection or single `#file` instead of whole repo
- [ ] Concise mode / `/token-diet` for terse answers
- [ ] Big docs converted to trimmed Markdown
- [ ] Reused a prompt file / chat mode instead of retyping
- [ ] Right-sized model

Next: [05 · Agent & auto mode](05-agent-and-auto-mode.md).

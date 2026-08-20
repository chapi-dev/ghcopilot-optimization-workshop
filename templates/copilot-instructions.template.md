<!--
============================================================================
 TEMPLATE · Copy to: .github/copilot-instructions.md
 Repo-wide custom instructions. Auto-attached to every Copilot Chat request
 in this repo (and read by the cloud coding agent).

 HOW TO USE
 1. Delete this comment block.
 2. Fill every <PLACEHOLDER>. Delete sections that don't apply.
 3. Keep it under ~2 pages — long instructions cost tokens on every request.
 4. Write rules as short, imperative, testable statements ("Use X", "Never Y").
 5. Verify Copilot honours a rule by starting a NEW chat and asking about it.
============================================================================
-->

# Copilot instructions — <PROJECT NAME>

## 1. Project overview
<One paragraph: what this project does, who uses it, and the problem it solves.>

- **Type:** <web app | API | CLI | library | mobile | data pipeline | docs>
- **Primary language(s):** <e.g. TypeScript, Python>
- **Frameworks / runtime:** <e.g. Next.js 14, Node 20, .NET 8, Django 5>
- **Package manager:** <npm | pnpm | yarn | pip/poetry | maven | nuget>

## 2. Build, test & run (use the EXACT commands)
> Give the real commands so the agent never guesses. Mark ones that must always run.

```bash
# install (always run first)
<npm ci>
# run locally
<npm run dev>
# build
<npm run build>
# test (single file / watch)
<npm test -- <path>>
# lint & format (must pass before commit)
<npm run lint && npm run format:check>
# type-check
<npm run typecheck>
```

## 3. Architecture & layout (where things live)
- `<src/>` — <application code>
- `<src/components/>` — <UI components>
- `<src/lib/ or src/services/>` — <business logic / API clients>
- `<tests/ or __tests__/>` — <tests, mirror the src structure>
- `<infra/ or .github/workflows/>` — <CI/CD, IaC>

<Add 1–2 sentences on the overall pattern, e.g. "Layered: routes → services →
repositories. UI never calls the DB directly.">

## 4. Coding conventions
- **Style:** follow the configured formatter/linter (`<prettier + eslint>`); do not hand-format.
- **Naming:** <camelCase vars, PascalCase types, kebab-case files>.
- **Errors:** <e.g. throw typed errors; never swallow exceptions; log with the shared logger>.
- **Types:** <e.g. no `any`; prefer explicit return types on exported functions>.
- **Imports:** <e.g. use path aliases `@/…`, no deep relative `../../..`>.
- **Tests:** <framework>, Arrange-Act-Assert, one behaviour per test, no network in unit tests.

## 5. Response style (this saves tokens — keep it)
- Answer directly. Do **not** restate the question or narrate a plan first.
- Prefer short bullet points; show **only the changed code**, not whole files.
- No apologies, no "as an AI", no closing "let me know if…" filler.
- If a request is ambiguous, ask **one** targeted question instead of guessing.
- Match the existing code style of the file you're editing.

## 6. Do / Don't
**Do**
- <e.g. Add/adjust tests when you change behaviour.>
- <e.g. Update the relevant README/docstring in the same change.>
- <e.g. Prefer standard library / existing utilities over new dependencies.>

**Don't**
- <e.g. Introduce new dependencies without calling it out and giving a reason.>
- Commit secrets, tokens, or credentials — use env vars / the secret store.
- <e.g. Touch generated files in `<dist/ | migrations/>`.>
- Add MCP-dependent steps <remove this line if your project uses MCP>.

## 7. Security & data
- Never log secrets, PII, or full request bodies.
- Validate and sanitize all external input at the boundary.
- <Auth model: e.g. "All API routes require a valid JWT except /health.">

## 8. Context discipline (token efficiency)
- Prefer scoped context: a selection or `#file:<path>` over whole-repo search.
- Preprocess large docs (PDF/DOCX → trimmed Markdown) before using as context.
- Reuse the prompt files in `.github/prompts/` instead of re-typing long prompts.

<!-- Trust these instructions; only search the codebase when they're incomplete or wrong. -->

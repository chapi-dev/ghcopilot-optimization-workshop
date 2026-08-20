---
# ============================================================================
# TEMPLATE · Copy to: .github/instructions/<name>.instructions.md
# Path-specific instructions. Applied ONLY to files matching `applyTo`.
# These stack on top of .github/copilot-instructions.md for matching files.
#
# HOW TO USE
# 1. Delete comment lines you don't need.
# 2. Set `applyTo` to a glob (or comma-separated globs).
# 3. Keep rules short — they enter context for every matching request.
# A LIBRARY of ready-made variants is at the bottom; copy one into its own file.
# ============================================================================
description: <what these rules govern, e.g. "React component conventions">
applyTo: "<glob, e.g. src/**/*.tsx>"
---

# <Area> rules

- <Rule 1 — imperative and testable, e.g. "Components are function components with typed props.">
- <Rule 2 — e.g. "Co-locate the test file next to the component.">
- <Rule 3 — e.g. "No inline styles; use the design tokens in `@/styles`.">

<!--
============================================================================
 LIBRARY — copy any block below into its own *.instructions.md file
============================================================================

--- tests.instructions.md ---------------------------------------------------
---
description: Test conventions
applyTo: "**/*.{test,spec}.*"
---
- Arrange-Act-Assert; one behaviour per test; descriptive test names.
- No real network or filesystem in unit tests — mock at the boundary.
- Cover the happy path AND at least one edge/error case.
- Don't assert on implementation details; assert on observable behaviour.

--- frontend.instructions.md ------------------------------------------------
---
description: Frontend/UI conventions
applyTo: "src/**/*.{tsx,jsx,css,scss}"
---
- Accessible by default: label controls, use semantic HTML, keyboard-navigable.
- No hard-coded colours/spacing; use design tokens.
- Keep components small; extract logic into hooks/utilities.

--- api.instructions.md -----------------------------------------------------
---
description: Backend/API conventions
applyTo: "src/{api,routes,controllers}/**/*.*"
---
- Validate and sanitize all input at the boundary; return typed errors.
- Never log secrets, tokens, or full request bodies.
- Every endpoint has an auth check unless explicitly public.

--- docs.instructions.md ----------------------------------------------------
---
description: Documentation style
applyTo: "**/*.md"
---
- Sentence-case headings; bullet lists over long paragraphs.
- Fenced code blocks with a language tag; keep relative links valid.
- Prefer examples over prose.

--- sql.instructions.md -----------------------------------------------------
---
description: SQL / migrations safety
applyTo: "**/*.sql"
---
- Migrations are forward-only and reversible; never edit an applied migration.
- Parameterize queries; never build SQL by string concatenation.
============================================================================
-->

---
# ============================================================================
# TEMPLATE · Copy to: .github/prompts/<name>.prompt.md
# A reusable prompt you run in chat with  /<name>.
#
# FRONT MATTER
#   mode:        ask | edit | agent      (agent can run tools/terminal)
#   description: shown in the /command picker
#   tools:       (optional, agent mode) limit which tools it may use
#   model:       (optional) pin a model, e.g. a cheaper one for simple prompts
#
# VARIABLES you can use in the body:
#   #file:<path>      a specific file        #selection    the current selection
#   #codebase         broader (costly) search
#   ${input:name}     ask the user for a value at run time
#   ${input:name:default text}
#
# HOW TO USE
# 1. Delete this comment block. 2. Fill the body. 3. Run /<name> in chat.
# A LIBRARY of ready-to-use prompts is at the bottom.
# ============================================================================
mode: agent
description: <one line — what running this prompt does>
tools: ['codebase', 'search', 'editFiles']
---

# <Prompt title>

<Clear instruction to Copilot describing exactly what to produce.>

Constraints:
- <e.g. Output only the diff / only the changed function.>
- Be terse: no preamble, no summary of what you did.
- <e.g. Follow the repo's test conventions.>

<!--
============================================================================
 LIBRARY — copy a block into its own .github/prompts/<name>.prompt.md
============================================================================

--- refactor-selection.prompt.md -------------------------------------------
---
mode: edit
description: Refactor the selection for readability without changing behaviour.
---
Refactor #selection to improve readability and naming. Preserve behaviour and
public signatures. Show only the changed code. Explain nothing unless a change
is non-obvious (then one short line).

--- add-tests.prompt.md -----------------------------------------------------
---
mode: agent
description: Generate tests for the current file following repo conventions.
tools: ['codebase', 'search', 'editFiles']
---
Write tests for #file covering the happy path plus edge/error cases. Use the
project's existing test framework and style (find a sibling test for reference).
No network/filesystem in unit tests. Output only the new test file.

--- explain-code.prompt.md --------------------------------------------------
---
mode: ask
description: Explain the selected code briefly.
---
Explain #selection in plain language: what it does, inputs/outputs, and any
gotcha. Keep it under 8 lines. Do not rewrite the code.

--- conventional-commit.prompt.md -------------------------------------------
---
mode: ask
description: Write a Conventional Commits message from the staged diff.
---
From the staged changes, write a Conventional Commits message
(`type(scope): subject`, <=50 char subject). Add a terse body only if it adds
real information. Output just the commit message.

--- security-review.prompt.md -----------------------------------------------
---
mode: agent
description: Review a diff/selection for security issues only.
tools: ['codebase', 'search']
---
Review #selection for security issues only (injection, authz gaps, secret
leakage, unsafe deserialization, SSRF). List concrete findings with severity and
a one-line fix. If none, say "No high-confidence issues found." No style notes.
============================================================================
-->

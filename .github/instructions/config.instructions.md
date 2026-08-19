---
description: Rules for editing configuration files (JSON/YAML) in this repo.
applyTo: "**/*.{json,jsonc,yml,yaml}"
---

# Configuration file rules

- Keep JSON valid; `.vscode/*.json` may use JSONC comments, plain `.json` may not.
- Add a short header comment (where allowed) stating what the file is and where it belongs.
- Never commit secrets, tokens, or personal paths. Use placeholders like `<OWNER>/<REPO>`.
- Keys must reflect real, current setting names (verify against official docs before adding).
- Prefer the smallest set of settings that achieves the goal; explain any non-obvious one.

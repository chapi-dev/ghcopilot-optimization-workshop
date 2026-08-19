# 01 · Setup

Get your machine ready in ~10 minutes.

## 1. Install the extensions

Open this folder in VS Code. You should get a prompt: **"This workspace has extension
recommendations."** Click **Install All**. If you miss it:

- Command Palette (`Ctrl+Shift+P`) → **Extensions: Show Recommended Extensions**.

The recommendations live in [`.vscode/extensions.json`](../.vscode/extensions.json). The key ones:

| Extension | Why |
| --- | --- |
| `github.copilot` | Inline code completions. |
| `github.copilot-chat` | Chat, agent mode, prompt files, chat modes. |
| `ms-vscode.vscode-chat-customizations-evaluations` | Analyzes your instructions/prompts/skills and suggests fixes. |
| `davidanson.vscode-markdownlint` | Keeps docs clean (this repo is docs-heavy). |
| `editorconfig.editorconfig` + `esbenp.prettier-vscode` | Small, consistent diffs = fewer tokens. |

## 2. Sign in to Copilot

Click the Copilot icon in the status bar (or Accounts icon) and sign in with the GitHub account
that has your Copilot license. Open Chat with `Ctrl+Alt+I`.

## 3. Apply the workshop settings

This workspace already ships token-friendly settings in
[`.vscode/settings.json`](../.vscode/settings.json). They apply automatically when you open the
folder. To use them **everywhere**, copy the keys you like into your **User** settings:

- Command Palette → **Preferences: Open User Settings (JSON)**.

The most impactful ones:

```jsonc
// User settings.json
"github.copilot.chat.codeGeneration.useInstructionFiles": true,
"chat.promptFiles": true,
"github.copilot.chat.codeGeneration.instructions": [
  { "text": "Be concise. Don't restate the question or the plan. Show only changed code." }
]
```

## 4. (Optional) Python for the token-saver challenge

Challenge 04 converts a PDF to Markdown with Microsoft's `markitdown`:

```bash
pip install "markitdown[all]"
```

## 5. Verify

- Open Chat, switch the mode dropdown — you should see **Concise** and **Planner** custom modes
  (from [`.github/chatmodes/`](../.github/chatmodes/)).
- Type `/` in Chat — you should see the repo's prompt files (`token-diet`, `pr-description`,
  `doc-to-markdown`).

If those appear, your customization files are being picked up correctly. On to
[02 · Configuration levels](02-configuration-levels.md).

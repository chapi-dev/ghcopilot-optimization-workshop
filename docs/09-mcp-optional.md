# 09 · MCP (optional — NOT used in this workshop)

> ⚠️ **We are not using MCP in this workshop** (company policy). This page exists so you know what
> MCP is and how you *would* configure it later. **No challenge depends on MCP**, and nothing in
> this repo starts an MCP server ([`.github/mcp.json`](../.github/mcp.json) has an empty
> `servers` block).

## What MCP is (in one paragraph)

The **Model Context Protocol (MCP)** lets Copilot talk to external tools/data sources through a
standard interface — e.g. a GitHub server, an Azure server, a docs server. It expands what the
agent can do, but adds **external dependencies, trust/security review, and often more tokens**
(tool schemas + tool outputs enter context). That's exactly why we skip it for a controlled
workshop.

## Where MCP is configured at each level

| Level | Where | Notes |
| --- | --- | --- |
| Local CLI | `~/.copilot/mcp-config.json` | Personal to your machine. |
| Repo (VS Code) | `.github/mcp.json` or `.vscode/mcp.json` | Shared with the team. |
| Cloud coding agent | Repo → **Settings ▸ Copilot ▸ Coding agent** → *MCP configuration* box | Plus secrets in the `copilot` environment. |

## Why we're not using it today

- **Policy/security:** MCP servers are external integrations that need review/approval.
- **Reproducibility:** the workshop must run identically on every machine, offline-friendly.
- **Token cost:** each enabled MCP server injects tool definitions (and results) into context.

## The MCP-free alternatives we use instead

| If you'd reach for MCP to… | Do this instead (no MCP) |
| --- | --- |
| Pull a doc/spec into context | Convert it with `markitdown` → trimmed Markdown ([04](04-token-optimization.md)) |
| Give the agent a repeatable capability | Write a **skill** (`SKILL.md`) or **prompt file** |
| Standardize behaviour | **Custom instructions** + **chat modes** |
| Run project commands | Agent mode terminal tools (with approvals) |

## If you enable MCP later

1. Start with **one** trusted server.
2. Store credentials as secrets/inputs, never inline.
3. Review the token impact — disable servers you're not actively using.
4. Keep the repo's MCP config reviewable in git so the team sees what's enabled.

Back to the [docs index](../README.md#-quick-map) · or start the
[challenges](../challenges/README.md).

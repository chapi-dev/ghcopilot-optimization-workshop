# Challenge 05 · Agent mode & auto approvals (20 pts)

**Goal:** run agent mode deliberately and understand tool auto-approval trade-offs.

Background: [docs/05-agent-and-auto-mode.md](../docs/05-agent-and-auto-mode.md)

## Steps

1. Switch Chat to **Planner** mode. Ask it to plan a small change (e.g. "add a `CONTRIBUTING.md`
   with 5 contribution rules"). Review and approve the plan — no edits happen yet.
2. Switch to **Agent** mode and have it execute the approved plan.
3. When it proposes a tool (edit/terminal), **approve intentionally**. Do not blanket
   auto-approve.
4. Review the diff before keeping it.

## Reflect (write in your scoreboard note)

- Which tool actions felt safe to auto-approve? Which didn't?
- What would you set `chat.tools.autoApprove` and `chat.agent.maxRequests` to for your team?

## Done when

- [ ] You used Planner → approve → Agent.
- [ ] The change was applied and you reviewed the diff.
- [ ] You can state your auto-approve policy in one sentence.

## ⭐ Stretch (+5)

Set `chat.agent.maxRequests` to a low number, trigger a bigger task, and observe the check-in
prompt. Explain how a cap protects against runaway token usage.

**Points:** 20 (+5 stretch)

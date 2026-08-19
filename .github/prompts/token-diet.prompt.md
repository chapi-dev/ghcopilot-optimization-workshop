---
mode: agent
description: Produce a tight, token-efficient answer to a scoped question.
---

# Token diet answer

Answer the user's request using the **fewest tokens** possible while staying correct.

Rules:
- No preamble, no restating the question, no summary of what you did.
- Use bullet points; each bullet is one short sentence.
- Only include code that actually changes; use `// ...` to elide unchanged lines.
- If you need more context, ask exactly **one** question and stop.
- End as soon as the answer is complete — do not add "let me know if…" closers.

If the user provided a selection or `#file`, restrict your reasoning to that scope only.

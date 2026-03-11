---
name: til
description: "Capture a reusable learning from the current conversation as a TIL note in the vault."
user-invocable: true
---

# TIL

Capture a reusable insight or learning from this conversation.

---

## The Job

1. Review the conversation and identify the key learning — the thing worth remembering
2. Check `TILs/` for existing notes to avoid duplicates and match naming convention (lowercase-kebab-case)
3. Read one existing TIL to match the format
4. Write a new TIL note to `TILs/<topic>.md` with:
   - Frontmatter: `tags: [til, <relevant-domain>]`, `date: <today>`
   - A clear title as `# heading`
   - **The short answer** — the takeaway in 1-2 sentences
   - **Supporting detail** — the reasoning, trade-offs, or context that makes the takeaway stick
   - **A rule of thumb** — when applicable, a heuristic for future decisions
5. Confirm to the user what was saved

## Rules

- Keep it concise — a TIL is a quick reference, not an essay
- Focus on the *reusable insight*, not the conversation that produced it
- One TIL per invocation — if there are multiple learnings, ask the user which to capture
- Use the vault's existing TIL format (check an existing note if unsure)
- Do NOT create commits — just write the file

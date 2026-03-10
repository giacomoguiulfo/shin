---
name: endsession
description: "End a work session by updating the project note's Current State section with what was done, what's next, and any open questions."
user-invocable: true
---

# End Session

Wrap up the current work session by persisting context for next time.

---

## The Job

1. Identify which project(s) were worked on this session by reviewing the conversation
2. Read the corresponding `Projects/<project>.md` file(s)
3. Update the `## Current State` section with:
   - _Last updated:_ today's date
   - **Recent work**: 2-3 sentence summary of what was accomplished (outcomes, not process)
   - **Next**: Clear next steps or "To be determined at next session start"
   - **Open questions**: Any unresolved blockers/decisions, or "None currently"
4. Confirm to the user what was saved

## Rules

- Keep the summary concise — 2-3 sentences for recent work, not a changelog
- Focus on outcomes, not process ("Added RLS policies to posts table" not "Read the file, then edited it, then...")
- If multiple projects were touched, update each one
- If no project note exists for the work done, ask the user if they want one created
- Do NOT create commits — just update the file

---
tags:
  - reading
  - project/domain-expansion
source: https://simonwillison.net/guides/agentic-engineering-patterns/better-code/
author: Simon Willison
date: 2026-03-13
---

# AI Should Help Us Produce Better Code

## Key Ideas

Agents should push code quality *up*, not give teams permission to let it slide. Four patterns:

1. **Agents as background refactoring workers** — Fire off an agent in a branch to handle the cleanup you keep postponing: renames, deduplication, file splits. Stay in flow while it churns.
2. **Zero tolerance for code smells** — Refactoring is now cheap enough that the threshold for "worth fixing" should drop dramatically.
3. **Exploratory prototyping** — Instead of debating Redis vs. Postgres theoretically, spin up an agent to build a throwaway simulation or load test. Evidence over vibes.
4. **Compound engineering loop** — End each project with a retrospective of what worked, feed insights into future prompts. Small improvements compound.

## Our Take

The core bet is right — agents should raise quality, not excuse sloppiness. But the piece is more pep talk than pattern guide.

- **"Zero tolerance" is naive without addressing the review bottleneck.** Cheap refactoring doesn't mean every refactor is worth doing. The mechanical cost dropped, but the judgment cost didn't. Teams that take this literally will drown in cosmetic PRs nobody reviews.
- **Exploratory prototyping is the real unlock.** The cost of answering "should we use X?" with evidence used to be a day-long spike. Now it's a 20-minute prompt. That changes which decisions get evidence vs. vibes.
- **The compound loop is the most interesting idea and gets the least airtime.** Willison frames it as "end-of-project retrospective." We've gone further with continuous capture — vault notes, TILs, project state updates feeding back into every session, not just at project boundaries.
- **Implementation quality is still the missing constraint.** Connects to [[ai-and-software-engineering]] — agents picking up existing patterns means clean code begets clean code. The article assumes agents produce good refactors; in practice, they mirror what's already there.

## Links

- [[ai-and-software-engineering]] — constraint quality > quantity, agents mirror existing code patterns
- [[Profile]] — compound loop as continuous capture, evidence over vibes

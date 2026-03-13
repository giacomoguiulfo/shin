---
tags:
  - domain-expansion
---

# Profile

Synthesized map of Giacomo's thinking — built through reading and discussion.

## Beliefs & Mental Models

- **Pragmatism over ideology** — Strategy depends on context, not universal principles. A brand moat and a substance moat are both valid; the right choice depends on the opportunity. ([[the-brand-age]])
- **Distribution > capability** — The bottleneck for AI businesses is often go-to-market, not technical ability. Copilots have better data but worse distribution for the autopilot transition. ([[services-the-new-software]])
- **Constraint quality > constraint quantity** — More constraints isn't monotonically better. What matters is semantic clarity — constraints that communicate intent, not just enforce correctness. Rust's borrow checker is overhead without payoff for AI; Ruby/Elixir's readability is the real force multiplier. ([[ai-and-software-engineering]])
- **Implementation is a constraint** — Existing code patterns are a signal AI follows. Beautiful exemplar code is as important as types and tests. Legacy patterns reproduce even in well-typed codebases. ([[ai-and-software-engineering]])
- **Codebase as memory** — For execution tasks, the project state (git, tests, files) is a more reliable memory than conversation history. Context rotation with strong constraints beats long-lived polluted contexts. But this only works for machine-verifiable work — judgment tasks need accumulated context. ([[ralph-loop-agent]], [[ai-and-software-engineering]])
- **Taste/judgment is the bottleneck** — AI collapses generation cost but not verification cost. The scarce skill is knowing what to keep, what to delete, and what's actually correct. Typing speed was never the bottleneck; neither is code generation. ([[against-vibes-generative-models]], [[unix-manifesto-age-of-ai]], [[developer-to-fleet-commander]], [[10x-is-the-new-floor]])
- **Paradigm replacement > task automation** — Real displacement comes from inventing new systems, not automating tasks within existing ones. ATMs didn't kill tellers; mobile banking did. Copilots are ATMs; agentic systems are the iPhone. ([[why-the-atm-didnt-kill-bank-tellers]], [[ai-companies-fewer-people]], [[jevons-paradox-doesnt-always-hold]])
- **Evidence over vibes** — LLM output that "looks right" defers cost to verification. Execution-based validation (tests, linting, coverage) beats human review or LLM-as-judge for machine-verifiable work. ([[against-vibes-generative-models]], [[rails-testing-agent]], [[agentic-engineering-better-code]])

## Likes

- Clear thesis writing (Paul Graham style) ([[the-brand-age]])
- Frameworks that explain *why* industries shift ([[the-brand-age]], [[services-the-new-software]])
- Clean 2x2s that generate non-obvious predictions ([[services-the-new-software]])

## Dislikes

- Binary thinking that presents one path as universally correct ([[the-brand-age]])
- Moralizing business strategy (treating brand-building as inherently inferior) ([[the-brand-age]])
- Innovator's dilemma used as a universal law rather than a tendency ([[services-the-new-software]])
- Treating "more X = better" as monotonic — constraints, types, tests all have diminishing/negative returns past a point ([[ai-and-software-engineering]])

## Recurring Themes

_Patterns across multiple discussions._

- **GTM matters more than tech** — In both [[the-brand-age]] and [[services-the-new-software]], the winning move isn't having the best product/model — it's having the right distribution for the market you're in.
- **Domain context determines the right tool** — No universal best practice. Unit tests for backend, e2e for web apps. Rust for systems, Ruby for AI-assisted app dev. The right constraint depends on what you're building. ([[ai-and-software-engineering]], [[services-the-new-software]])
- **Constraints thesis keeps validating** — Ralph Loop works because git + tests + guardrails are sufficient constraints for fresh agents. CLAUDE.md audit showed less context = better performance. Both confirm: the right constraints matter more than more constraints. ([[ralph-loop-agent]], [[claude-md-less-is-more]], [[ai-and-software-engineering]])

---
tags:
  - reading
  - domain-expansion
source: https://mistral.ai/news/rails-testing-on-autopilot-building-an-agent-that-writes-what-developers-wont
author: Maxime Langelier & Mathis Grosmaitre (Mistral AI)
date: 2026-03-11
---

# Rails Testing on Autopilot: Building an Agent That Writes What Developers Won't

## Summary

Mistral built an autonomous agent that generates RSpec tests for Rails codebases at scale. 275 files, 100% pass rate, 100% line coverage, zero RuboCop violations. The architecture: `AGENTS.md` for execution instructions + specialized skill files per file type + forced execution validation via SimpleCov. Only ~1/3 of initially generated tests passed on first attempt — the self-correction loop through tool feedback is what made it work.

## Key Ideas

- **Context engineering > prompt engineering** — An `AGENTS.md` file with step-by-step instructions bumped quality scores from 0.68 → 0.74. Specialized skill files per component type (controllers, models, serializers) with concrete patterns and examples did the heavy lifting.
- **Execution is the only real validator** — Their LLM-as-a-judge rated a syntactically broken test (missing parenthesis) at 0.75. Forcing SimpleCov + RSpec execution as the final gate was "the single most impactful decision." Without it, quality metrics fail to catch non-runnable code.
- **Self-correction loop** — Read source → generate test → execute → fix failures → re-validate. Iterative tool feedback is the mechanism that scales. ~2/3 of tests needed at least one correction pass.
- **File type difficulty varies predictably** — Models scored 0.81 (self-contained logic, predictable patterns), serializers 0.80, controllers 0.67 (HTTP request handling complexity). The more self-contained the unit, the better agents perform.
- **Precise assertions over vague matchers** — Explicitly banned `be_present`, `be_truthy` in favor of `eq(exact_value)`. Specificity in test expectations = higher signal from failures.

## Reaction

The "missing parenthesis problem" is the headline insight: an LLM evaluating LLM output without grounding in execution is circular validation. This reinforces the constraint quality thesis from [[ai-and-software-engineering]] — agents need hard external signals (test execution, linting, coverage) to produce reliable work. Vibes-based evaluation doesn't cut it.

The `AGENTS.md` + skill files architecture is essentially what we do with project notes + worktree handoff prompts. Their specialized skill files per file type mirror how good CLAUDE.md files work — not generic instructions, but targeted patterns with concrete examples for specific contexts. Connects to [[claude-md-less-is-more]]: domain-specific instructions beat broad ones.

The parallel processing angle is worth noting — multiple agent instances on different files simultaneously. Same pattern as our worktree pipeline, just at a finer granularity.

Controllers being hardest tracks with the general pattern: the more integration surface area (HTTP, auth, middleware), the worse agents perform. Self-contained units with clear inputs/outputs are the sweet spot.

## Connections

- [[ai-and-software-engineering]] — execution-based validation validates the constraints thesis; agents need hard signals, not vibes
- [[claude-md-less-is-more]] — skill files per file type = domain-specific CLAUDE.md instructions beat generic ones
- [[ralph-loop-agent]] — same self-correction pattern; Ralph rotates context, this agent iterates within context
- [[Profile]] — reinforces: implementation constraints (tests, linting) as quality mechanism

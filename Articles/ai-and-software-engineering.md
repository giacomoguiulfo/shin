---
tags:
  - reading
  - project/domain-expansion
source: https://dlants.me/ai-se.html
author: dlants
date: 2026-03-03
---

# How Does AI Change Software Engineering?

## Key Ideas

AI doesn't change what good engineering is — it changes the **payoff** of good engineering. Codebases with strong constraints become dramatically more malleable; poorly constrained ones get marginal gains.

**Four claims:**
1. **Rewrites become feasible** — 200K-line Angular-to-React port in 6 weeks. The hard work is building behavioral comparison harnesses, not the port itself.
2. **Types are force multipliers** — Discriminated unions > loose optional properties. Invalid states unrepresentable in the type system = agents refactor confidently.
3. **Constraints > implementation** — The more robust the constraints (tests, types, specs, linters), the more freely agents can rewrite implementation. Example: AI building a C compiler using GCC torture tests + reference compiler + Rust's type system.
4. **Unit tests over integration tests** — Small, targeted tests give agents fast, non-flaky feedback loops. Agents make comprehensive unit testing worth the effort.

**Organizational punchline:** Small teams with good constraints outpace large orgs with messy codebases. AI widens the gap.

## Our Take

Agree with the constraints thesis but the article is too abstract about what "constraints" means.

- **Implementation is itself a constraint** — Models pick up existing patterns in a codebase. Perfect types and tests with gnarly legacy code will produce well-typed gnarly code. The real constraint stack is: types + tests + specs + **exemplar code**. Beautiful existing code is the missing constraint the article doesn't mention.
- **Constraints can have negative ROI** — The article treats "more constraints = better" as monotonic, but there's a curve. Rust's borrow checker and Haskell's complexity optimize for *proving correctness to the compiler*, not *communicating intent to an AI agent*. Semantically clean languages like Ruby and Elixir produce better AI results because the code reads like what it does. What matters is **semantic clarity**, not formal rigor.
- **E2E > unit tests for web apps** — The testing flip only holds for pure backend/CLI work. For web apps: unit tests can pass while the feature is visually broken, and it's easy to write unit tests that test the wrong thing. E2E with visual replay (previews, screen recordings) is a *human-verifiable* constraint — you can see correctness without reading code. The right test type depends on the domain.

**Meta-point:** Constraint *quality* matters more than constraint *quantity*.

## Links

- [[Profile]] — constraint quality > quantity, semantic clarity > formal rigor, implementation as constraint

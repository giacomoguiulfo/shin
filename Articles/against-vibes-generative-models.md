---
tags:
  - reading
  - project/domain-expansion
source: https://www.williamjbowman.com/blog/2026/03/05/against-vibes-when-is-a-generative-model-useful/
author: William J. Bowman
date: 2026-03-05
---

# Against Vibes: When is a Generative Model Useful?

## Key Ideas

Most discourse on LLM usefulness is vibes-based — subjective feelings instead of measurable properties. Bowman proposes a three-factor framework:

1. **Encoding cost** — Is it cheaper to describe the task via prompt than to just do it? Complex specifications (type systems, subtle invariants) can make prompting as hard as coding.
2. **Verification cost** — Can you confirm the output is correct? Crucially, verification often requires the same domain expertise as production. As models produce more plausible output, verification gets *harder*, not easier.
3. **Process dependency** — Does the act of creation matter beyond the artifact? Writing-to-think, learning-by-doing, and creative exploration all break when delegated.

**The sweet spot:** low encoding cost, trivial verification, process-irrelevant tasks.

**Examples:**
- **Failure:** 8 hours prompting Claude Opus for a DSL interpreter — unusable code with type errors. High encoding cost, high verification cost, expertise-dependent.
- **Success:** One-line prompt to install forgotten software — trivial encoding, trivial verification, process doesn't matter.
- **Process-dependent:** Writing the blog post itself. The thinking *is* the point.

## Our Take

The framework is solid and maps well to our experience. It's essentially a formalization of what we've been learning through [[ai-and-software-engineering]] — constraints and verifiability determine AI leverage.

- **Connects to constraint quality** — Bowman's "verification cost" is the flip side of dlants' "constraints." Good constraints (types, tests, specs) *reduce* verification cost. The two frameworks are complementary: invest in constraints to make the verification side of Bowman's equation trivial.
- **The plausibility trap is real** — This is the core danger of vibes-based adoption. Plausible output *feels* like progress but defers cost to verification. We've seen this: generated code that looks right, passes a glance, but fails under real use.
- **Missing dimension: iteration cost** — What about tasks where the first output is wrong but cheap to fix? The framework is static — it doesn't account for feedback loops. In practice, fast iteration (run tests, fix, repeat) can make high-verification tasks viable if each cycle is cheap.

## Links

- [[ai-and-software-engineering]] — complementary frameworks: constraints reduce verification cost
- [[Profile]] — plausibility trap, verification as the bottleneck for AI leverage

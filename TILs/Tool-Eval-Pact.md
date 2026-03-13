---
tags:
  - tool-eval
  - revisit
date: 2026-03-13
verdict: revisit
---

# Pact

## What It Is

Contract-first multi-agent software engineering framework. Defines typed interfaces and tests *before* agents implement, enforcing correctness mechanically. [GitHub](https://github.com/jmcentire/pact) — 136 stars, MIT license, Python.

## Problem It Solves

LLM code generation struggles with multi-component coordination, verification, and context window limits. Pact inverts the usual flow: contracts and tests come first, implementations are disposable artifacts. Agents can't ship code that violates its contract.

## Key Observations

- **10-phase pipeline**: Interview → Shape → Decompose → Contract → Test → Validate → Implement → Integrate → Polish → Diagnose. Each phase is a mechanical gate.
- **Philosophy deeply aligned**: "Contracts are source of truth, implementations are disposable" maps directly to our constraints thesis — the right constraints matter more than more code. Tests as enforcement (not suggestions) is exactly the codebase-as-memory insight.
- **Benchmark is impressive**: 100% pass on 5 ICPC World Finals problems where iterative Claude Code hit 92%. The contract-first approach forced upfront analysis that iterative prompting can't replicate.
- **Heavy framework**: Own project structure, own decomposition pipeline, own CLI, daemon mode, MCP server. This *replaces* your workflow rather than augmenting it.
- **Very early**: Created Feb 14 2026, solo developer (jmcentire), 136 stars, 9 forks. No community ecosystem yet.
- **Production story is interesting**: Sentinel watches logs, attributes errors to components via embedded keys, spawns fixer agents loaded with contract context, adds reproducer tests, rebuilds. Human reviews the contract change, not the code.

## Trust Check

1. **Source availability**: Open source, MIT — full audit possible
2. **Developer credibility**: Solo dev, no public track record. No org backing. Very new project.
3. **Access scope**: Runs LLM agents with full codebase access + shell. Budget caps and audit logs mitigate but scope is high.
4. **Dependency weight**: Python 3.12+, Pydantic, PyYAML. LLM SDKs optional. Lightweight core.

## Why Not Adopt Now

- **Replaces rather than augments**: We have vault → plan → worktree dispatch → Claude Code builds with CLAUDE.md constraints + tests. Pact wants to own the whole pipeline from decomposition through implementation. That's a swap, not an addition.
- **Ceremony vs. payoff**: The 10-phase pipeline makes sense for genuinely complex multi-component systems. For most of our work (features, refactors, bug fixes), it's massive overhead.
- **Solo dev, 1 month old**: The philosophy is sound but the implementation needs time to prove out. No community, no battle-testing beyond benchmarks.
- **Ideas > tool**: The most valuable parts — contract-first thinking, Goodhart tests, health monitoring for agent pipelines — are extractable insights we can apply to our existing workflow without adopting the framework.

## Verdict

**Revisit.** The contract-first philosophy is the most aligned thing we've evaluated — it's essentially our constraints thesis turned into a framework. But it's too early (solo dev, 1 month), too heavy (replaces workflow vs. augmenting it), and the ideas are more portable than the tool. Revisit when: (a) it has community traction and battle-testing, or (b) we're building a system complex enough that our worktree pipeline can't coordinate the components — that's when the decomposition + contract layer earns its keep.

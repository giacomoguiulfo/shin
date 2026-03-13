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
- **Operationalizes what we keep saying**: We've validated the constraints thesis across multiple sessions but don't have a tool that enforces it. Pact is someone who built exactly that.
- **Production story is novel**: Sentinel watches logs, attributes errors to components via embedded keys, spawns fixer agents loaded with contract context, adds reproducer tests, rebuilds. Human reviews the contract change, not the code. Contract-driven self-healing.
- **Very early**: Created Feb 14 2026, solo developer (jmcentire), 136 stars, 9 forks. No community ecosystem yet.

## Trust Check

1. **Source availability**: Open source, MIT — full audit possible
2. **Developer credibility**: Solo dev, no public track record. No org backing. Very new project.
3. **Access scope**: Runs LLM agents with full codebase access + shell. Budget caps and audit logs mitigate but scope is high.
4. **Dependency weight**: Python 3.12+, Pydantic, PyYAML. LLM SDKs optional. Lightweight core.

## What Gives Pause

- **Solo dev, 1 month old**: If jmcentire disappears, you're maintaining a Python framework. Real risk for something you'd build a workflow around.
- **Cost model**: $13 per ICPC problem. Multi-agent pipeline adds up. Fine for complex systems, expensive if applied broadly.
- **Ceremony calibration**: 10 phases is a lot. Need to know when to reach for it vs. when a simple worktree dispatch suffices.

## Verdict

**Revisit — but try it soon.** The contract-first philosophy is the most aligned thing we've evaluated — it operationalizes our constraints thesis rather than just validating it. We don't have a mature workflow yet, so there's less to "replace." Worth experimenting with on the next real multi-component project. Worst case: we learn what contract-first feels like in practice and bring the patterns back regardless. The maturity risk (solo dev, 1 month) means don't build around it yet, but do build *with* it and see.

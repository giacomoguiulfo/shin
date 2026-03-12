---
tags:
  - tool-eval
  - skip
date: 2026-03-13
verdict: skip
---

# oh-my-claudecode (OMC)

## What It Is

Multi-agent orchestration plugin for Claude Code that adds 32 specialized agents, multiple execution modes, and magic keywords. [GitHub](https://github.com/yeachan-heo/oh-my-claudecode) — 9.5k stars, 1,820 commits, MIT license. Very actively maintained.

## Problem It Solves

Automates complex multi-step development workflows by decomposing tasks across specialized agents (planning, design, execution, verification, debugging) with automatic retry loops and parallel execution.

## Key Observations

- **Massive feature surface**: 32 agents, 5+ orchestration modes (Team, Autopilot, Ralph, Ultrawork, Pipeline), magic keywords, HUD, analytics, cost tracking, notifications, session replay
- **Heavy overlap with existing setup**: We already have `superpowers:dispatching-parallel-agents`, `superpowers:executing-plans`, `ralph-loop`, `claude-mem`, `superpowers:brainstorming`, `superpowers:verification-before-completion` — covering the same plan→execute→verify loop
- **Thick abstraction layer**: Adds its own skill learning, memory, model routing, and orchestration on top of Claude Code's native capabilities
- **Trust passes but access scope is high**: Open source, MIT, decent community. But as a Claude Code plugin it gets full codebase + shell access, and the abstraction makes it harder to reason about what's actually executing

## What OMC Does That Our Stack Doesn't

Being honest about gaps:

- **Smart model routing**: Haiku for simple tasks, Opus for complex reasoning. Claims 30-50% token cost savings. Our stack uses whatever model is configured globally — no per-task routing
- **Rate-limit auto-resume**: Daemon that resumes work after hitting API limits. We don't have this — rate limits just interrupt the session
- **Multi-provider CLI workers**: Real tmux panes spawning Codex, Gemini, Claude instances. Our stack is Claude-only
- **Built-in cost tracking and HUD**: Session analytics showing token usage, model distribution, real-time progress. We have no observability into what agents are consuming
- **Deep-interview / Socratic clarification**: Weighted dimensional analysis to expose hidden assumptions before coding. Similar to brainstorming but more structured

## Why We Still Skip

The capabilities above are real, but the trade-off doesn't favor switching:

1. **We'd lose vault integration.** OMC doesn't know about project notes, TILs, profile, or session boundaries. Rebuilding that integration inside OMC's framework would be significant work.
2. **Abstraction opacity.** 32 agents and magic keywords mean less control over what's actually executing. When something goes wrong, debugging through OMC's orchestration layer is harder than debugging a skill you wrote.
3. **Feature surface vs. actual use.** User reviews confirm: "after a few days, only a handful of features get used regularly." The 80% of OMC we wouldn't use is still consuming context and adding complexity.
4. **Philosophy mismatch stands.** "Zero learning curve, maximum power" is the opposite of understanding your tools deeply. Magic keywords that auto-delegate obscure the constraint quality that makes agents reliable.

## Verdict

**Skip, but with noted gaps.** The model routing, rate-limit handling, and observability features are genuinely useful capabilities we lack. If those become pain points, the right move is adding them as targeted skills (a model-router skill, a cost-tracker hook) rather than adopting the full OMC framework. Cherry-pick the ideas, not the monolith.

---
tags:
  - tool-eval
  - skip
date: 2026-03-13
verdict: skip
---

# oh-my-claudecode (OMC)

## What It Is

Multi-agent orchestration plugin for Claude Code that adds 32 specialized agents, multiple execution modes, and magic keywords. [GitHub](https://github.com/yeachan-heo/oh-my-claudecode) — 9.5k stars, MIT license.

## Problem It Solves

Automates complex multi-step development workflows by decomposing tasks across specialized agents (planning, design, execution, verification, debugging) with automatic retry loops and parallel execution.

## Key Observations

- **Massive feature surface**: 32 agents, 5+ orchestration modes (Team, Autopilot, Ralph, Ultrawork, Pipeline), magic keywords, HUD, analytics, cost tracking, notifications, session replay
- **Heavy overlap with existing setup**: We already have `superpowers:dispatching-parallel-agents`, `superpowers:executing-plans`, `ralph-loop`, `claude-mem`, `superpowers:brainstorming`, `superpowers:verification-before-completion` — covering the same plan→execute→verify loop
- **Thick abstraction layer**: Adds its own skill learning, memory, model routing, and orchestration on top of Claude Code's native capabilities. npm package name (`oh-my-claude-sisyphus`) doesn't match repo name — minor packaging hygiene flag
- **Trust passes but access scope is high**: Open source, MIT, decent community. But as a Claude Code plugin it gets full codebase + shell access, and the abstraction makes it harder to reason about what's actually executing
- **Philosophy mismatch**: "Zero learning curve, maximum power" via magic keywords and auto-delegation runs counter to our principles — constraint quality > quantity, less context = better performance, understanding tools deeply

## Verdict

**Skip.** We already have a curated skill stack covering the same plan→execute→verify workflow with more transparency and less abstraction. OMC's "32 agents and magic keywords" approach is the opposite of the minimal-structure, quality-constraints philosophy we follow. If our current orchestration setup ever feels limiting, the right move is extending our existing skills, not replacing them with a monolithic framework.

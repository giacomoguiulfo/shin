---
tags:
  - tool-eval
  - skip
date: 2026-03-13
verdict: skip
---

# Get Shit Done (GSD)

## What It Is

Meta-prompting and context engineering system for Claude Code, OpenCode, Gemini CLI, and Codex. Orchestrates AI development through structured phases: discuss → plan → execute → verify. [GitHub](https://github.com/gsd-build/get-shit-done) — 28.7k stars, MIT license.

## Problem It Solves

Context degradation in long AI coding sessions. GSD breaks work into atomic phases with fresh context windows, manages parallel task "waves," and creates structured planning artifacts (PROJECT.md, REQUIREMENTS.md, ROADMAP.md, STATE.md) for continuity.

## Key Observations

- **Popular and active**: 28.7k stars, 2.4k forks, 1,010 commits, pushed yesterday. Healthy community with Discord. Trusted by engineers at major companies
- **Same category as OMC**: Multi-agent orchestration on top of Claude Code. Plan→execute→verify with parallel dispatch — exactly what our superpowers skills + ralph-loop + worktree pipeline already do
- **Creates its own project management layer**: PROJECT.md, REQUIREMENTS.md, ROADMAP.md, STATE.md duplicates the vault's project note approach and conflicts with our "codebase as memory" principle
- **Recommends `--dangerously-skip-permissions`**: Required for frictionless automation. Understandable for the workflow but widens attack surface
- **Context rotation insight is valid but already captured**: Fresh context per agent with structured handoffs is exactly what our worktree pipeline does — GSD just formalizes it differently

## Verdict

**Skip.** Heavy overlap with existing stack. We already practice context rotation via worktree isolation, have plan→execute→verify via superpowers skills, and run parallel agents via dispatching-parallel-agents. GSD's planning artifacts (PROJECT.md, ROADMAP.md, etc.) conflict with our vault-based project notes and add ceremony we don't need. The core insight — atomic tasks with fresh context windows — is already how we work. Adopting GSD would mean replacing a curated, transparent skill stack with an opinionated framework.

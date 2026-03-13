---
tags:
  - tool-eval
  - revisit
date: 2026-03-13
verdict: revisit
---

# Paperclip

## What It Is

Open-source orchestration platform that manages teams of AI agents working toward business goals. "If OpenClaw is an employee, Paperclip is the company." [GitHub](https://github.com/paperclipai/paperclip) — 21k stars, 879 commits, MIT license.

## Problem It Solves

Coordination overhead when running multiple AI agents simultaneously. Without it: scattered configs, untracked work, cost overruns, manual context management. Paperclip provides org charts, budgets, ticketing, heartbeats, and a dashboard to manage agent fleets as a unified workforce.

## Key Observations

- **Agent-agnostic**: Works with Claude Code, Codex, Cursor, OpenClaw, Bash, or HTTP-based agents. Not locked to one ecosystem
- **Full "company" metaphor**: Org charts with hierarchies, roles, approval gates, per-agent monthly budgets with auto-throttling, persistent ticket conversations with audit trails
- **Heartbeats and scheduling**: Scheduled agent wake-ups and event-based triggers — cron for agents
- **Multi-company isolation**: Complete data separation within one deployment. Useful if managing agents across projects
- **Heavy stack**: TypeScript + React + PostgreSQL. Self-hosted. Non-trivial to run for a solo dev managing 1-3 parallel agents

## Trust Check

- **Source**: Open, MIT, auditable
- **Credibility**: 21k stars, active development (v0.3.1, March 2026). Community is real
- **Access scope**: Manages agent lifecycles — it needs to spawn, monitor, and control agents. High access scope
- **Dependency weight**: PostgreSQL, Node.js server, React dashboard. Heavier than a skill or CLI plugin

## Verdict

**Revisit.** The concept is solid — agent fleet management with budgets and governance will matter as agent parallelism scales. But it's solving a problem we don't have yet. Our current setup (1-3 worktree agents, vault-based context, manual dispatch) works fine at current scale. The overhead of running a full management server with PostgreSQL doesn't justify itself for solo use. Revisit when running 5+ concurrent agents regularly or when agent cost tracking becomes a real pain point.

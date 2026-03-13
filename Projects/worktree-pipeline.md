---
tags:
  - project/worktree-pipeline
  - pattern
status: planning
---

# Worktree Pipeline

Autonomous development orchestration. Mind plans and dispatches; git worktrees implement in isolated Zellij sessions with their own Claude instance. A quality pipeline reviews, and a merge queue integrates.

## The Idea

Instead of one Claude session doing everything sequentially, spin up parallel workers — each in its own git worktree with its own Claude context. Mind stays strategic (planning, decisions, vault work), workers stay focused (one task, one branch). This is how you get concurrent development from a single developer.

**Core principle**: The prompt is the handoff. Mind pre-digests all context the worker needs. Workers are disposable; the work they produce is what matters.

## Key Decisions

- **Zellij over tmux** — declarative layouts, named panes, WASM plugin potential
- **Mind never writes project code** — session boundary principle
- **Local-only merge queue** — no GitHub PRs for now, sequential rebase → test → merge
- **Claude-mem scopes by cwd** — worktree observations stay separate from mind observations

## Lifecycle

`create` (worktree + branch) → `start` (Zellij + Claude) → implement → `review` (simplify → review → security) → `merge` (rebase → test → fast-forward)

## Open Questions

- `wt` CLI: shell script, Ruby, or Go?
- Does mind generate the task breakdown, or does the worker session break it down?
- Is this an evolution of Kanvify's Dark Factory, or a replacement?

## Current State

_Last updated: 2026-03-10_

**Status**: Planning complete.

**Next**: Phase 1 — build the `wt` CLI (create/destroy/list) and state file format. Install Zellij.

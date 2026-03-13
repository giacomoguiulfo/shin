---
tags:
  - tool-eval
---

# Tool Radar

Tools we've evaluated. Each links to a detailed note in `TILs/`.

## Adopt

_Tools we're using or plan to use._

- [[Tool-Eval-Lazygit]] — Terminal UI for git. Visual rebase, hunk staging, worktree management in a single Go binary. (2026-03-11)

## Process

- [[Tool-Eval-Process-Checklist]] — Trust check: always verify source, credibility, access scope, and dependency weight before recommending adopt

## Skip

- **21st.dev** — React/Tailwind component library + AI agent SDK. Component library overlaps heavily with shadcn/ui which we already use. Agent SDK is separate concern, revisit if shipping an agent product. (2026-03-10)
- [[Tool-Eval-Piebald]] — Multi-provider agentic CLI. Claude Code + `--worktree` already covers the parallel workflow. (2026-03-10)
- [[Tool-Eval-UUPM]] — Paid design intelligence skill for Claude Code. Already have `frontend-design` skill doing this. (2026-03-10)
- [[Tool-Eval-GrapeRoot]] — Codebase graph MCP server. Closed source, unverified solo dev, no public repo. Concept worth exploring via open-source alternatives. (2026-03-10)
- [[Tool-Eval-OMC]] — Multi-agent orchestration plugin for Claude Code. Heavy overlap with existing stack; model routing and observability are real gaps but not worth the abstraction trade-off. Cherry-pick ideas instead. (2026-03-13)
- [[Tool-Eval-GSD]] — Meta-prompting orchestration for Claude Code. Same plan→execute→verify loop we already have via superpowers + worktrees, plus conflicting project artifact layer. (2026-03-13)

## Revisit

- [[Tool-Eval-RWSDK]] — React framework for Cloudflare Workers. Appealing "zero magic" philosophy, but edge-first has data locality trade-offs. Revisit when building something that genuinely needs edge compute. (2026-03-10)
- [[Tool-Eval-Mem0]] — Managed memory layer for AI apps. Skip for personal use, revisit if building AI product features needing per-user memory. (2026-03-10)
- [[Tool-Eval-Paperclip]] — Agent fleet management platform with org charts, budgets, ticketing. Overkill for solo use; revisit when running 5+ concurrent agents. (2026-03-13)

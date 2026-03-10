---
tags:
  - tool-eval
---

# Tool Radar

Tools we've evaluated. Each links to a detailed note in `TILs/`.

## Adopt

_Tools we're using or plan to use._

## Skip

- **21st.dev** — React/Tailwind component library + AI agent SDK. Component library overlaps heavily with shadcn/ui which we already use. Agent SDK is separate concern, revisit if shipping an agent product. (2026-03-10)
- [[Tool-Eval-Piebald]] — Multi-provider agentic CLI. Claude Code + `--worktree` already covers the parallel workflow. (2026-03-10)
- [[Tool-Eval-UUPM]] — Paid design intelligence skill for Claude Code. Already have `frontend-design` skill doing this. (2026-03-10)
- [[Tool-Eval-GrapeRoot]] — Codebase graph MCP server. Closed source, unverified solo dev, no public repo. Concept worth exploring via open-source alternatives. (2026-03-10)

## Revisit

- [[Tool-Eval-RWSDK]] — React framework for Cloudflare Workers. Appealing "zero magic" philosophy, but edge-first has data locality trade-offs. Revisit when building something that genuinely needs edge compute. (2026-03-10)
- [[Tool-Eval-Mem0]] — Managed memory layer for AI apps. Skip for personal use, revisit if building AI product features needing per-user memory. (2026-03-10)

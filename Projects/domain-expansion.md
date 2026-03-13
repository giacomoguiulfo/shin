---
tags:
  - project/domain-expansion
---

# Domain Expansion

Article reading and discussion loop that builds a shared mental model between Giacomo and Claude. Each article expands the domain — capturing reactions, opinions, and patterns in thinking.

## Workflow

1. Share an article (URL or pasted text)
2. Claude summarizes the key ideas
3. We discuss — agree, disagree, riff, connect to other ideas
4. Claude captures the article note + updates the profile

## How It Works

- Article notes live in `Articles/`, tagged `#reading`
- Synthesized views accumulate in `Profile.md` (likes, dislikes, beliefs, mental models)
- Articles link to profile themes; profile links back to articles as evidence

## Current State

_Last updated: 2026-03-10_

**Recent work**: Evaluated claude-mem (thedotmack/claude-mem, 33k stars) — an auto-capture memory plugin for Claude Code that records session activity, compresses with AI, and injects relevant context into future sessions. Installed it for general dev use. Stress-tested it against our existing research: the ETH Zurich "Less Is More" finding (auto-generated context hurts performance), constraint quality > quantity thesis, and the Mem0 eval's "opaque vs. transparent" tradeoff. Key nuance: claude-mem's search-then-fetch (RAG-like) pattern is meaningfully different from the static context injection the paper warned against, so it may avoid the worst pitfalls.

**Next**: Fifth article. Monitor claude-mem across dev sessions to see if it actually helps or just burns tokens.

**Open questions**: Does claude-mem's progressive disclosure actually avoid the "more context = worse performance" trap, or does it still pollute the context window?

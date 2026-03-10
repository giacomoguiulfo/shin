---
tags:
  - til
  - pattern
  - project/kanvify
---

# CLAUDE.md — Less Is More

ETH Zurich paper "Evaluating AGENTS.md" (Feb 2026, ICML 2026) found that auto-generated context files **reduce** agent performance by 2-3% while **increasing cost 20%+**. Even human-written files only help ~4%.

## What hurts

- **Codebase overviews** (stack tables, directory trees) — agents don't find files faster with them
- **Code examples of existing patterns** — redundant with what the agent reads in actual source files
- **Lengthy instructions** — increase reasoning tokens 14-22%, making tasks appear harder
- **Duplicated documentation** — when existing docs were removed, context files actually helped

## What to keep

Only non-discoverable information:
- Build/test/lint commands
- Gotchas and constraints (e.g., "ESLint bans useForm", "CI enforces unique public_id prefixes")
- Non-obvious conventions the agent can't infer from code
- "Exemplar" pointers to real files instead of code examples

## Applied to Kanvify

Trimmed 9 CLAUDE.md files from ~1,150 lines to ~148 lines (87% reduction). Deleted 2 files, gutted 6, kept ralph agent instructions untouched.

## Links

- [[Profile]] — evidence for "constraint quality > quantity"
- [[ai-and-software-engineering]] — same principle at the codebase level: semantic clarity > formal rigor

## Source

- Paper: arXiv:2602.11988 — Gloaguen et al., SRI Lab, ETH Zurich

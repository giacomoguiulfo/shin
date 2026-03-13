---
tags:
  - project/kanvify
repo: ~/Github/kanvify
github: https://github.com/plus-ultra-industries/kanvify
stack: Rails 8 + React 19 + Inertia.js + PostgreSQL
---

# Kanvify

Multi-platform social media scheduling and publishing platform with team workspaces. Supports Facebook, Instagram, Twitter/X, LinkedIn, TikTok, Pinterest, YouTube, and Threads.

## Why This Exists

Social media scheduling tools are either expensive enterprise SaaS or cheap but fragile. Kanvify targets the middle — teams and creators who need multi-platform publishing without the Buffer/Hootsuite price tag.

## Key Decisions

- **Rails + React via Inertia** — server-driven with rich frontend, no API layer to maintain
- **RLS-first multi-tenancy** — PostgreSQL row-level security instead of application-level scoping
- **Self-hosted via Kamal** — Docker deploy, no platform lock-in
- **Agent-friendly codebase** — CLAUDE.md files, hooks, and custom cops guide autonomous dev sessions

## Research & Connections

- [[creator-economics-as-moat]] — why creator tools have natural retention
- [[sota-models-over-custom-ones]] — using frontier models for AI features instead of fine-tuning
- [[commoditized-crawling-unlocks]] — relevant to platform API integration strategy

## Current State

_Last updated: 2026-03-09_

**Recent**: CLAUDE.md audit — reduced 9 files from ~1,150 to ~130 lines based on ETH Zurich "Evaluating AGENTS.md" paper. Added PreToolUse hooks and custom RuboCop cops as guardrails.

**Next**: Back to feature work. Consider more custom cops if agent keeps making scoped-lookup mistakes.

**Open questions**: None currently.

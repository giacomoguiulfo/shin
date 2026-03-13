---
tags:
  - project/gyo
repo: ~/Github/gyo
stack: Bun + TypeScript, Cloudflare Email Workers
---

# Gyo (凝)

*Hunter x Hunter technique: focus aura into your eyes to see what's hidden.*

Personal AI briefing tool that reads your newsletters and gives you back just the gyo — filtered by what actually matters to you.

## The Problem

You subscribe to 20 newsletters because the topics matter. You read 5 because you don't have time. The insights are buried in walls of text, and most of it isn't relevant to your life anyway.

## The Product

Forward your newsletters to Gyo. Every day, get a single digest with:
- What changed in your world
- Why it matters to you specifically
- Only the stuff that affects your life, work, or projects

Not "top 3 articles." More like: "here's what you need to know, in 60 seconds."

## The Bet

Nobody does "forward newsletters → get personalized briefing filtered by what matters to you." Existing tools (Meco, Stoop, Readwise Reader, Feedly) either organize or help you read more — none help you read *less*. The gap is a "so what?" layer that knows who you are.

## Path to MRR

1. **Personal tool** — build for yourself, validate that digests are actually useful
2. **Productize** — web app with onboarding, email delivery (most people don't have Obsidian), $10-15/month
3. **Grow** — Telegram/Slack delivery, team plans, RSS/web sources beyond newsletters

## Research & Connections

- [[information-diet-curation]] — Gyo is a focused implementation of Model 1 (The Personal Editor)
- [[personalized-so-what-layer]] — the "why it matters to you" intelligence layer; Gyo's relevance filter is a narrow version of this
- [[topic-level-curation]] — topic-following as one dimension of the curation problem
- [[trust-weighted-filtering]] — source credibility scoring; relevant for ranking newsletter signal quality

## Open Questions

- How aggressive to filter? Relevance threshold tuning
- Handling newsletters that are mostly links vs. mostly prose
- Japanese vs. English newsletter handling
- Domain name (gyo.app? gyo.so? usegyo.com?)

## Current State

_Last updated: 2026-03-11_

**Recent**: Repo scaffolded with Bun + TS. Core pipeline modules in place. Architecture settled: Cloudflare Email Workers for ingestion, Claude CLI for processing, cron for scheduling.

**Next**: Set up email forwarding, test with real newsletters, iterate on relevance filtering.

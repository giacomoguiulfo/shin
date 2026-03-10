---
tags:
  - tool-eval
  - revisit
date: 2026-03-10
verdict: revisit
---

# RedwoodSDK (rwsdk)

## What It Is

React framework built for Cloudflare Workers. Next evolution from the RedwoodJS team, but a radical departure — minimal, edge-native. https://rwsdk.com/

## Problem It Solves

Building full-stack React apps on Cloudflare's edge with first-class access to D1, R2, Durable Objects, Queues, and Cron — without the abstraction overhead of Next.js or Remix.

## Key Observations

- **React Server Components on Workers** — SSR via a Vite plugin, streaming responses
- **"Zero magic" philosophy** — No file-based routing, no code generation, no special file conventions. Explicit imports/exports only
- **Web-native** — Uses raw `Request`/`Response`/`fetch` instead of wrapping them. Middleware is just functions
- **Cloudflare-native** — D1, R2, Durable Objects, Queues all first-class. Not bolted on, it's the foundation
- **Early-stage** — Small ecosystem, thin community compared to Next.js/Remix

## Verdict

**Revisit.** The philosophy is appealing — "no magic" React with direct platform access. But:

- Locked into Cloudflare's ecosystem
- D1 is still maturing
- Edge-first has fundamental trade-offs for data-heavy apps (see [[edge-first-tradeoffs]])
- Framework is young, expect churn

Worth picking up if/when building something that genuinely benefits from edge compute (real-time collab, global low-latency reads, personalization). Not a default choice for CRUD apps.

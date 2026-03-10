---
tags:
  - til
  - architecture
date: 2026-03-10
---

# Edge-First Architecture — Where It Falls Apart

## The Core Tension

Edge compute puts code close to users, but data is rarely at the edge. Every DB query from a Worker in São Paulo to a database in Virginia adds latency — defeating the point.

## Where It Breaks Down

- **Data locality** — You either replicate globally (expensive, eventual consistency) or accept most requests round-trip to one region anyway
- **CPU limits** — Cloudflare Workers cap at ~30ms CPU. Heavy computation (image processing, PDF gen, complex aggregations) doesn't fit — you offload to a traditional server, adding architectural complexity
- **Immature data tooling** — D1 is SQLite-based, still young. ORMs on Workers have rough edges. Compare to Rails/Django where the data layer is solved
- **Auth/sessions** — Traditional session stores assume a single origin. Edge needs distributed state — JWTs help but have revocation/size trade-offs
- **Third-party services assume origin servers** — Payment processors, webhooks, email APIs expect a single endpoint with consistent IPs, not 300 PoPs
- **Observability** — Code runs across dozens of locations. Reproducing edge-specific bugs is painful. Logging/tracing tooling is still catching up

## Where It Actually Shines

- Auth gates, redirects, A/B tests
- Personalization
- Static sites with dynamic sprinkles
- Real-time collaboration (Durable Objects)
- API proxies, rate limiting

## The Rule of Thumb

Edge-first is a **topology optimization**, not an architecture improvement. If your bottleneck is network latency to users and your data model is simple or read-heavy, it's great. If your bottleneck is "query a relational database and do business logic," putting compute at the edge just moves the problem.

Most apps are better served by a single-region server close to their database, with a CDN in front. Edge is for the parts that genuinely benefit — not the whole stack.

## Context

Came up while evaluating [[Tool-Eval-RWSDK]].

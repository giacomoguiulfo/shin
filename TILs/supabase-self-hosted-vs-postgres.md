---
tags:
  - til
  - infrastructure
date: 2026-03-11
---

# Self-Hosted Supabase vs Plain PostgreSQL

## The Short Answer

If you're self-hosting, just run Postgres. Self-hosted Supabase is the worst of both worlds.

## What Self-Hosted Supabase Adds

- PostgREST (auto-generated REST API from schema)
- GoTrue (auth: email/password, OAuth, magic links)
- Realtime (websocket CDC)
- Storage (S3-compatible, tied to Postgres RLS)
- Edge Functions (Deno serverless)
- Studio (admin dashboard)

## Why It's Usually Not Worth It

- **~12 Docker containers** — Kong, GoTrue, PostgREST, Realtime, Storage, Studio, meta, imgproxy, etc. Significant operational overhead for what's mostly a database
- **Upgrades are painful** — you're managing a distributed system, not just a DB
- **Features degrade** — Edge Functions, branching, backups work worse or not at all vs Supabase Cloud
- **Redundant with an app server** — if you have one, PostgREST is unnecessary
- **You lose the main value prop** — Supabase's product is the managed cloud experience

## When It Makes Sense

- You want the Firebase-replacement DX on your own infra
- You'd otherwise wire up PostgREST + auth + realtime yourself
- You want RLS-driven auth flowing from DB to API automatically

## The Rule

Want Supabase DX? Use Supabase Cloud — that's the actual product. Want control? Run Postgres directly.

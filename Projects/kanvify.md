---
tags:
  - project/kanvify
repo: ~/Github/kanvify
github: https://github.com/plus-ultra-industries/kanvify
---

# Kanvify

Multi-platform social media scheduling and publishing platform with team workspaces.

## Stack

| Layer | Tech |
|-------|------|
| Backend | Rails 8.1, Ruby 4.0 |
| Frontend | React 19, TypeScript 5.9, Vite 7 |
| Bridge | Inertia.js |
| Database | PostgreSQL 17 (RLS-first, multi-db) |
| Styling | Tailwind CSS v4, shadcn/ui (Radix) |
| Serialization | Alba + Typelizer (auto-generates TS types) |
| Background Jobs | GoodJob |
| Payments | Stripe |
| Storage | Active Storage + S3 |
| Testing | Minitest (Ruby), Vitest (unit), Playwright (E2E) |
| Deployment | Kamal (Docker) |
| Marketing Site | Astro |
| Design System | Storybook |

## Key Conventions

- **Scope everything** through `Current.workspace`, `Current.user`, `Current.account`
- **Alba for all serialization** — never hand-roll JSON
- **Public IDs for URLs** — Stripe-style (`po_a8Kx3mNp2qR1`), numeric IDs internally
- **`db/schema.rb` is source of truth** — never read migrations
- **Models stay thin** — domain logic in concerns (`Post::Publishing`)
- **RLS policies** on all account/workspace-scoped tables
- **Commit format**: `type(scope): description`
- **Path aliases**: `@/*` → `app/frontend/*`, `@ui/*` → `ui/*`
- **Array type**: `Array<T>` not `T[]`

## Key Directories

```
app/models/         # ActiveRecord + domain concerns
app/controllers/    # Rails controllers (render Inertia pages)
app/resources/      # Alba serializers → TypeScript types
app/frontend/
  ├── pages/        # Inertia pages (file-based routing)
  ├── components/   # Reusable React components (shadcn/ui)
  ├── hooks/        # Custom React hooks
  ├── layouts/      # Layout components
  └── types/        # Auto-generated TS types (Typelizer)
lib/                # Platform API wrappers (Facebook, Twitter, etc.)
test/               # Minitest suite
e2e/                # Playwright E2E tests
site/               # Astro marketing site
```

## Context Files in Repo

- `/CLAUDE.md` — Main conventions (145 lines)
- `/app/models/CLAUDE.md` — Model patterns, concerns, POROs (427 lines)
- `/test/CLAUDE.md` — Testing patterns & exemplars
- `/db/CLAUDE.md` — Database conventions, RLS template
- `/.factory/README.md` — Autonomous agent system (Dark Factory)

## Supported Channels

Facebook, Instagram, Twitter/X, LinkedIn, TikTok, Pinterest, YouTube, Threads

## Dev Commands

```bash
bin/dev                          # Start all (Rails + Vite + GoodJob)
bin/rails test                   # Ruby tests
pnpm test                        # Vitest
pnpm run test:e2e                # Playwright
pnpm run lint && pnpm run check  # Type checking + ESLint
bin/rubocop                      # Ruby style
```

## Current State

_Last updated: 2026-03-09_

**Recent work**: CLAUDE.md audit based on ETH Zurich "Evaluating AGENTS.md" paper (ICML 2026). Reduced 9 CLAUDE.md files from ~1,150 to ~130 lines (87% reduction) by removing codebase overviews, code examples, and anything already enforced by tooling. Added new guardrails: PreToolUse hooks blocking `.rubocop_todo.yml` edits and `gh issue close`, custom `Kanvify::NoRenderJson` RuboCop cop. Created `/endsession` skill in the mind vault for session wrap-up.

**Next**: Consider more custom cops (scoped lookups, GlobalID job args) if agent keeps making those mistakes. Otherwise, back to feature work.

**Open questions**: None currently.

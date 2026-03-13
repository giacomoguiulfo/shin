---
tags:
  - project/kage-bunshin
repo: ~/Github/kage-bunshin
stack: TypeScript, Playwright, SQLite, Claude CLI
---

# Kage Bunshin (影分身)

AI-automated job search pipeline. Shadow clones hunt opportunities, tailor resumes, and fire off applications — Giacomo only steps in for interviews.

## Context

- Based in Japan, targeting globally remote US-based roles
- US work authorization (can work for US companies from Japan)
- Previous: FAANG, 330K USD/yr → Current: 80K USD/yr in Japan
- Target: 200-330K USD remote roles

## The Idea

Full pipeline from discovery to application, AI-driven at every stage:

**Discover** (scrape job boards) → **Score** (rank by fit, comp, Japan-remote compatibility) → **Tailor** (per-job resume + cover letter) → **Apply** (browser automation) → **Track** (pipeline dashboard) → **Prep** (interview research briefs)

Quality over quantity — 50 targeted apps > 500 spray-and-pray. High-value targets (FAANG network) get manual human touch.

## Key Constraints

- "Remote" often means US-only — aggressive filtering needed
- LinkedIn rate-limits scraping — need to be careful
- Some roles worth applying manually with warm intros
- ATS parsing varies — clean formatting matters

## Open Questions

- LinkedIn scraping without login is limited — authenticated scraping or different approach?
- Right balance between automated spray vs. curated high-touch?
- US mailing address / LLC for companies requiring US presence?

## Current State

_Last updated: 2026-03-11_

**Recent**: Repo scaffolded. Full CLI working: discover, score, tailor, status, list, show. Scrapers for LinkedIn + RemoteOK. AI scoring and resume tailoring via Claude CLI. SQLite tracking DB.

**Next**: Test discovery against real queries. Build more scrapers (Wellfound, WeWorkRemotely, HN). Build the `apply` command with Playwright form-filling.

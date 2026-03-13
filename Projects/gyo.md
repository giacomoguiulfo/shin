---
tags:
  - project/gyo
repo: ~/Github/gyo
---

# Gyo (凝)

*Hunter x Hunter technique: focus aura into your eyes to see what's hidden.*

Personal AI briefing tool that reads your newsletters and gives you back just the gyo — filtered by what actually matters to you.

## The Problem

You subscribe to 20 newsletters because the topics matter. You read 5 because you don't have time. You read 0 articles they link to. The insights are buried in walls of text, and most of it isn't relevant to your life anyway.

## The Product

Forward your newsletters to Gyo. Every day, get a single digest in your Obsidian vault with:
- What changed in your world
- Why it matters to you specifically
- Only the stuff that affects your life, work, or projects

Not "top 3 articles." More like: "here's what you need to know, in 60 seconds."

## Architecture (MVP)

```
Newsletters → Email Inbox → Parser → LLM (with personal context) → Daily Digest .md
```

### Components

| Component | Tech | Notes |
|-----------|------|-------|
| Email ingestion | IMAP polling on a custom domain | Forward newsletters to `read@gyo.domain` |
| Email parsing | HTML-to-text extraction | Strip formatting, images, ads, footers |
| Personal context | Static context file | Interests, location (Japan), projects, "I care about X" rules |
| Relevance filter | Claude API | "Does this affect Giacomo? Score 1-10" — drop anything below threshold |
| Summarization | Claude API | Per-newsletter summary → merged daily digest |
| Output | Markdown file | Drop into Obsidian vault daily |
| Scheduler | Cron job | Run once daily (e.g., 7am JST) |

### Personal Context File

A structured file that tells the LLM who you are and what you care about:

```yaml
name: Giacomo
location: Japan
languages: [English, Japanese]
roles: [founder, developer]
interests:
  - AI/ML tooling and agent frameworks
  - SaaS business building
  - Creator economy
  - Japan tech/startup scene
  - Immigration & visa policy (Japan)
filter_rules:
  - "Political news: only if it impacts daily life, taxes, immigration, or tech industry"
  - "AI news: focus on practical tools, not research papers unless breakthrough"
  - "Business news: focus on indie/bootstrapped, not enterprise"
projects:
  - Kanvify (social media scheduling)
  - Job search automation
  - Domain expansion / knowledge building
```

### Daily Digest Format

```markdown
---
date: 2026-03-11
sources: 8 newsletters processed
items: 12 relevant (34 filtered out)
---

# Daily Briefing — March 11, 2026

## Must Know
- **Japan immigration policy update:** New startup visa extension from 1→2 years effective April. Directly affects your visa status. [Source: Japan Times]

## Worth Knowing
- **Claude 4.5 tool-use improvements:** New parallel tool calling pattern reduces latency 3x. Relevant to Kanvify AI features. [Source: Superhuman AI]
- **Stripe launches in-app subscriptions for mobile:** Could simplify Kanvify's payment flow. [Source: TLDR]

## Noise Filtered
> 34 items skipped. Topics: US politics (8), celebrity news (3), enterprise SaaS fundraising (6), crypto prices (4), sports (3), other (10)
```

## Stack (MVP)

| Layer | Tech | Why |
|-------|------|-----|
| Runtime | Bun + TypeScript | Fast, native TS, zero config |
| Email ingestion | Cloudflare Email Workers + KV | Free, production-ready, no IMAP needed |
| HTML parsing | In the CF Worker (cheerio) | Parse at ingestion time |
| LLM | Claude Code CLI (`claude -p`) | No API key, uses existing subscription |
| Config | `yaml` | Personal context file |
| Output | Write `.md` file to vault path | Zero infrastructure |
| Scheduler | `cron` (macOS) | Simplest possible. No server needed for v0 |

See `PLAN.md` in the repo for detailed implementation steps.

## Path to MRR

### Phase 1: Personal Tool (Week 1)
- Build for yourself
- Local script, your email, your vault
- Validate that the digests are actually useful
- Iterate on the relevance filter and digest format

### Phase 2: Productize (Week 2-3)
- Web app with onboarding: "forward your newsletters here"
- User profile builder (replaces static context file)
- Email delivery (most people don't have Obsidian)
- Stripe subscription: **$10-15/month**

### Phase 3: Grow (Week 4+)
- Telegram/Slack delivery options
- "Why this matters" personalization depth
- Team plans ($30-50/user/month)
- API for developers
- Add RSS/web source ingestion (beyond newsletters)

## Competitive Landscape

| Product | What It Does | Gap |
|---------|-------------|-----|
| Meco | Newsletter inbox organizer | No summarization, no relevance filtering |
| Stoop | "Podcast app for newsletters" | No AI, no personalization |
| Readwise Reader | Read-later + highlights | Helps you read more, not read less |
| Superhuman AI | Email AI features | General email, not newsletter-specific |
| Kagi News | AI news synthesis | RSS-based, no newsletter ingestion |
| Feedly + Leo | AI feed reader | $1,600/mo enterprise tier, overkill |

**The gap:** Nobody does "forward newsletters → get personalized briefing filtered by what matters to you."

## Research

- [[information-diet-curation]] — the full landscape of information diet curation; Gyo is a focused implementation of Model 1 (The Personal Editor)
- [[personalized-so-what-layer]] — the "why it matters to you" intelligence layer; Gyo's relevance filter is a narrow version of this
- [[topic-level-curation]] — topic-following as one dimension of the curation problem
- [[trust-weighted-filtering]] — source credibility scoring; relevant for ranking newsletter signal quality

## Open Questions

- [ ] Domain name availability (gyo.app? gyo.so? usegyo.com?)
- [ ] Email domain for newsletter forwarding
- [ ] Relevance threshold tuning — how aggressive to filter?
- [ ] Handle newsletter formats that are mostly links vs. mostly prose
- [ ] How to handle newsletters in Japanese vs. English

## Current State

### Session: 2026-03-11
- Created project spec
- Identified MVP architecture: Bun/TS script + IMAP + Claude API + cron → Obsidian .md
- Defined personal context file approach for relevance filtering
- Mapped Phase 1-3 roadmap from personal tool to paid product
- Set up repo with Bun + TypeScript: `src/fetch.ts`, `src/digest.ts`, `src/render.ts`, `src/index.ts`
- **Next:** Set up email forwarding, configure `.env`, test with real newsletters.

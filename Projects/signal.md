---
tags:
  - project/gyo
repo: ~/Github/gyo
---

# Signal

Personal AI briefing tool that reads your newsletters and gives you back just the gyo — filtered by what actually matters to you.

## The Problem

You subscribe to 20 newsletters because the topics matter. You read 5 because you don't have time. You read 0 articles they link to. The insights are buried in walls of text, and most of it isn't relevant to your life anyway.

## The Product

Forward your newsletters to Signal. Every day, get a single digest in your Obsidian vault with:
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
languages: [English, Italian, Japanese]
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
| Language | Python | Fast scripting, great email/LLM libraries |
| Email | `imaplib` or `imap_tools` | Standard IMAP polling |
| HTML parsing | `beautifulsoup4` | Extract text from newsletter HTML |
| LLM | Claude API (`anthropic` SDK) | Best at nuanced relevance judgment |
| Output | Write `.md` file to vault path | Zero infrastructure |
| Scheduler | `cron` (macOS) | Simplest possible. No server needed for v0 |

Total infrastructure for v0: **zero.** It's a Python script on a cron job.

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

## Open Questions

- [ ] Domain name / product name (Signal is taken — working title only)
- [ ] Email domain for newsletter forwarding
- [ ] Relevance threshold tuning — how aggressive to filter?
- [ ] Handle newsletter formats that are mostly links vs. mostly prose
- [ ] How to handle newsletters in Japanese vs. English

## Current State

### Session: 2026-03-11
- Created project spec
- Identified MVP architecture: Python script + IMAP + Claude API + cron → Obsidian .md
- Defined personal context file approach for relevance filtering
- Mapped Phase 1-3 roadmap from personal tool to paid product
- **Next:** Build Phase 1 — the personal tool. Set up email forwarding, write the script, test with real newsletters.

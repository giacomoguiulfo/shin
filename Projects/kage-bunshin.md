---
tags:
  - project/kage-bunshin
repo: ~/Github/kage-bunshin
---

# Kage Bunshin (影分身)

AI-automated job search pipeline. Shadow clones hunt opportunities, tailor resumes, and fire off applications — Giacomo only steps in for interviews.

## Context

- Based in Japan, targeting globally remote US-based roles
- US work authorization (can work for US companies from Japan)
- Previous: FAANG, 330K USD/yr
- Current: 80K USD/yr in Japan
- Target: 200-330K USD remote roles

## Pipeline

```
Discovery → Filter/Rank → Tailor Resume → Apply → Track → Interview Prep
   AI          AI            AI            AI     AI         AI-assisted
```

### 1. Discovery (AI Agents)

Automated opportunity sourcing across multiple channels:

- **LinkedIn** — alerts + scraping for remote roles matching profile
- **Wellfound / Otta** — startup-focused, API-friendly
- **Hacker News Who's Hiring** — monthly threads, AI parses and filters
- **Levels.fyi** — comp data cross-reference
- **RemoteOK / WeWorkRemotely / Flexjobs** — broader net
- **Company career pages** — direct scraping of target companies

Target companies (Japan entity or true global-remote):
- FAANG with Japan offices (Google, Meta, Apple, Amazon)
- Global-remote: GitLab, Automattic, Zapier, Deel, Remote.com
- Crypto/Web3: Coinbase, Chainlink, Protocol Labs
- EOR-friendly Series B-D startups
- Companies using Deel/Remote/Oyster for international hires

### 2. Filter & Rank (AI Scoring)

Each opportunity scored on:
- Comp band (target 200K+ USD)
- Remote-from-Japan compatibility
- Role fit (seniority, stack, domain)
- Company stage & stability
- Visa/tax structure (direct hire vs EOR vs contractor)

### 3. Resume Tailoring (AI Generation)

- Master resume + context doc with all experience, projects, metrics
- Per-job tailored resume: rewrite bullets, reorder sections, keyword-match
- Per-job cover letter (where required)
- All generated artifacts stored for tracking

### 4. Application (AI + Automation)

- Auto-fill common fields (browser automation)
- Submit via platform APIs where possible
- Manual submission queue for high-value targets needing human touch

### 5. Tracking (Dashboard)

Pipeline stages:
- `discovered` → `qualified` → `applied` → `response` → `interview` → `offer`
- Track response rates, optimize resume versions
- Weekly digest of pipeline status

### 6. Interview Prep (AI-Assisted)

- Company-specific research briefs
- Role-specific technical prep plan
- Behavioral question prep with STAR stories from experience
- Salary negotiation strategy per company

## Key Assets to Build

| Asset | Description |
|-------|-------------|
| Master Resume | Complete experience doc — every bullet, metric, project |
| Profile Context | Skills, preferences, deal-breakers, salary expectations |
| Company Targets | Curated list with Japan-remote compatibility notes |
| Resume Templates | Base templates optimized for ATS parsing |
| Application Tracker | Structured data: company, role, status, dates, notes |

## Tech Considerations

| Layer | Options |
|-------|---------|
| Scraping/Discovery | Playwright, Puppeteer, API integrations |
| AI Engine | Claude for tailoring, scoring, prep |
| Automation | Browser automation for form filling |
| Tracking | Local DB or Airtable/Notion |
| Orchestration | Claude Code + worktree-pipeline |

## Constraints

- Many US roles saying "remote" mean US-only — need to filter aggressively
- ATS systems parse resumes differently — need clean formatting
- LinkedIn rate limits on scraping — need to be careful
- Quality over quantity — 50 targeted apps > 500 spray-and-pray
- Some roles worth applying manually with warm intros (FAANG network)

## Current State

_Last updated: 2026-03-11_

**Recent work**: Project created. Defined pipeline stages, target companies, and key assets.

**Next**:
- Build master resume/context doc (capture all FAANG experience, metrics, projects)
- Curate initial target company list with Japan-remote compatibility research
- Evaluate existing job search automation tools (LazyApply, Sonnet, Simplify, etc.)
- Design the discovery agent architecture

**Open questions**:
- Build custom tooling or leverage existing job-search automation platforms?
- What's the right balance between automated spray vs. curated high-touch applications?
- Should we set up a US mailing address / LLC for companies that require US presence?

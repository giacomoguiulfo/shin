---
tags:
  - til
  - infrastructure
  - business
date: 2026-03-13
---

# Commoditized Web Crawling Changes the Build-vs-Buy Math

## The Takeaway

Cloudflare's Browser Rendering `/crawl` endpoint (and similar services) commoditize what used to require dedicated crawl infrastructure — Scrapy clusters, proxy rotation, scheduling, diffing. When crawling becomes a single API call with incremental support and structured extraction built in, every business that depends on "what's on the web and what changed" gets dramatically cheaper to build.

## What It Unlocks

- **Incremental crawling as a primitive** — `modifiedSince` and `maxAge` as first-class params eliminate the need to build your own change-detection layer. This is the real value; most crawl setups are either "everything every time" or custom diffing.
- **Crawl + parse in one step** — Structured JSON output via Workers AI collapses the traditional crawl-then-extract pipeline into a single call.
- **Compliance by default** — Respects `robots.txt` and AI Crawl Control, identifies as a bot. Removes the ethical/legal gray area of rolling your own scraper.

## Business Patterns This Enables

1. **Competitive intelligence SaaS** — monitor competitor sites for changes weekly
2. **Content freshness monitoring** — SEO agencies tracking stale content at scale
3. **Regulatory/policy alerting** — crawl government sites, flag changes (immigration, tax, compliance)
4. **RAG pipeline bootstrapping** — go from "I need domain knowledge" to populated vector store in one call
5. **Price/market data tracking** — structured extraction from product pages across retailers

## Rule of Thumb

When a capability moves from "build infrastructure" to "make an API call," look for businesses that were previously gated by that infrastructure cost. The winners are vertical tools that combine cheap crawling with domain-specific intelligence on top.

## Context

Came up evaluating Cloudflare's new `/crawl` endpoint. Relevant to [[gyo]] Phase 3 (RSS/web source expansion) and link dereferencing in newsletter digests.

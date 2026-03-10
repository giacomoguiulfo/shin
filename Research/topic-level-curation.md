---
tags:
  - research
  - social-media-futures
  - curation
date: 2026-03-11
---

# Topic-Level Curation

The idea: instead of following *people*, you follow *topics* — and get the most important updates curated for you. "The 5 most important things in WebAssembly this week." This is a survey of who's trying, what's broken, and where the real opportunity lives.

## Landscape

### Human-Curated Newsletters (The Incumbent Model)

The newsletter boom proved that topic curation has massive demand. The economics are strong, but the model is inherently unscalable — each vertical requires a dedicated human editor.

| Player | Model | Scale | Revenue/Status |
|--------|-------|-------|----------------|
| **TLDR** | Daily tech digest, ad-sponsored | 1.2M+ subscribers | ~$5-7M/yr revenue, 4-person team, bootstrapped |
| **Morning Brew** | Daily business news + 8 professional verticals (marketing, HR, tech, CFO, retail, healthcare) | 4.4M subscribers (flagship) | ~$70M+ across consumer + B2B; B2B surpassed consumer in 2025 ($25M) |
| **Superhuman AI** | Daily AI digest, "smarter about AI in 3 min" | 1M+ subscribers | 7-figure revenue within 4 months; ad spots consistently sold out |
| **Hacker Newsletter** | Weekly hand-curated HN best-of | 60,000+ subscribers | Running since 2010; small but durable |
| **Dense Discovery** | Design/tech/culture weekly curation | Niche but influential | Paid subscriptions + sponsorship |
| **Specialized Substacks** | Hyper-niche curation (e.g., Midjourney prompts, hospitality marketing) | Small but high-conversion (4-10% paid conversion vs. 1-2% for broad) | Higher CPMs; 5K niche subscribers worth more than 50K general |

**Key insight:** Niche newsletters command disproportionate value. A 5,000-subscriber newsletter where every reader is an HR leader is worth more to sponsors than a 50,000-subscriber general one. Paid conversion rates are 4-10x higher in tight niches.

### Platform Topic-Following Features

Every major platform has tried topic-following. None do it well.

- **Twitter/X Topics** (launched 2019): Follow topics to see related tweets in your timeline. In practice, the algorithm surfaces low-quality, engagement-optimized content. The timeline is "absolutely saturated with low-quality content" — Twitter treats noise like signal. Topic follows inject viral tweets, not important ones.
- **Reddit Subreddits**: The closest thing to working topic-following. But quality degrades with scale (r/programming vs. r/ExperiencedDevs), moderation is volunteer-dependent, and there's no cross-subreddit synthesis. You get raw firehose, not curated digest.
- **Quora Spaces**: Collaborative topic blogs with editorial control. Quality is abysmal — "if 80% of Quora content is utter crap, 90% of Spaces are fetid crap." Quora closed several Space features in late 2024.
- **Google Alerts**: Free, simple, terrible. Research shows only ~10% relevance with 40% of important news never detected. Purely keyword-based with no semantic understanding.
- **Twitter Lists**: Powerful but manual. You're still following people, not topics — and maintaining lists is ongoing work nobody does.

### AI-Powered News Aggregators

A wave of AI news apps has emerged, but most optimize for *general news consumption*, not deep topic tracking.

- **Artifact** (Instagram founders): Launched Feb 2023, shut down Jan 2024. Only 444K total downloads. Failed due to insufficient demand, loss of focus (pivoted toward Pinterest/Twitter features), no revenue model, and geographic limitations (44% US, no country above 4%). Lesson: founder pedigree cannot overcome weak product-market fit in a competitive consumer market.
- **Particle News**: AI-powered newsreader with multi-source headlines, AI summaries, entity pages, and chatbot Q&A. Covers broad categories (tech, sports, politics). More interactive than Artifact but still general-purpose.
- **Kagi News**: AI-generated daily summaries from thousands of RSS feeds. Free, customizable topic areas, one update/day at noon UTC. Closer to the "digest" model but lacks depth and niche specialization.
- **News Minimalist**: Uses GPT-4 to score thousands of articles daily on a 0-10 significance scale. Prioritizes significance over popularity — an interesting signal, but still broad news.
- **Bulletin**: Post-Artifact AI news reader focused on anti-clickbait summaries (launched early 2024).
- **Upstract**: Aggregates Reddit, Google News, Reuters, Medium, CNN onto one page with trending topic highlights.

### AI-Powered Feed Readers & Intelligence Platforms

- **Feedly + Leo AI**: The most mature topic intelligence product. Born as RSS reader (2008), became business intelligence platform. Leo AI filters, deduplicates, summarizes, and detects emerging trends across websites, newsletters, blogs, Reddit, X, forums, even dark web. Topic AI Model prioritizes keywords, mentions, trends. Serves enterprise customers. **But**: full features require ~$1,600/month (Enterprise tier), and it's fundamentally a power-user tool, not a consumer product.
- **Readwise Reader**: Read-it-later app with daily digest that clusters items by theme and summarizes what's interesting. MCP server integration for AI access to your reading history.

### Competitive Intelligence / Enterprise Monitoring

The enterprise market has well-funded players doing topic monitoring for business:

- **Crayon**: AI-driven competitive intelligence. Summarizes and importance-scores competitor activity. 68% of deals now face direct competition per their 2025 report.
- **AlphaSense**: Market intelligence used by 85% of S&P 100. AI search across 10,000+ data sources (earnings calls, SEC filings, broker research). Premium enterprise pricing.
- **Contify**: AI + NLP across 1M+ public sources for competitive intelligence newsfeeds.
- **Klue**: Competitive enablement — battlecards, dashboards, real-time alerts for sales teams.
- **Brand24 / Meltwater / Awario / Talkwalker**: Social listening and brand monitoring. Track mentions across social, news, blogs, review sites. Sentiment analysis, influencer scoring.

### Emerging AI Agent Approaches

- **Alertmouse** (Rand Fishkin, late 2025): Built as explicit Google Alerts replacement. Broader coverage, smarter filtering, exact phrase matching, site blocking. From SparkToro/Moz founder — credibility in the space.
- **SignalHub**: Combines user-selected sources with plain-language AI filtering plus push notifications to Slack, Discord, Telegram, webhooks. Addresses the gap where Feedly charges $1,600/month for Slack integration.
- **Yutori Scouts**: AI agents that run Google searches on schedules with AI filtering (~1M tokens per analysis). Ex-Meta researchers. Acknowledges ~10% error rate. Trades user control for convenience.
- **Perplexity Discover Daily**: AI-curated daily stories + real-time newswire feeds for equities. Watchlist with AI-generated market synthesis. Moving toward personalized topic monitoring.
- **DIY workflows (n8n, Make)**: Growing ecosystem of "build your own AI digest" automations — fetch from HN/RSS/APIs, filter with GPT, email daily digest. Sign that the product doesn't exist yet and power users are building it themselves.

## What's Broken

### 1. The Depth Problem
No existing tool understands a topic deeply enough to rank *importance within a niche*. GPT can summarize an article, but can it tell you that a particular WebAssembly proposal matters more than a new WASM runtime? That requires understanding the field's trajectory, key debates, and what practitioners actually care about. Current AI curation operates at the "keyword match + engagement signal" level, not the "domain expert judgment" level.

### 2. The Source Problem
Important developments in niche topics don't all happen in one place. A WebAssembly breakthrough might surface as a GitHub PR, a W3C spec discussion, a conference talk, a tweet thread, a blog post, and a Reddit comment — all separately. No tool does cross-source synthesis well. Feedly comes closest but requires manual source configuration and enterprise pricing.

### 3. The Signal-vs-Engagement Problem
Platform algorithms optimize for engagement (clicks, likes, shares), not importance. This systematically biases toward controversy, novelty, and emotional content over substantive developments. Research confirms: engagement-driven curation leads to "algorithmic sensationalism, where content is shaped to provoke rather than to inform."

### 4. The Scalability-vs-Quality Tradeoff
Human-curated newsletters have quality but can't scale. Each vertical needs a dedicated expert editor (Morning Brew runs 8 verticals with specialized teams). AI tools scale but produce generic, surface-level output. Nobody has cracked the middle: AI that curates with expert-level judgment across hundreds of niches simultaneously.

### 5. The Cold Start Problem
Following a new topic requires you to already know the landscape — which sources matter, which voices are authoritative, what the key debates are. Platforms offer "follow this topic" but don't help you understand the topology of the field. You get a firehose from day one with no ramp.

### 6. The Notification/Delivery Problem
Even when tools curate well, delivery is broken. Google Alerts emails get buried. App notifications get ignored. RSS readers require active checking. The gap is: curated, important updates delivered to wherever you already are (Slack, Discord, email, SMS) with the right cadence (not every article — a weekly synthesis).

### 7. Artifact's Lesson: Consumer News is a Trap
Artifact proved that "better AI-powered general news" is not a viable market. SmartNews, Google News, and Apple News own the general case. The opportunity is in *specificity* — niches where the cost of ignorance is high and existing coverage is poor.

## Business Opportunities

### The Obvious Gap: AI-Powered Niche Curation at Scale
The whitespace is: Morning Brew quality at TLDR scale across hundreds of verticals, powered by AI instead of human editors. A system that can spin up a new "WebAssembly Weekly" or "Kubernetes Security Digest" with expert-level curation quality, without needing a human domain expert for each one.

**Why now:** LLMs can now read, summarize, and compare technical content with reasonable accuracy. Combined with broad source ingestion (RSS, GitHub, social, forums, specs), the technical foundation exists. What's missing is the ranking layer — teaching AI what matters *within* a domain.

### Model 1: Prosumer Topic Intelligence ($10-30/month)
- Pick your topics from a long-tail catalog (not just "tech" — but "Rust async runtime development" or "EU AI regulation")
- Get a weekly or daily digest with importance-ranked items
- Progressive depth: headline → summary → full analysis → source links
- Cross-source synthesis: "This week's most important development was X, which appeared across [GitHub PR], [blog post], and [HN discussion]"
- Position: Feedly Leo for individuals, without the $1,600 enterprise price tag

### Model 2: Professional/Enterprise Topic Monitoring
- Competitive intelligence for specific technology domains
- Regulatory monitoring for specific industries
- Market signal detection (new entrants, funding, product launches, hiring patterns)
- Existing players (Crayon, AlphaSense, Contify) charge enterprise prices ($10K+/year) and focus on competitive intelligence. Opportunity to serve mid-market ($50-500/month) with AI-native architecture.

### Model 3: Community-Validated Curation Network
- Combine AI pre-filtering with community upvoting/validation
- Expert curators earn reputation in their niches (like Stack Overflow for curation)
- AI handles the 90% (source ingestion, deduplication, summarization), humans handle the 10% (importance ranking, context, "why this matters")
- Revenue: subscriptions for consumers, API/feeds for enterprises, sponsored placements for vendors

### Model 4: Newsletter Infrastructure (Picks-and-Shovels)
- Platform that lets anyone launch an AI-assisted niche newsletter
- AI handles source monitoring, draft generation, trending topic detection
- Human editor adds voice, judgment, context
- Revenue: SaaS fees to newsletter operators + rev share on ads
- Beehiiv and ConvertKit are moving this direction but haven't solved the AI curation layer

### Addressable Market Signals
- Newsletter industry growing rapidly (Morning Brew $75M exit, TLDR $5-7M/yr bootstrapped, Superhuman AI 7-figure monthly)
- AI agent market: $5.25B (2024) → projected $52.62B (2030)
- Competitive intelligence tools market well-established at enterprise tier
- DIY automation workflows (n8n, Make) show unmet demand — people are building this themselves

## Breakthrough Ideas

### 1. The "Domain Model" Approach
Instead of general-purpose AI + keyword matching, train (or fine-tune) specialized models that understand individual domains deeply. A WebAssembly curation model would understand the difference between a spec proposal and a tutorial, know which authors are core contributors vs. commentators, and recognize when a PR to a key repo signals a paradigm shift. This is the equivalent of having a domain expert editor — but one that scales across hundreds of niches. The training data exists: years of HN discussions, Reddit threads, GitHub activity, conference talks, and newsletter archives encode collective expert judgment about what matters.

### 2. Progressive Depth Interface
Most curation is flat: here's a list of links. Instead, offer progressive disclosure:
- **Level 0 — The number**: "3 important things happened in WebAssembly this week"
- **Level 1 — Headlines**: One-line descriptions
- **Level 2 — Summaries**: 2-3 paragraph synthesis with context
- **Level 3 — Full analysis**: Deep dive with cross-references, history, implications
- **Level 4 — Source material**: Original links, discussions, code

Users choose their depth per topic, per day. Monday morning: Level 1 scan of 20 topics. Tuesday afternoon: Level 3 deep dive on the one that matters. This maps to how experts actually consume information.

### 3. Importance Signals Beyond Engagement
Build a multi-signal importance ranking that goes beyond clicks and likes:
- **Author authority**: Is this from a core maintainer, a spec editor, a known expert? (GitHub commit history, conference speaking, citation networks)
- **Structural significance**: Does this change a spec? Merge a major PR? Shift a roadmap? (Parse changelogs, release notes, meeting minutes)
- **Community expert attention**: Are known experts engaging with this? (Track engagement from curated "expert lists" per domain)
- **Cross-source resonance**: Is this being discussed across multiple independent venues? (Triangulate GitHub + HN + Twitter + blogs)
- **Novelty vs. domain state**: Is this genuinely new, or a rehash of known information? (Compare against knowledge graph of the domain)

### 4. The "Briefing Room" Model
Instead of static digests, create a conversational interface:
- "What happened in WebAssembly this week?" → structured briefing
- "Why does the component model proposal matter?" → contextual deep dive
- "How does this compare to what was happening 6 months ago?" → temporal analysis
- "What should I read first?" → personalized priority ranking based on your role and knowledge level

This is essentially Perplexity but specialized for ongoing topic monitoring rather than one-off queries. The key differentiator: it maintains state across sessions, building a model of what you already know and what you care about.

### 5. Cross-Topic Synthesis
The most valuable insights often come from connections *between* topics. A development in WebAssembly + a development in edge computing + a new Cloudflare product launch = a trend worth knowing about. No tool does this today. An AI system monitoring 50+ topics simultaneously could surface these cross-domain patterns that no single-topic newsletter would catch.

### 6. The "Curate Once, Distribute Everywhere" Platform
Build the curation engine once, then output to every format:
- Weekly email digest for casual followers
- Daily Slack/Discord notification for active practitioners
- RSS feed for power users
- API endpoint for tools and dashboards
- Podcast script for audio consumption
- Widget embeddable in docs/portals

The same ranked, synthesized content — adapted to every consumption pattern. Currently everyone builds one output format and ignores the rest.

### 7. Expertise-Aware Personalization
Not just "topics you follow" but "topics at your level." A WebAssembly core contributor and a curious frontend developer both follow "WebAssembly" but need completely different curation. The contributor needs: spec proposals, VM implementation details, benchmark changes. The developer needs: new framework support, tutorial-level explainers, adoption milestones. Current tools treat all followers identically.

## Sources

### Newsletters & Curated Content
- [TLDR Newsletter Business Analysis](https://growthinreverse.com/tldr/)
- [Morning Brew $70M+ Media Empire](https://newsmachines.substack.com/p/how-morning-brew-uses-data-to-grow)
- [Morning Brew Growth Strategy](https://www.marketergems.com/p/morning-brew-newsletter-growth-strategy-case-study)
- [Superhuman AI Newsletter](https://www.superhuman.ai/)
- [Superhuman Newsletter Growth](https://www.creatorspotlight.com/p/superhuman)
- [Best Curated Newsletters 2025 — Robin Good](https://robingood.substack.com/p/the-best-curated-newsletters-of-2025)
- [Rise of Vertical Newsletters — Beehiiv](https://blog.beehiiv.com/p/the-rise-of-vertical-newsletters)
- [Hacker Newsletter](https://hackernewsletter.com/)

### AI News Aggregators
- [Why Artifact Failed — Failory](https://newsletter.failory.com/p/why-artifact-failed)
- [Artifact Shutdown — TechCrunch](https://techcrunch.com/2024/01/18/why-artifact-from-instagrams-founders-failed-shut-down/)
- [Particle News Web Launch — TechCrunch](https://techcrunch.com/2025/05/06/particle-brings-its-ai-powered-news-reader-to-the-web/)
- [Kagi News — Nieman Lab](https://www.niemanlab.org/2025/10/kagi-news-is-an-ai-powered-app-for-keeping-up-with-the-world/)
- [News Minimalist](https://opentools.ai/tools/news-minimalist)
- [Bulletin AI News Reader — TechCrunch](https://techcrunch.com/2024/02/15/bulletin-is-a-new-ai-powered-news-reader-that-tackles-clickbait-and-summaries-stories/)

### AI Curation & Intelligence Tools
- [Feedly AI](https://feedly.com/ai)
- [Feedly Review 2026](https://salesdorado.com/en/monitoring-software/review-feedly/)
- [Best AI Content Curation Tools 2025](https://influencermarketinghub.com/ai-content-curation-tools/)
- [Best Web Monitoring Tools 2026 — SignalHub](https://getsignalhub.com/blog/the-best-web-monitoring-tools-in-2026-from-google-alerts-to-ai-agents)
- [Google Alerts Alternatives 2026](https://awario.com/blog/best-google-alerts-alternatives/)
- [Competitive Intelligence Tools 2026 — Contify](https://www.contify.com/resources/blog/best-competitive-intelligence-tools/)
- [Competitive Intelligence Tools — AlphaSense](https://www.alpha-sense.com/blog/product/competitive-intelligence-tools/)

### Platform Topic Features
- [Twitter Signal-to-Noise — Medium](https://medium.com/enrique-dans/twitter-and-the-signal-to-noise-ratio-b038ddd614e2)
- [Twitter Algorithm 2025](https://xbeast.io/blog/twitter-algorithm-2025-tweets-disappear-fix)
- [Quora Spaces Problems — Medium](https://medium.com/illumination/what-is-happening-to-quora-spaces-8b4da05c021e)

### Editorial Judgment & AI Limitations
- [NYT Editorial Judgment in Algorithms — Nieman Lab](https://www.niemanlab.org/2024/10/how-the-new-york-times-incorporates-editorial-judgment-in-algorithms-to-curate-its-home-page/)
- [Algorithmic Recommendation vs. Human Curation — CMU](https://www.heinz.cmu.edu/media/2023/November/algorithmic-recommendation-technology-or-human-curation-study-of-online-news-outlet-in-germany-suggests-both)
- [AI Content Curation Changes Newsletter Creation](https://curatedletters.com/ways-ai-content-curation-changing-newsletter/)

### Market & Trends
- [AI Agent Market Growth](https://aifundingtracker.com/top-ai-agent-startups/)
- [AI Agent Startup Ideas 2026](https://wearepresta.com/ai-agent-startup-ideas-2026-15-profitable-opportunities-to-launch-now/)
- [Perplexity Discover Daily](https://www.perplexity.ai/podcast)
- [LetMeKnow.News](https://letmeknow.news/)

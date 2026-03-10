---
tags:
  - research
  - social-media-futures
  - curation
date: 2026-03-11
---

# Information Diet Curation

The idea: a single layer that curates your *entire* information intake across all platforms and sources. Not just news, not just one vertical -- everything. "Here's what matters to you today." A personal editor for your information diet.

This is distinct from [[topic-level-curation]] (following specific topics deeply) and [[trust-weighted-filtering]] (ranking by source credibility). This note is about the *meta-product* -- the unified intake layer that sits across all your information sources and tells you what to pay attention to.

---

## Landscape

### The Fragmentation Problem

The average knowledge worker's information intake is scattered across 8-12 surfaces:

| Surface | What it delivers | Curation model |
|---------|-----------------|----------------|
| **Email inbox** | Newsletters, work comms, alerts | Chronological + spam filter |
| **Twitter/X** | Real-time discourse, breaking news | Engagement-optimized algorithm |
| **LinkedIn** | Professional updates, industry news | Engagement + network proximity |
| **RSS reader** | Blog posts, publications | Chronological, no ranking |
| **Podcasts** | Long-form audio | Manual subscription |
| **YouTube** | Video essays, tutorials | Recommendation algorithm |
| **Reddit** | Community discussion, niche topics | Upvote-driven |
| **Slack/Discord** | Team + community conversation | Unread counts |
| **Substack/newsletters** | Curated analysis | Author-selected |
| **Group chats** | Peer recommendations | Social trust |
| **Apple/Google News** | Broad news | Editorial + algorithmic |
| **Hacker News** | Tech signal | Community voting |

Nobody has built the layer that sits *above* all of these and says: "Across everything you consume, here are the 7 things that actually matter to you today."

### Existing Players by Category

#### News Aggregators (Broad)

**Apple News** -- Free + Apple News+ ($12.99/month). Editor-curated + algorithmic. 400+ premium publications in News+. 4.6-star rating, 1.5M reviews. Strength: editorial quality, native iOS integration. Weakness: Apple ecosystem only, no cross-platform ingestion, no personalization beyond topic following. Doesn't touch your email, RSS, podcasts, or social feeds.

**Google News** -- Free, ad-supported. AI-powered personalization, Full Coverage feature showing multiple perspectives. Massive scale. Weakness: optimizes for engagement/clicks, no deep personalization, doesn't aggregate beyond news articles. Google's incentive is keeping you in Google's ecosystem, not curating your whole diet.

**SmartNews** -- Free, ad-supported. 50M+ downloads, 4,500+ publisher partners. Political spectrum slider. Algorithmic + editorial curation. Weakness: still just news articles, no cross-platform integration, ad-driven incentives.

**Flipboard** -- Free, ad-supported. "World's first social magazine." Now integrates with Fediverse (Threads, Mastodon, Bluesky). User-created magazines. Recently launched "Surf" and "Trending." Weakness: discovery-oriented, not diet-oriented. Helps you find more to read, not less.

**Ground News** -- Freemium subscription. Aggregates from 50,000+ sources, shows media bias ratings and ownership data alongside stories. Unique angle on perspective diversity. Weakness: bias lens is valuable but narrow; still just news, no cross-platform integration.

#### The Artifact Story (The Cautionary Tale)

**Artifact** (2023-2024) -- Founded by Instagram co-founders Kevin Systrom and Mike Krieger. Launched Feb 2023 as "TikTok for text" -- an AI-powered personalized news feed. Added features rapidly: AI headline rewriting (anti-clickbait), emoji reactions, article flagging, "Links" discovery, AI text-to-speech with celebrity voices, social "Posts" feature, AI image generation.

Shut down January 2024 after less than a year. Systrom's stated reason: **"the market opportunity isn't big enough to warrant continued investment"** despite building "something that a core group of users love." Only ~444K total downloads. 44% US users, no other country above 4%.

Yahoo acquired the technology in April 2024 to integrate into Yahoo News.

**Why Artifact matters for this research:**
- Proved that even legendary founders with deep pockets couldn't make "better AI news feed" work as a standalone consumer product
- Lost focus by bolting on social features (Posts, Links) instead of deepening the core curation
- Competed with free, pre-installed defaults (Apple News, Google News) that are "good enough"
- News-only scope was too narrow to justify a separate app
- The lesson: a better *news* feed is not the product. The product has to be a better *information* feed across everything

#### RSS Readers (Power Users)

**Feedly** -- The most mature player. Born as RSS reader (2008), pivoted hard to enterprise intelligence platform. Three products: Threat Intelligence, Market Intelligence, and personal News Reader. Leo AI filters, deduplicates, summarizes, detects trends. Enterprise customers include Cloudflare, Verizon, Lufthansa, Airbus. Full AI features require ~$1,600/month Enterprise tier. The personal reader is a shadow of the enterprise product.

**Inoreader** -- RSS + social listening (Facebook, Telegram, Mastodon, Reddit, YouTube) + newsletters + web monitoring. AI article summaries and smart tags on Pro ($7.50/month annual). 2,500 feed limit on Pro. Monitoring feeds in 30+ languages. More consumer-friendly than Feedly but still fundamentally an RSS reader with bolted-on features.

**Reeder** (app, $9.99 one-time) -- Beautiful RSS reader rebuilt over 15 years. Now aggregates RSS, videos, podcasts, social media into unified timeline. iCloud sync. Custom filters. Clean and focused but no AI, no cross-platform ingestion beyond RSS, no "what matters" ranking.

#### Read-It-Later / Knowledge Management

**Readwise + Reader** ($9.99/month Full) -- The closest thing to a unified reading layer. Reader supports RSS, newsletters, PDFs, EPUBs, YouTube transcripts, Twitter threads, web articles. Ghostreader AI copilot (GPT-powered Q&A, summaries, term definitions). Syncs highlights to Obsidian, Notion, Logseq. Strong power-user following. Weakness: it's a *reading app*, not a *curation layer*. It organizes what you've already chosen to read; it doesn't tell you what matters across your intake.

**Omnivore** -- Open-source read-it-later app. Supported newsletters, RSS, highlights, Obsidian/Logseq plugins. Cloud version deprecated November 2024; now self-hosted only. Demonstrates both the demand and the sustainability challenge for open-source consumer tools.

#### Newsletter Aggregators

**Meco** -- "#1 newsletter reader." Pulls newsletters out of your email inbox into a dedicated reader. Declutters inbox. Free + premium tiers. The pitch: newsletters don't belong in email. Weakness: only handles newsletters, not the full information diet.

**Stoop** -- "Like a podcast app but for newsletters." Discovery, subscription management, one-click unsubscribe. Free + $10/year premium. Appears largely dormant (copyright 2019, iPhone still "coming soon" at time of last update). Illustrates the graveyard of newsletter-only tools.

**Mailbrew** -- Creates personalized email digests from multiple sources (RSS, Reddit, Hacker News, YouTube, Twitter, stocks, weather, Google Calendar). Automated delivery on schedule. Closer to the "unified digest" concept but still user-configured, not AI-curated.

#### Human-Curated Newsletters (The Analog Model)

**The Browser** -- Daily newsletter, 5 outstanding articles. 150,000+ subscribers. Human-curated by editorial team. Selection criteria: "Would we recommend it to friends? Will it delight intelligent general readers? Will it remain valuable a month later?" This is the *taste* model -- a human editor with good judgment. Doesn't scale, doesn't personalize, but proves people will pay for curation quality.

**TLDR** -- Daily tech digest. 1.6M subscribers on flagship, 6M+ total across 12 vertical newsletters. Ad-supported (free to readers). ~$5-7M/yr revenue, small team. Proves curation at scale works commercially, but it's one-size-fits-all within each vertical.

**Morning Brew** -- Daily business news. 4.4M subscribers flagship. $70M+ revenue across consumer + B2B. Exited to Business Insider for $75M. B2B verticals now outpacing consumer. The success story for newsletter-as-business.

**Superhuman AI Newsletter** -- Daily AI digest. 1M+ subscribers. 7-figure revenue within 4 months of launch. Proves massive demand for niche curation.

#### AI Assistants Encroaching on This Space

**Perplexity** -- AI search engine with Discover feature showing curated daily stories and real-time newswire feeds. Moving toward personalized topic monitoring. The "answer engine" is becoming a curation engine, but discovery is secondary to its search function.

**ChatGPT with Search** -- OpenAI integrated web search into ChatGPT. Users can ask "what happened today in AI?" and get a curated briefing. Ad-hoc, not systematic. No persistent preferences or ongoing monitoring. But the interaction model is right: conversational, contextual, adjustable depth.

**Kagi** -- Premium search engine ($5-25/month). Offers Small Web (curated human knowledge directory), Summarizer, and Kagi News (AI-generated daily summaries from thousands of RSS feeds). Philosophy of "you are the customer, not the product." Closer to the right model (user-pays, no engagement incentives) but search-first, not curation-first.

#### The DIY Power-User Stack

A growing ecosystem of people building their own information diet curation:
- **n8n / Make / Zapier** workflows: fetch from HN/RSS/APIs, filter with GPT, email daily digest
- **Custom scripts** pulling from multiple APIs, ranking with LLMs, pushing to Slack/email
- **Obsidian + Readwise** as knowledge capture layer
- **IFTTT / Huginn** for cross-platform automation

The existence of this DIY movement is the clearest signal that the product doesn't exist yet. When power users are duct-taping solutions together, there's a product waiting to be built.

---

## What's Broken

### 1. The Cross-Platform Ingestion Problem

The fundamental technical challenge: your information comes from a dozen different platforms, each with different APIs (or no API), rate limits, authentication, and data formats. Building a unified ingestion layer requires:
- RSS/Atom parsing (the easy part)
- Email parsing for newsletters (doable but fragile -- formats change)
- Twitter/X API (expensive, unreliable, rate-limited, recently restricted)
- Reddit API (pricing controversy in 2023 killed many third-party apps)
- YouTube Data API (quota limits)
- Podcast RSS (standardized but audio requires transcription)
- LinkedIn (no public API for feed data)
- Slack/Discord (requires app installation with permissions)
- Hacker News API (open but basic)
- Substack (no official API)

Most platforms are actively hostile to data extraction because your attention is their product. They have zero incentive to let a meta-layer sit on top and redirect your attention elsewhere. This is why nobody has built the unified layer -- the platforms won't cooperate.

### 2. The "Good Enough" Default Problem

Apple News comes pre-installed on every iPhone. Google News is a tap away on Android. Both are free, decent, and familiar. The bar for displacing a default is astronomically high -- you need to be not 10% better but 10x better to justify the switching cost of installing a new app, configuring sources, and building new habits.

Artifact learned this the hard way: even with AI-powered personalization from Instagram's founders, "good enough" defaults won. The market isn't "people who want better news" (that's everyone) -- it's "people who want better news badly enough to change their behavior" (that's a small, non-venture-scale number for news alone).

### 3. The Personalization Cold Start

True personalization requires deep understanding of your interests, expertise level, professional context, and information goals. Current approaches:
- **Explicit preferences** (pick your topics): too coarse. "Technology" means nothing. Even "AI" is too broad.
- **Behavioral signals** (what you click/read): biased toward engagement, not importance. You click on celebrity gossip; you *need* to read the regulatory update.
- **Social graph** (what your network shares): the Nuzzel model. Worked well but died when Twitter API access was restricted. Network-dependent.
- **Professional context** (job title, industry): LinkedIn has this data but doesn't use it for curation.

The gap: no product learns your information *needs* (what you should know for your job, your projects, your decisions) as distinct from your information *wants* (what's entertaining, novel, emotionally engaging).

### 4. The Engagement-vs-Importance Misalignment

Every ad-supported platform optimizes for engagement metrics (clicks, dwell time, shares). This systematically biases toward:
- Controversy over substance
- Novelty over importance
- Emotion over information
- Breadth over depth

Research (PNAS Nexus, 2025) showed Twitter's engagement algorithm amplifies content that makes users feel *worse* -- anger, sadness, anxiety. A stated-preference timeline reduced negative emotions but platforms won't adopt it because engagement = ad revenue.

An information diet curator must optimize for *importance to you* -- which is a fundamentally different objective function. This requires a business model aligned with user value (subscription), not advertiser value (engagement).

### 5. The Scope Problem (Why Nobody Has Won)

Every player in this space has chosen a scope that's too narrow:
- News aggregators: only news articles
- RSS readers: only sources with RSS feeds
- Newsletter aggregators: only newsletters
- Podcast apps: only podcasts
- Social media: only that platform
- Read-it-later: only what you manually save

The information diet includes *all of these* plus work communications, Slack messages, group chat recommendations, conference talks, GitHub activity, research papers, and more. Building the unified layer requires ingesting from every surface -- a massive engineering and partnership challenge that no startup has been willing or able to tackle.

### 6. The Artifact Lesson in Detail

Artifact's failure is the most instructive data point in this space:
- **Market too small for VC scale**: Systrom concluded the standalone news app market couldn't support a venture-backed business. This doesn't mean the *information diet* market is small -- it means the *news-only* slice is small.
- **Feature creep killed focus**: Adding Posts (social), Links (bookmarking), AI image generation diluted the core value prop. They were searching for adjacent markets because news alone wasn't enough.
- **Distribution disadvantage**: Competing against pre-installed defaults (Apple News, Google News) with a standalone app is near-impossible without a distribution moat.
- **No lock-in**: Nothing about a news reader creates switching costs. Your reading history and preferences don't compound into irreplaceable value.

The meta-lesson: the winning product in this space will not be a "better news app." It will be something that creates compounding value the more you use it -- a knowledge layer, not a reading layer.

### 7. The Business Model Trap

- **Ad-supported**: Misaligns incentives (optimize for engagement, not importance). Requires massive scale. Competes with Google/Meta for ad dollars.
- **Subscription**: Hard to justify $10+/month for "a better feed" when alternatives are free. Requires demonstrating clear, tangible value.
- **Freemium**: The free tier must be good enough to attract users but limited enough to convert. Hard to calibrate.
- **B2B/Enterprise**: Higher willingness to pay but different product requirements (competitive intelligence, team features, compliance).

The Browser charges ~$5/month for 5 curated articles/day. Readwise charges $9.99/month for a reading app. Feedly's AI features start at ~$1,600/month for enterprise. The consumer willingness-to-pay for curation is somewhere in the $5-15/month range -- enough for a business, but not a venture-scale rocketship unless retention is exceptional.

---

## Business Opportunities

### The Core Insight

The whitespace is not "better news" -- it's **"your personal editor."** A product that:
1. Ingests from everywhere you consume information
2. Learns what you actually need to know (not just what you click on)
3. Synthesizes a daily/weekly briefing ranked by *importance to you*
4. Creates compounding value through a personal knowledge graph

### Model 1: The Personal Editor ($10-20/month)

**The pitch:** "One place where your entire information diet is curated, ranked, and synthesized. Not another app to check -- the *only* app to check."

**How it works:**
- Connect your sources: email (newsletters auto-detected), RSS, Twitter, Reddit, YouTube, podcasts, Slack, HN
- AI learns your professional context, expertise level, and information goals through onboarding + ongoing behavior
- Daily briefing: "Here are the 5-10 things that matter to you today, across all your sources"
- Progressive depth: headline -> summary -> analysis -> original source
- Weekly synthesis: "Here's how the landscape shifted this week in your areas"
- Cross-source deduplication: if 4 newsletters and 3 Twitter threads are about the same thing, you see it once with a synthesis

**Why people would pay $10-20/month:**
- Time savings: replace 45 minutes of scattered checking with 10 minutes of focused reading
- Reduced anxiety: "I'm not missing anything important" -- information FOMO solved
- Better decision-making: see the important signal, not the noisy firehose
- Knowledge compounding: the system builds a map of what you know and what you've read

**Key differentiator from everything else:** It's not a reading app (Readwise), not a news app (Apple News), not a feed reader (Feedly). It's an *editor* -- it makes judgment calls about what matters *to you specifically*, across *every* source.

**Wedge market:** Start with a specific professional cohort where the cost of being uninformed is high: VCs, startup founders, tech leads, policy analysts. These people already cobble together DIY solutions. Convert them first, expand from there.

### Model 2: Team Intelligence Layer ($15-50/user/month)

**The pitch:** "Your team's shared information radar. Everyone sees the same important developments, nobody wastes time sharing links that others have already seen."

**How it works:**
- Shared team topics + individual customization
- AI-curated team digest: "Here's what matters to [Company] this week"
- Collaborative annotation: "I think this matters because..."
- Competitive intelligence built in: track competitors, market signals, regulatory changes
- Replaces the "did you see this article?" Slack channel

**Why now:** Remote teams have worse information osmosis than co-located ones. The "watercooler link sharing" is broken. Enterprise competitive intelligence tools (Crayon, AlphaSense, Contify) charge $10K+/year and are overly complex. Mid-market teams ($50-500/month) are underserved.

### Model 3: The Knowledge Compound (Premium Tier, $20-30/month)

**The pitch:** Not just what matters today, but how today connects to everything you've read before. Your personal knowledge graph, built automatically from your information diet.

**Premium features:**
- **Knowledge graph:** Every article, thread, and podcast you consume is mapped into entities, relationships, and themes. "You've been tracking 47 entities related to AI regulation across 200+ pieces over 6 months."
- **Memory:** "You read about this company 3 months ago when they raised their Series A. Here's what changed." The system remembers what you've already consumed and contextualizes new information.
- **Trend detection:** "This topic appeared in 3 of your sources this week for the first time. Emerging signal?"
- **Export to PKM:** Sync curated insights to Obsidian, Notion, Logseq. The information diet feeds your knowledge system.
- **Briefing generation:** "Prepare me a briefing on [topic] using everything I've consumed about it in the last 6 months."

This is where the compounding value creates lock-in. Your knowledge graph becomes more valuable over time, making switching costs real.

### Model 4: Infrastructure / API Play

**The pitch:** Don't build the consumer product. Build the curation engine and let others integrate it.

**Customers:**
- Newsletter platforms (Beehiiv, ConvertKit, Substack): AI curation layer for their writers
- Enterprise tools (Slack, Notion, Confluence): "Important external developments" feed
- AI assistants (ChatGPT, Claude, Perplexity): structured curation API for ongoing monitoring
- Media companies: personalized edition generation

**Revenue:** API pricing per call/user/month. The picks-and-shovels play.

### Addressable Market Signals

- Newsletter industry: TLDR ($5-7M/yr bootstrapped), Morning Brew ($75M exit), Superhuman AI (7-figure/month within months of launch). Proves people want curated information.
- Read-it-later: Readwise growing steadily at $9.99/month. Pocket acquired by Mozilla. Instapaper still alive.
- Competitive intelligence: Crayon, AlphaSense, Contify -- well-funded at enterprise tier. Mid-market gap.
- AI agent market: $5.25B (2024) -> projected $52.62B (2030).
- The Browser: 150K subscribers paying ~$5/month for human-curated articles = proves subscription curation works.
- DIY automation: growing n8n/Make/Zapier community building custom curation = product gap signal.

---

## Breakthrough Ideas

### 1. The "Information Metabolic Rate" Model

Treat information consumption like nutrition. Just as a nutritionist doesn't just tell you "eat healthy" but understands your specific metabolic needs, an information diet curator would:

- **Audit your current intake:** "You spend 3 hours/day on information consumption. 40% is Twitter, 25% is newsletters, 15% is news apps, 20% is podcasts. Of that, roughly 30% is redundant (same story across sources), 25% is entertainment disguised as information, and only 45% is genuinely useful signal."
- **Set an information budget:** "For your role as a tech lead, you need ~30 minutes/day of curated signal across: industry trends, technical developments, team-relevant news, and professional development."
- **Optimize the ratio:** Replace scatter with signal. Not "read more" but "read less, better."

The key insight: most people's information problem isn't *access* -- it's *excess*. The product that helps you consume *less* while knowing *more* is counterintuitive but valuable. Charge for saving time, not for adding content.

### 2. The "Why This Matters to You" Layer

Current aggregators show you *what* happened. The 10x product explains *why it matters to you specifically*.

"OpenAI released a new model" is news. "OpenAI released a new model. This matters to you because: (1) your company uses their API and this model is 40% cheaper, which affects your Q2 infrastructure budget; (2) it supports the new function-calling pattern you were evaluating for the agent project; (3) three of the newsletters you follow are covering it from different angles -- here's a synthesis."

This requires knowing:
- Your professional context (role, company, projects)
- Your information history (what you've read before)
- Your current priorities (what you're working on)
- The relationships between entities in your world

No product does this today. AI models are capable of it -- the gap is the data integration and the interaction design.

### 3. Cross-Source Triangulation

The most reliable signal that something matters is when it appears independently across multiple, unrelated sources. A development mentioned in:
- A niche technical blog
- A HN discussion thread
- Your company's Slack #industry channel
- A newsletter you subscribe to
- A podcast you listen to

...is almost certainly important. Current tools treat each source independently. The breakthrough product would detect cross-source resonance and surface items that are being independently discussed across your information landscape, weighted by source diversity (5 Twitter accounts saying the same thing is less signal than 1 blog + 1 newsletter + 1 podcast + 1 Slack message).

### 4. The Anti-Feed: Structured Briefing, Not Infinite Scroll

Every existing product defaults to a feed -- an infinite scrollable list. Feeds are engagement-optimized by design. The breakthrough interaction model is the **structured briefing**:

- **Morning brief** (2 minutes): "3 things you need to know today." Numbers, not feeds. Finite, not infinite.
- **Deep dive queue** (for when you have time): "5 pieces worth reading in full this week, ranked by relevance to your current projects."
- **Synthesis report** (weekly): "Here's how the landscape shifted in your areas this week. 2 emerging trends, 1 thing that resolved, 1 thing that changed direction."
- **Conversational exploration:** "Tell me more about item 2" -> progressive depth, not a new feed.

The anti-feed is deliberately *finite*. It respects your time budget. It says "you're done" when you're done, instead of pulling you into infinite scroll.

### 5. Taste Learning, Not Engagement Learning

Current recommendation systems learn from clicks, reads, and dwell time. These are *engagement* signals, not *value* signals. You might click on a celebrity gossip article but it didn't make you smarter.

A taste-learning system would use:
- **Explicit value ratings:** "Was this worth your time?" (not "did you like it?" -- those are different questions)
- **Save/export behavior:** Things you save to Obsidian, highlight, or share with colleagues are higher-value signals than things you merely read
- **Professional outcomes:** Did reading about X lead you to make a decision, start a project, change a plan? (Hard to measure but the most meaningful signal)
- **Stated goals:** "I need to stay current on AI regulation for my board" is more informative than 1,000 click signals
- **Negative signals:** "Stop showing me crypto content" should be a first-class feature, not buried in settings
- **Social calibration:** "When [trusted colleague] shares something, weight it 5x"

Over time, the system learns not what you *click* on but what you *value* -- and these are very different things.

### 6. The "Knowledge Debt" Concept

Just as engineers track technical debt, the product could track *knowledge debt*: topics where you're falling behind relative to your needs.

"You haven't read anything about EU AI regulation in 3 weeks. Given your role, this is accumulating knowledge debt. Here's a 5-minute catchup synthesis."

"Your competitor shipped a major product update 4 days ago. You haven't seen any coverage of it yet. Here's what changed."

This inverts the model from "here's what's new" to "here's what you're missing." It creates urgency and demonstrates value -- the product is protecting you from blind spots.

### 7. The Compounding Personal Knowledge Graph

The most defensible version of this product builds a **personal knowledge graph** from your information consumption over time:

- **Entities:** People, companies, technologies, concepts you track
- **Relationships:** How entities relate to each other and to your work
- **Timeline:** How your understanding has evolved ("You first encountered this company in March 2025. Here's everything you've consumed about them, in order.")
- **Gaps:** Entities connected to things you care about that you haven't explored yet
- **Predictions:** Based on your consumption patterns and the trajectory of entities you track, "Here's what might matter next"

This creates genuine lock-in because the knowledge graph becomes more valuable over months and years. Your information history has compounding returns. Switching to a new product means losing your accumulated context.

The integration play: export to Obsidian/Notion as a structured knowledge base. The curation product feeds your PKM system, which feeds your thinking, which feeds back into what you need to know. A virtuous cycle.

### 8. Credibility-Weighted Curation

Integrate [[trust-weighted-filtering]] into the curation layer. Not all sources are equal, and importance should be weighted by source credibility in the relevant domain:

- A core maintainer's blog post about a framework change outranks a content-farm tutorial
- An SEC filing outranks a blog speculating about the same company
- A peer-reviewed paper outranks a Twitter thread on the same topic

Combined with cross-source triangulation: "This finding was reported by 3 high-credibility sources independently" is a much stronger signal than "this went viral on Twitter."

---

## Sources

### Artifact & News Aggregator Market
- [Artifact Shutdown Announcement — Techmeme](https://www.techmeme.com/240113/p1) — Kevin Systrom: "the market opportunity isn't big enough to warrant continued investment"
- [Artifact Launch as "TikTok for Text" — TechCrunch](https://techcrunch.com/2023/01/31/instagrams-co-founders-launch-artifact-a-tiktok-for-text/)
- [Why Artifact Failed — Failory](https://newsletter.failory.com/p/why-artifact-failed) — 444K downloads, 44% US, loss of focus
- [Yahoo Acquires Artifact Technology (April 2024)](https://techcrunch.com/2024/04/02/yahoo-acquires-artifact/)
- [Nuzzel acquired by Scroll, then Twitter (2021)](https://nuzzel.com/about)

### News Aggregators
- [Apple News — App Store](https://apps.apple.com/us/app/apple-news/id1066498020) — Apple News+ at $12.99/month, 400+ publications
- [SmartNews](https://www.smartnews.com/) — 50M+ downloads, 4,500+ publishers, political spectrum slider
- [Flipboard — About](https://about.flipboard.com/about-us/) — Fediverse integration (Threads, Mastodon, Bluesky)
- [Ground News](https://ground.news/) — 50,000+ sources, media bias ratings
- [Particle News](https://particle.news/) — AI-powered summaries, multi-source aggregation

### RSS & Reading Tools
- [Feedly](https://feedly.com/) — Enterprise intelligence platform, Leo AI, ~$1,600/month enterprise tier
- [Inoreader](https://www.inoreader.com/) — Pro at $7.50/month, 2,500 feeds, AI summaries, social listening
- [Reeder](https://reeder.app/) — 15 years, unified timeline (RSS + video + podcasts + social)
- [Readwise + Reader](https://readwise.io/) — $9.99/month, RSS + newsletters + PDFs + YouTube + Twitter threads
- [Omnivore](https://github.com/omnivore-app/omnivore) — Open-source read-it-later, cloud version deprecated Nov 2024

### Newsletter Ecosystem
- [Meco](https://www.meco.app/) — Newsletter reader, inbox decluttering
- [Stoop](https://stoopinbox.com/) — Newsletter app, largely dormant
- [Mailbrew](https://www.mailbrew.com/) — Custom digests from RSS, Reddit, HN, YouTube, Twitter, stocks
- [TLDR](https://tldr.tech/) — 1.6M subscribers flagship, 6M+ total, 12 verticals, ad-supported
- [The Browser](https://www.thebrowser.com/) — 150K+ subscribers, human-curated, 5 articles/day

### AI Search & Curation
- [Kagi](https://www.kagi.com/) — Premium search, Kagi News, Small Web, Summarizer
- [Perplexity](https://www.perplexity.ai/) — AI search with Discover feature for curated daily stories
- [Techmeme](https://www.techmeme.com/) — Human + algorithmic tech news curation since 2005
- [daily.dev](https://daily.dev/) — 1M+ developers, personalized dev news feed, free

### Productivity & Email
- [Superhuman](https://www.superhuman.com/) — AI email, inbox prioritization, cross-tool integration
- [Shortwave](https://www.shortwave.com/) — AI email, smart filtering, newsletter bundling

### Market Data & Analysis
- Topic-level curation landscape — see [[topic-level-curation]]
- Trust-weighted filtering — see [[trust-weighted-filtering]]
- [PNAS Nexus (2025) — Engagement vs. User Satisfaction](https://pmc.ncbi.nlm.nih.gov/articles/PMC11894805/)
- [AI Agent Market: $5.25B (2024) -> $52.62B projected (2030)](https://aifundingtracker.com/top-ai-agent-startups/)
- [Morning Brew Growth — $70M+ revenue](https://www.marketergems.com/p/morning-brew-newsletter-growth-strategy-case-study)

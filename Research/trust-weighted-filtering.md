---
tags:
  - research
  - social-media-futures
  - curation
date: 2026-03-11
---

# Trust-Weighted Filtering

The core idea: rank content not by engagement metrics (likes, shares, time-on-page) but by the credibility and domain-specific reputation of the source. A climate scientist's thread on CO2 data ranks higher than a random influencer's hot take. A veteran security researcher's vulnerability disclosure outranks a blogspam rehash.

## Landscape

### Fact-Checking & Source Reliability Platforms

**NewsGuard** — Human journalists rate news sources on a 0-100 trust scale across 9 criteria (separates news from opinion, avoids deceptive headlines, discloses ownership, etc.). $21.5M raised, ~50 employees. Sells to browsers, search engines, ad-tech platforms, and governments. Found that leading generative AI tools repeat false news claims 35% of the time. Limitation: rates *publications*, not individual authors or claims. Manual process doesn't scale to the long tail.

**Ground News** — Aggregates stories from 50,000+ sources, categorizes by political bias (left/center/right), factuality, and ownership structure. Processes ~30,000 stories daily. Consumer subscription model. Useful for bias awareness but doesn't score individual content credibility — it's a *lens*, not a *filter*.

**ClaimBuster / Full Fact / Google Fact Check Tools** — Automated and semi-automated claim detection and verification. Google's Fact Check Markup allows publishers to tag fact-checks with ClaimReview schema. These are primarily tools for fact-checkers, not consumer-facing feed infrastructure.

### Bridging & Consensus Algorithms

**X Community Notes** — The most deployed trust-weighted system at scale. Uses a bridging-based matrix factorization algorithm: notes are shown only if rated helpful by people who *typically disagree* with each other. The algorithm automatically identifies an ideological spectrum and extracts a "helpfulness score" as the residual after accounting for partisan lean. Requires at least 10 ratings from users with different viewpoints (as of March 2025). Strength: resistant to partisan pile-ons. Weakness: only adds *corrections* to existing content; doesn't rank or filter the feed itself. Recent research flags sustainability concerns — contributor fatigue and adversarial gaming.

**Polis** — Open-source deliberation platform (Computational Democracy Project). Participants submit and rate short statements; PCA + K-means clustering identifies opinion groups and surfaces *consensus statements* that bridge divides. Used by Taiwan's government (vTaiwan) for policymaking on Uber regulation, AI governance. Proves that bridging algorithms can find common ground at scale, but it's a *deliberation tool*, not a content feed.

### Decentralized & Composable Moderation

**Bluesky / AT Protocol** — Pioneering "stackable moderation": open labeling system where anyone can run independent moderation/labeling services. Labels can be informational ("Satire"), topical ("Politics"), curational ("Dislike"), or moderational ("Rude"). Users subscribe to labeling services like choosing spam filters. Open-sourced Ozone (collaborative moderation tool). This is the closest existing architecture to a trust-weighted feed — but labels are *categorical*, not *credibility-scored*. No one has built a credibility labeler yet.

**Farcaster** — Hybrid onchain-offchain social protocol on OP Mainnet. User identity tied to Ethereum addresses via smart contracts. On-chain reputation systems record positive interactions across all Farcaster apps. Peaked at 80K MAU, dropped to under 20K by late 2025. Demonstrates the challenge: crypto-native reputation works but hasn't achieved mainstream adoption.

**Lens Protocol** — Profile NFTs (ERC-721), portable social graphs. Lens V3 moving to custom L2 with zkSync. More radical ownership model but same adoption challenge as Farcaster.

### Reputation Protocols & Algorithms

**OpenRank** — Decentralized ranking/reputation protocol using EigenTrust and matrix factorization on social graph data (Farcaster, Lens, onchain transactions). Compute nodes execute reputation algorithms; verifier nodes validate results with cryptographic proofs secured through EigenLayer restaking. Closest thing to a "trust API" in Web3. Core idea: a person's reputation is defined recursively by the people who trust them, weighted by *those people's* reputations (PageRank for trust).

**EigenTrust** (academic, 2003) — Foundation algorithm. Global trust value = weighted sum of local trust values, where weights are the assigning peers' own reputations. Converges via power iteration on a normalized trust matrix. Proven to reduce inauthentic content in P2P networks. Directly inspired by PageRank.

**Galxe** — Credential infrastructure for Web3. On-chain reputation tracking and rewards for authentic engagement. Used in Gitcoin Passport (drastically reduced bot activity in grants rounds).

**Nomis** — Onchain identity protocol; users leverage onchain reputation for personalized Web3 experiences.

### Academic & Citation Systems

**h-index / Google Scholar** — Author-level metric (h papers each cited at least h times). Now *anti-correlated* with reputation among top scientists — Goodhart's Law in action. Correlation with scientific awards dropped significantly post-2010 due to hyperauthorship (100+ coauthor papers), gaming via coercive citation practices, and Google Scholar's vulnerability to fake papers. Field-dependent and doesn't capture *domain-specific* expertise. A cautionary tale for any reputation metric.

**Stack Overflow** — Reputation earned through peer voting on answers. Research shows reputation score is *generalized* — it doesn't capture domain-specific expertise. ProficiencyRank (PageRank variant) was proposed to fix this. Lesson: reputation must be *topic-scoped* to be meaningful.

**Wikipedia Editor Rankings** — Earned through edit history, community processes (RfA), and dispute resolution track record. Resistant to gaming due to transparency and peer oversight but extremely labor-intensive. Not portable outside Wikipedia.

### Subscription/Expert-Driven Models

**Substack** — Reader-funded model aligns incentives differently. Because revenue comes from subscriptions (not ads), there's no incentive for engagement-bait. Notes algorithm optimizes for subscription conversion, not clicks. Effectively a trust signal: readers vote with their wallets. But it's an *economic filter*, not a *credibility score* — popular writers aren't necessarily credible ones.

### Prediction Markets as Track-Record Systems

**Metaculus** — Forecasting platform that weights predictions by track record. Aggregate predictions are calibrated and weighted by recency and predictors' historical accuracy. 79% accuracy, outperforming Polymarket (73%) and traditional polls. Demonstrates that *track record scoring works* for quantifiable predictions. The credibility signal: "this person has been right before, with receipts."

**Polymarket** — Real-money prediction market. 73% accuracy overall. Outperforms polls by 8 percentage points in political forecasting. But accountability concerns: speculative infrastructure can operate independently of ethical constraints.

## What's Broken

### The Engagement Trap

Social media companies operate on advertising-based revenue. Engagement metrics (clicks, shares, dwell time) directly maximize ad inventory and time-on-platform. This creates a structural misalignment: **what keeps users scrolling is not what users say they want to see.**

Research (PNAS Nexus, 2025) showed that Twitter's engagement-based algorithm amplifies emotionally charged, out-group hostile content that users explicitly said made them feel *worse*. A stated-preference timeline reduced anger, sadness, and anxiety — but stated preferences are "rarely observed and harder to optimize than engagement." The business model makes engagement the path of least resistance.

The trade-off is real but narrower than expected: stated preferences reduced exposure to *all* out-group content (including valuable cross-cutting exposure), not just hostile content. The challenge isn't just "engagement bad, trust good" — it's designing metrics that promote *quality* cross-cutting exposure.

### Fact-Checking Doesn't Scale

Human fact-checking requires expert judgment, context sensitivity, and editorial discretion that automated systems can't replicate. Reuters Institute research concludes automated fact-checking will require "human supervision for the foreseeable future." LLM-based fact-checking achieves 90% accuracy identifying false headlines, but this *doesn't translate* to improved user discernment — human-generated fact-checks do. The bottleneck isn't detection; it's *legitimacy and persuasion*.

Community Notes partially solved this with bridging, but it only *annotates* — it doesn't *rank*. And it faces contributor fatigue and adversarial strategies.

### Reputation Systems Are Fragile

**Sybil attacks** — Creating fake identities to inflate reputation. Sybil prevention can't prevent attacks entirely and may be vulnerable to widespread small-scale attacks. IP and CAPTCHA restrictions are easily circumvented (a human can solve thousands of CAPTCHAs per day).

**Cold start** — New users have no reputation. How do you bootstrap? Assign a default (exploitable) or require existing credentials (exclusionary)?

**Goodhart's Law** — Once a metric becomes a target, it ceases to be a good metric. The h-index story is instructive: correlation with scientific awards *collapsed* after the metric became widely used and gamed.

**Domain specificity** — Stack Overflow's generalized reputation score doesn't capture expertise in specific domains. A TypeScript guru's reputation doesn't transfer to their opinions on database architecture. Most reputation systems flatten expertise into a single number.

**Political subjectivity** — Who decides what's "credible"? Any centralized credibility scoring system becomes a target for political capture. Even Community Notes' bridging algorithm has been critiqued for assuming a single ideological spectrum.

**Portability** — Reputation earned on one platform (Wikipedia edits, Stack Overflow answers) doesn't transfer elsewhere. Every platform is a walled garden of trust.

### Regulatory Tailwinds (But Slow)

The EU Digital Services Act requires annual risk assessments, algorithm audits, and researcher data access for very large platforms (Article 40.4, effective October 2025). First harmonized transparency reports due early 2026. First fine issued to X in December 2025 for non-compliance. 14 investigations opened. This creates *demand* for alternative ranking approaches but doesn't prescribe solutions. Platforms are responding with minimal compliance, not fundamental redesigns.

## Business Opportunities

### 1. Trust Layer API (Infrastructure Play)

**The pitch:** A credibility scoring API that any platform, app, or AI agent can call. Takes a piece of content or a source identifier and returns domain-specific credibility signals. Think "Stripe for trust."

**Revenue model:** Per-API-call pricing for platforms, media companies, ad-tech. Enterprise tiers for newsrooms and AI companies that need to ground their models in reliable sources.

**Moat:** The scoring model itself (proprietary blend of signals), the data flywheel (more usage = better calibration), and network effects (more platforms contributing trust signals = richer graph).

**Precedent:** OpenRank is building this in Web3 with EigenTrust. No one has built the equivalent for the mainstream web. NewsGuard's licensing model is the closest, but it's manually curated and scores publications, not authors or claims.

**Key challenge:** Who are the first customers? AI companies building RAG pipelines that need source reliability scores. This is the wedge — LLMs citing unreliable sources is an acute, funded problem.

### 2. Credibility Labeler for Bluesky/AT Protocol

**The pitch:** Build the first domain-specific credibility labeling service on Bluesky's open labeling infrastructure. Users subscribe to get credibility-scored feeds (e.g., "Science Feed — ranked by author credentials and track record").

**Revenue model:** Freemium — basic labels free, premium feeds with detailed credibility breakdowns via subscription. Or B2B: license to other apps built on AT Protocol.

**Why now:** Bluesky's architecture was *designed* for this but no one has built it. The labeling API is ready. First-mover advantage in a growing ecosystem.

**Key challenge:** Building the credibility model. Where do the scores come from?

### 3. Domain-Expert Verification Network (B2B + Consumer)

**The pitch:** A "verified expert" network where domain-specific credentials are checked and linked to social identities. Not a full social network — a portable credential that plugs into existing platforms. A professor verified on climate science gets a badge that surfaces in their posts across Bluesky, Substack, LinkedIn.

**Revenue model:** Experts pay for verification (like Twitter Blue, but for credentials). Platforms pay for API access to verification data. Conferences, journals, media outlets pay for speaker/source vetting.

**Precedent:** Academic ORCID for researchers, but broader and consumer-facing. Prolific already does domain expert verification for AI training data.

**Key challenge:** Getting experts to opt in. The value proposition must be immediate and tangible — "your posts will rank higher on platforms that use our API."

### 4. Track Record Accountability Layer

**The pitch:** Apply Metaculus-style track record scoring to pundits, analysts, and commentators. Automatically extract predictions from public statements (AI-assisted), track outcomes, publish calibration scores. A "batting average for takes."

**Revenue model:** Media companies pay for analyst credibility dashboards. Consumer app with free tier (look up any public figure's track record). Premium for custom watchlists and alerts.

**Why now:** LLMs can extract predictions from natural language at scale. Prediction market infrastructure has matured. Public appetite for accountability is high.

**Key challenge:** Defining what counts as a "prediction" and what counts as "right." Subjective claims resist binary resolution. The system must handle degrees of correctness and hedged language.

### 5. Trust-Weighted Ad Marketplace

**The pitch:** An ad network that charges premium CPMs for placement alongside high-credibility content. Advertisers already pay more for "brand safe" environments (DoubleVerify, IAS). This extends the concept from "not harmful" to "actually credible."

**Revenue model:** Take rate on premium ad placements. Credibility scoring as a value-add layer on top of existing ad-tech.

**Why now:** Brand safety is a $4B+ market. Extending to "brand *credibility*" is a natural evolution, especially as AI-generated slop floods the web.

**Key challenge:** Chicken-and-egg. Need publisher adoption to attract advertisers and vice versa.

## Breakthrough Ideas

### 1. Recursive Trust Graphs (EigenTrust for Social Media)

Apply EigenTrust to mainstream social feeds: your trust score on topic X is the weighted sum of trust from people who trust you on topic X, weighted by *their* trust scores. Not a single reputation number — a *vector* of domain-specific trust scores that propagate through the social graph.

Key insight: you don't need a central authority to score credibility. The graph scores itself. If experts in your field trust you, that signal propagates. If only engagement-farmers trust you, that signal *doesn't* propagate (because engagement-farmers have low trust scores from experts).

This is what OpenRank is building onchain. The 10x opportunity is bringing it offchain to the mainstream web with better UX and no crypto prerequisites.

### 2. Prediction-Market-Style Accountability Feeds

Every claim in a feed gets a confidence score. Users can "bet" on whether claims will prove true (reputation stakes, not money). Over time, users build calibration scores — visible to everyone. A feed ranked by author calibration would surface people who are *reliably right*, not just popular.

Make it concrete: a "Track Record" tab on every profile showing past claims, outcomes, and calibration curve. The social incentive shifts from "be loud" to "be accurate."

Combine with AI claim extraction: LLMs parse posts for implicit predictions ("inflation will hit 5% by Q3"), track outcomes automatically, and update calibration scores. This makes accountability *passive* — you don't have to opt in; your public claims speak for themselves.

### 3. Peer Validation Networks (Expertise Endorsements)

Like LinkedIn endorsements, but with actual signal. Domain-specific endorsements from other verified experts, weighted by the endorser's own standing in that domain. A climate scientist's endorsement of another climate scientist carries more weight than a random follower's.

The key difference from existing systems: endorsements are *domain-scoped* and *weighted by endorser credibility*. It's not "17 people endorsed you for Machine Learning" — it's "Yann LeCun's team endorsed you for ML, and their endorsement carries weight because of their own track record."

Pair with negative signals: if someone consistently promotes debunked claims, domain experts can flag this, and the flag carries weight proportional to the flagger's own domain reputation.

### 4. Credibility-Aware AI Agents

As AI agents increasingly curate information for users (Perplexity, ChatGPT browsing, Apple Intelligence summarization), they need source reliability signals. The 10x play: build the trust layer that AI agents *call* when deciding which sources to cite. Every RAG pipeline, every AI search engine, every summarization tool becomes a customer.

This is where the infrastructure play meets the AI wave. If you are the API that AI agents use to assess "should I trust this source on this topic?", you become invisible infrastructure — like DNS for trust.

Google's E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) framework already signals demand for this. 96% of AI Overview content comes from sources that score high on authority signals. But E-E-A-T is Google's proprietary black box. An open, auditable trust API would be a genuine alternative.

### 5. Community-Curated Trust Calibration

Instead of top-down credibility scoring, let communities define and calibrate their own trust models. A subreddit for oncologists defines what "credible" means differently than a subreddit for woodworking. Each community trains its own trust model on domain-appropriate signals (peer-reviewed citations vs. completed project photos).

Bluesky's labeling architecture makes this technically possible today. The missing piece is tooling that lets non-technical community leaders configure trust models and see how they change their feed.

The composability is the breakthrough: you could stack trust models. "Show me posts that score highly on *both* the oncology community's trust model *and* the patient advocacy community's trust model" — bridging expert and lived-experience perspectives.

### 6. The "Slow Feed"

A deliberately slower feed that only surfaces content after a credibility assessment delay. New claims get a 24-hour hold while they're cross-referenced, annotated by domain experts, and scored. What surfaces has already been vetted.

This inverts the speed competition of social media. The value proposition is *not* "see it first" but "see it *right*." Premium positioning for people who are tired of being wrong quickly.

Combine with the prediction accountability layer: content that was flagged as likely false during the delay period gets tagged with the outcome when resolved, building a track record for the scoring system itself.

## Links

- [[information-diet-curation]] — trust-weighting as one dimension of a unified curation layer
- [[topic-level-curation]] — complements topic curation with source credibility scoring

## Sources

### Fact-Checking & Source Reliability
- [NewsGuard](https://www.newsguardtech.com/) — News reliability ratings platform
- [Ground News Review 2026](https://ratingfacts.com/blogs/ground-news-review-take-a-look-at-this-bias-busting-news-app) — Bias-aware news aggregator
- [Reuters Institute: Promise and Limits of Automated Fact-Checking](https://reutersinstitute.politics.ox.ac.uk/our-research/understanding-promise-and-limits-automated-fact-checking)
- [PNAS: Fact-checking with LLMs](https://www.pnas.org/doi/10.1073/pnas.2322823121)

### Engagement vs. Trust Research
- [PNAS Nexus: Engagement, User Satisfaction, and Divisive Content](https://pmc.ncbi.nlm.nih.gov/articles/PMC11894805/)
- [ScienceDirect: How Social Media Algorithms Fuel Misinformation](https://www.sciencedirect.com/science/article/pii/S0047272726000253)
- [Engagement-Based Ranking Algorithms](https://www.mxmoritz.com/article/engagement-based-ranking-algorithms)

### Bridging & Consensus
- [Understanding Community Notes and Bridging-Based Ranking](https://jonathanwarden.com/understanding-community-notes/)
- [Asterisk: The Making of Community Notes](https://asteriskmag.com/issues/08/the-making-of-community-notes)
- [Consensus Stability of Community Notes on X](https://arxiv.org/html/2601.14002)
- [Polis — Computational Democracy Project](https://compdemocracy.org/polis/)
- [Bridging Systems Working Paper](https://bridging.systems/files/bridging-systems-working-paper.pdf)

### Decentralized Social & Reputation
- [Bluesky Stackable Moderation](https://bsky.social/about/blog/03-12-2024-stackable-moderation)
- [OpenRank Protocol](https://docs.openrank.com/)
- [EigenTrust Algorithm (Stanford)](https://nlp.stanford.edu/pubs/eigentrust.pdf)
- [Farcaster vs Lens: Web3 Social Graph](https://blockeden.xyz/blog/2026/01/13/farcaster-vs-lens-socialfi-web3-social-graph/)
- [On-Chain Reputation in Farcaster and Lens](https://farcasternews.com/2025/10/22/how-on-chain-reputation-systems-are-transforming-community-growth-in-farcaster-and-lens-protocols/)
- [Web3 Decentralized Reputation Systems](https://tde.fi/founder-resource/blogs/web3-strategy/why-every-web3-founder-should-care-about-decentralized-reputation-systems-in-2025-2/)

### Academic Reputation & Limitations
- [h-index No Longer Effective Correlate of Reputation](https://pmc.ncbi.nlm.nih.gov/articles/PMC8238192/)
- [How Good is the h-index?](https://arxiv.org/html/2503.13456)
- [Stack Overflow Reputation Analysis](https://www.researchgate.net/publication/262366731_Analysis_of_the_reputation_system_and_user_contributions_on_a_question_answering_website_StackOverflow)

### Prediction Markets & Track Records
- [Polymarket Accuracy Analysis](https://www.fensory.com/intelligence/predict/polymarket-accuracy-analysis-track-record-2026)
- [Metaculus Forecasting Comparison](https://manifund.org/projects/comparing-forecasting-platform-accuracy)

### Regulation & Transparency
- [EU Digital Services Act](https://digital-strategy.ec.europa.eu/en/policies/digital-services-act)
- [DSA Enforcement Phase](https://www.medialaws.eu/e120-million-later-the-dsa-enters-the-enforcement-phase/)

### Sybil Attacks & Reputation Fragility
- [Sybil Attack (Wikipedia)](https://en.wikipedia.org/wiki/Sybil_attack)
- [EigenTrust for Reputation Management in P2P Networks](https://dl.acm.org/doi/10.1145/775152.775242)

### Content Curation Models
- [Substack Notes Algorithm](https://pubstacksuccess.substack.com/p/the-notes-algorithm-explained-by)
- [Content Marketing Institute: Audience Trust Index](https://contentmarketinginstitute.com/measurement-optimization/audience-trust-index)

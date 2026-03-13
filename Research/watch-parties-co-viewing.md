---
tags:
  - research
  - social-media-futures
  - shared-live-experience
---

# Watch Parties & Co-Viewing

Research into remote synchronized content consumption with a social layer -- groups of people watching together in real-time while physically apart.

---

## Landscape

### Dedicated Watch Party Apps / Extensions

**Teleparty** (formerly Netflix Party, 2020)
- Browser extension (Chrome, Edge, Safari) that synchronizes playback across Netflix, YouTube, Disney+, HBO Max, Hulu, Amazon Prime Video. Text chat sidebar with emoji reactions and themed avatars.
- Exploded during COVID lockdowns. Reported 10M+ users by late 2020, peaked around 2021. Chrome Web Store showed 10M+ installs at peak. Usage dropped significantly post-pandemic as in-person socializing resumed.
- Freemium model: free basic version, "Teleparty Premium" adds video chat, custom emojis, and additional features. No known venture funding -- bootstrapped by a small team led by creators who originally built it as a side project.
- Core limitation: browser-only (no mobile, no smart TV, no living room). Text chat is the entire social layer -- no voice, no video on the free tier.

**Rave** (2016)
- Mobile-first app (iOS, Android, macOS, Windows) for synchronized streaming from Netflix, YouTube, Amazon Prime, Disney+, HBO Max. Also supports music via Spotify and Apple Music.
- Differentiator: works natively on phones, not just browsers. Supports voice chat during viewing. Also has RaveDJ for creating mashups.
- User base unclear but has maintained consistent App Store presence. Free with ads. One of the few co-viewing apps that survived post-pandemic without collapsing.
- Weakness: latency issues on mobile, sync drift over long sessions, audio mixing problems when voice chat overlaps with content audio.

**Scener** (2018, Seattle)
- "Virtual movie theater" concept. Browser extension with synchronized playback plus webcam/audio rooms so you can see your friends' reactions.
- Raised $2.1M seed round in 2020 (investors included Vulcan Capital). Positioned as the premium co-viewing experience with theatrical presentation.
- Added public watch parties and creator-hosted screenings. Free with premium tier and ad support. Uses Agora SDK for real-time communication.
- Pivoted multiple times. Struggled with scale beyond enthusiast users. The webcam-during-movies concept was awkward -- people don't actually want to be watched while watching.

**Kosmi** (Toronto, Canada)
- Browser-based virtual hangout platform. Synchronized streaming from Netflix, YouTube, etc., plus voice/video chat, screen sharing, retro gaming (SNES, NES, PSX emulators), card games.
- Completely free, no subscriptions. Backed by Techstars, Mozilla, Comcast, Brunnur Ventures. Featured by TechCrunch and Engadget.
- Differentiator: themed room environments (living rooms, drive-ins, cafes). Positioned as "virtual hangout space" rather than pure watch party tool.
- Small but loyal user base. Hasn't achieved mainstream scale.

**TwoSeven** (2017)
- Synchronized video watching with webcam support. Covers Netflix, Amazon, YouTube, Hulu, HBO, Disney+, and local files.
- Free tier supports YouTube and local files; paid tier ($4/month) unlocks streaming service sync.
- Niche but beloved by long-distance couples and friend groups. One of the more technically reliable sync engines.

**Hyperbeam** (2021)
- B2B/developer-focused: embeddable virtual browsers that enable co-viewing, co-browsing, and shared experiences inside any web app.
- REST API + NPM package. Pricing: free tier (10K participant-minutes/month), then $0.007/participant-minute with volume discounts.
- Powers co-viewing features for other apps rather than being a consumer product. Supports 1-10,000 concurrent participants.
- Interesting infrastructure play -- sells picks and shovels to the co-viewing gold rush.

### Big Platform Features

**Discord Watch Together / Activities** (2021)
- YouTube Watch Together launched as a Discord Activity in October 2021, replacing the shut-down Groovy and Rythm bots that had offered unauthorized music streaming.
- Part of Discord's broader "Activities" platform (games, whiteboard, etc. inside voice channels). Free for all users.
- Massive built-in distribution: Discord has 200M+ MAU. Watch Together is one of the most-used Activities. Natural fit because Discord users already sit in voice channels together.
- Limitation: YouTube only. No Netflix, no streaming services. Limited to content available on YouTube.

**Apple SharePlay** (2021, iOS 15 / macOS Monterey)
- System-level synchronized playback during FaceTime calls. Watch movies/TV, listen to music, play games together with spatial audio placing each person's voice in their tile's position.
- Works with Apple TV+, Disney+, HBO Max, Hulu, ESPN+, Paramount+, and 100+ third-party apps that integrate the SharePlay API.
- Apple Vision Pro takes it further: FaceTime participants appear as spatial "Personas" in your room. You watch a movie on a virtual theater screen while your friends' avatars sit beside you. Shared spatial audio creates genuine "being there" sensation.
- Limitation: Apple ecosystem only. Requires all participants to have compatible Apple devices AND individual subscriptions to the content service. Adoption has been modest -- most users don't know it exists.

**Amazon Prime Video Watch Party** (2020-2023, DISCONTINUED)
- Text chat alongside synchronized Prime Video playback. Required all participants to have Prime subscriptions.
- Expanded to smart TVs and streaming devices in 2022. Killed in 2023.
- Died because: low usage, maintenance cost not justified, text chat was too thin a social layer, requiring everyone to have Prime was a hard gate.

**Hulu Watch Party** (2020-2023, DISCONTINUED)
- Similar to Amazon's: synchronized playback with text chat. Launched May 2020, expanded to ad-supported tier in Sept 2020, officially launched Dec 2020.
- Also discontinued. Same fundamental problems as Amazon's version.

**Twitch Watch Parties** (2020-2022, DISCONTINUED)
- Streamers could watch Amazon Prime Video content with their Twitch audience. The streamer's webcam showed their reaction while the audience watched synced content.
- Shut down August 2022. Licensing complexity was the core issue -- content rights for "public performance" in a streaming context are legally thorny. Amazon couldn't justify the licensing burden for a feature few streamers used regularly.

**Facebook Watch Together / Watch Party** (2018-2022, DISCONTINUED)
- Group video watching in Facebook Groups and Messenger. One of the earliest big-platform attempts at co-viewing.
- Discontinued in 2022. Never gained traction. Facebook's social graph (broad, weak-tie connections) was wrong for intimate co-viewing. Nobody wants to watch a movie with 500 "friends."

**Spotify Group Session** (2020)
- Synchronized listening for Premium subscribers in the same physical location (initially), later expanded to remote. Everyone in the session can add to queue and control playback.
- Still active but rarely used. Music is more ambient than video -- synchronization matters less when you're not staring at the same screen.

### VR / Spatial Computing

**Bigscreen VR** (2016)
- Watch movies, TV, and stream your PC desktop in virtual reality environments (movie theaters, living rooms, drive-ins). Multiplayer rooms where up to 15 people sit together as avatars.
- Raised $11M+ total. One of the most popular social VR apps on Quest. Also launched Bigscreen Beyond, a lightweight PC VR headset ($999).
- The closest thing to "actually being in a theater together" that exists today. But VR adoption remains niche (~30M Quest headsets sold total vs. billions of phones).

**Meta Horizon Worlds** (2021)
- Meta's social VR platform includes watch party rooms and shared media experiences. Theater environments, sports viewing lounges.
- Struggled enormously. Horizon Worlds has been a disappointment for Meta despite billions invested. Low user counts, bad avatars, empty rooms.

**Apple Vision Pro** (2024)
- SharePlay in spatial computing: watch a 100-foot virtual screen together while FaceTime participants appear as life-like Personas beside you. Spatial audio places their voice where they "sit."
- The most technically impressive co-viewing experience ever built. Also the most expensive ($3,499) and the most limited in audience (estimated <500K units sold).

### Gaming Platforms as Co-Viewing Venues

**Fortnite** (Epic Games)
- Has hosted massive in-game events: Travis Scott concert (12.3M concurrent viewers), Ariana Grande Rift Tour, Christopher Nolan film screenings, Star Wars event premieres.
- Not a dedicated co-viewing product, but demonstrates that virtual worlds can create shared viewing moments at unprecedented scale. The social context (your avatar, your squad, the shared game world) makes the viewing feel communal in a way browser extensions never do.

**Roblox**
- Similar trajectory: concerts (Lil Nas X, Twenty One Pilots), movie promotions, branded experiences. 70M+ DAU provides massive distribution.
- Both Fortnite and Roblox prove that co-viewing works best when embedded in a world you already inhabit with people you already know, not bolted on as a separate tool.

---

## What's Broken

### 1. The Browser Extension Trap

The dominant co-viewing form factor -- a browser extension that overlays chat on a streaming service -- is fundamentally limited:

- **Platform fragility.** Extensions break every time Netflix/Disney+/etc. update their DOM structure. Teleparty developers spend enormous effort on maintenance just to keep sync working. One streaming service update can break the product for millions of users overnight.
- **No living room.** Most streaming happens on TVs (70%+ of Netflix viewing is on TVs), but browser extensions only work on laptops. This excludes the primary consumption environment. Amazon's expansion to smart TVs was an attempt to fix this but died anyway.
- **Second-class citizen.** Extensions have no relationship with the streaming service. They reverse-engineer the player, inject sync logic, and hope it works. No access to DRM-protected content metadata, no official API, no support from the platform. One policy change or technical update can kill the extension.
- **Desktop-only social layer.** Text chat in a sidebar while watching on your laptop is not how people naturally socialize. It's typing, not talking. It splits your attention between reading/writing and watching.

### 2. The Licensing Quagmire

Every big platform that built native watch parties (Amazon, Hulu, Twitch, Facebook) eventually killed them. The common thread: content licensing.

- Streaming rights are negotiated per-territory, per-platform, per-use-case. "Watch party" is an ambiguous use case -- is it private viewing (like watching at home with family) or public performance (like a screening)?
- When Twitch let streamers "watch" Prime Video content with thousands of viewers, rights holders saw it as unauthorized public exhibition. The legal exposure was significant.
- Even for private watch parties, requiring all participants to have subscriptions is a hard gate that dramatically limits adoption. Amazon and Hulu both required this. The result: your friend without a subscription can't join, which defeats the social purpose.
- Third-party extensions like Teleparty sidestep this by not hosting any content -- each user plays from their own account. But this still requires everyone to have subscriptions and is a legally gray area that streaming services tolerate rather than endorse.

### 3. The Social Layer Is Too Thin

The social layer in every major co-viewing product is some variant of text chat + emoji reactions. This is pathetically thin compared to the richness of actually watching something with people:

- **No presence.** You can't feel that someone is next to you. There's no ambient audio, no shared laughter, no whispered commentary, no comfortable silence.
- **No reactions at scale.** When something shocking happens on screen, you see a few chat messages scroll by. Compare to being in a theater where 300 people gasp simultaneously -- the collective reaction IS the experience.
- **Attention split.** Reading chat requires looking away from the content. You're either watching or chatting, never both. Audio commentary would solve this, but most products don't support it (and when they do, talking over a movie is its own problem).
- **No shared body language.** Leaning forward during tension, covering your eyes during horror, laughing together -- none of this translates through text chat.

### 4. The Synchronization Problem

Perfect sync is technically hard and socially fragile:

- **Latency variance.** Different ISPs, different CDNs, different device processing speeds. Getting everyone to the same frame at the same millisecond is nearly impossible. Even 2-3 seconds of drift breaks the shared experience (you hear your friend react to a plot twist before you see it).
- **Pause/unpause chaos.** One person pauses to go to the bathroom, and the sync breaks. Someone's stream buffers. Someone's kid walks in. Managing shared playback state across unreliable networks is a nightmare.
- **Live content is worse.** For live events (sports, concerts), even a few seconds of delay means your friend is texting about the goal before you see it. This is the "sports spoiler" problem and it has no good solution short of everyone using the exact same stream.

### 5. The Post-Pandemic Demand Collapse

COVID-19 was a massive tailwind for co-viewing. Lockdowns meant:
- People couldn't watch together in person.
- Screen time and streaming consumption spiked.
- There was genuine emotional need for shared experiences.

When lockdowns ended, co-viewing usage cratered across every product. Teleparty's user numbers fell dramatically. Amazon and Hulu killed their features. The lesson: pandemic demand was a bubble, not a baseline. The true organic demand for remote co-viewing is much smaller than 2020-2021 numbers suggested.

The exception: long-distance relationships and geographically distributed friend groups. These users have persistent, genuine need. But it's a niche, not a mass market.

### 6. Nobody Owns the Full Stack

The fundamental structural problem: no single company controls both the content and the social experience.

- Streaming services (Netflix, Disney+) own the content but have no social graph and no incentive to build one (social features don't reduce churn enough to justify engineering investment).
- Social platforms (Discord, Meta) own the social graph but don't own content (and licensing it is expensive and legally complex).
- Third-party tools (Teleparty, Rave) own neither the content nor the social graph. They're parasitic on both, vulnerable to changes from either side.

The winning co-viewing product would need to own both sides -- or find a way to make the social layer so valuable that it transcends the content layer entirely.

---

## Business Opportunities

### 1. Live Sports Co-Viewing (The Highest-Value Niche)

Sports is the only content genre where synchronous, real-time, emotionally charged group viewing is the default behavior -- and where remote viewing is genuinely worse than being together. This is the highest-value whitespace.

- **The product:** A dedicated second-screen companion for live sports that creates an audio "couch" with your friends. Not video chat (too heavy), not text chat (too thin) -- spatial audio that puts your friends' voices in the room as if they're sitting on the couch with you.
- **Key features:** Push-to-talk or always-on mic with smart ducking (voices auto-lower during play-by-play, auto-raise during breaks). Real-time reaction capture (phone detects cheering/groaning via audio). Group emotion visualization (your group's collective excitement mapped in real-time). Integrated with sportsbooks for shared betting. Clip sharing ("did you see that?!").
- **Business model:** B2B2C with sports streaming services (ESPN+, DAZN, Peacock, Amazon TNF). Per-game premium ($1-2/game for premium social features) or bundled with streaming subscriptions. Brand sponsorship of "viewing rooms" (Budweiser Couch, etc.). Data insights on real-time fan emotion sold to leagues and broadcasters.
- **Why now:** Sports streaming rights are fragmenting across platforms. Fans are increasingly watching alone at home instead of at bars or friends' houses. The social experience gap is widening, and fans will pay to close it.

### 2. Creator-Hosted Watch Parties (Twitch Model, Done Right)

Twitch Watch Parties failed due to licensing, but the concept -- a charismatic host curating and commentating while you watch -- is powerful. Commentary is content.

- **The product:** Creators host "screenings" with their audience. Instead of syncing copyrighted content (the licensing trap), the creator's commentary track is the product. Viewers play the content on their own devices; the creator's audio/video commentary syncs on top as an overlay.
- **Think of it as:** Director's commentary, but from your favorite YouTuber/streamer, delivered live with audience interaction.
- **Business model:** Creator subscription (Patreon-style access to exclusive watch parties). Tipping during screenings. Brand-sponsored screenings (a studio pays a creator to host a watch party for their new release). Affiliate revenue from streaming service sign-ups.
- **Why it works:** Separates the social value (commentary, community, personality) from the content licensing (each viewer uses their own subscription). The creator is the draw, not the content.

### 3. Enterprise / Remote Team Social Viewing

Remote and hybrid teams need shared cultural moments. "All-hands movie night" and "team watch party" are increasingly common rituals, but the tooling is terrible (screen share on Zoom with lag and bad audio).

- **The product:** A Slack/Teams-integrated tool for team watch parties. Synchronized playback of any content (YouTube, company training videos, recorded all-hands, even streaming services via individual accounts). Integrated spatial audio chat. Reaction and engagement analytics for team leads.
- **Business model:** SaaS, per-seat pricing ($3-5/seat/month). Sells to People/Culture teams, L&D departments, and remote-first companies. Enterprise licensing for large orgs.
- **Adjacent value:** Can also power "lunch and learn" sessions, onboarding video walkthroughs, and async video annotation (team members can leave timestamped comments for colleagues in different time zones).

### 4. Theatrical Premiere Events (Premium Co-Viewing)

Studios spend hundreds of millions on marketing new releases. A premium virtual premiere event -- with controlled access, curated social experience, and exclusivity -- is a new distribution channel.

- **The product:** Limited-attendance virtual screenings with social layers. Think 50-100 people per "room," curated by interest or social graph. Pre-show social mixer. Synchronized viewing with spatial audio reactions. Post-show discussion facilitated by AI or a human moderator.
- **Business model:** B2B to studios/streamers. Per-event licensing. Premium tickets ($10-20) for consumers who want the "opening night" experience at home. Merch integration (buy the shirt while watching).
- **Why it could work:** Studios already spend on premieres, press screenings, and fan events. Virtual versions are dramatically cheaper and reach global audiences. The key is making them feel exclusive and social, not like watching alone with a chat sidebar.

### 5. Music Listening Rooms (The Overlooked Cousin)

Co-listening is underserved. Spotify Group Sessions are broken. Turntable.fm (2011, iconic, shut down) proved the concept but couldn't monetize. The market has evolved.

- **The product:** Intimate listening rooms (2-8 people) with DJ rotation. Spatial audio so each person "sits" in a different position. Reactions are ambient (tapping, head nodding via phone accelerometer, not text). Album listening parties for new releases with artist commentary.
- **Business model:** Freemium consumer app. Premium features (higher-quality audio, larger rooms, recording). B2B to labels/artists for release events. Integration with Spotify/Apple Music APIs.
- **The unlock:** AI DJ that reads the room's energy and selects tracks to maintain a collective mood. The algorithm optimizes for group satisfaction, not individual taste.

---

## Breakthrough Ideas

### 1. "The Living Room" -- Spatial Audio Presence Without Video

The missing piece in co-viewing isn't video chat (nobody wants their face on screen for a 2-hour movie) or text chat (too thin). It's **ambient audio presence** -- the feeling that someone is in the room with you.

- Each participant occupies a spatial position in a virtual "living room." You hear their breathing, their laughter, their gasps -- placed in 3D space via spatial audio (AirPods Pro, any spatial-audio headphones).
- Smart audio ducking: the content audio is primary. Human sounds are mixed underneath at low volume, just enough to create presence without distraction. When someone actually speaks ("oh my god did you see that"), their voice rises above the content temporarily.
- No video, no chat UI, no visual distraction. Just the movie on your screen and the feeling of people beside you.
- **The uncanny valley of presence:** This would need incredibly careful audio engineering. Done poorly, hearing someone breathe is creepy. Done well, it's the closest you can get to "being there" without VR.

### 2. "Pulse" -- Collective Emotion Visualization

What if you could see the emotional state of everyone watching the same thing, in real-time?

- During a live event or synchronized watch party, each viewer's phone passively measures engagement signals: ambient audio (cheering, gasping, silence), grip pressure (accelerometer), viewing posture (gyroscope -- leaning forward vs. reclined), and heart rate (Apple Watch/wearables).
- These signals are aggregated and visualized as a real-time "pulse" overlay on the content: a gentle glow around the screen that shifts color and intensity based on collective emotion. Red for excitement, blue for calm, white for shock, pulsing faster when the group is engaged.
- You don't need to see individual reactions -- you feel the crowd. It recreates the theater/stadium sensation of collective energy without requiring any active input from viewers.
- Post-viewing, the "pulse timeline" becomes a data artifact: you can see exactly when the audience peaked, dipped, or split (some excited, some horrified). Studios would pay for this data. Fans would share pulse maps like they share Spotify Wrapped.

### 3. "The Commentary Layer" -- AI-Powered Shared Annotation

Instead of a chat sidebar, build a commentary system that lives inside the content:

- Viewers can leave "audio annotations" at specific timestamps -- short voice clips (max 10 seconds) that play for others at that exact moment in the content, mixed at low volume under the main audio.
- AI moderates and curates: the best/funniest/most insightful annotations float to the top. Bad ones get filtered. The result is a crowdsourced "commentary track" that evolves over time as more people watch.
- Different "tracks" emerge: the "funny friends" track, the "film analysis" track, the "first-time watchers" track, the "superfan" track. You choose which layer to listen to (or none).
- **The social feedback loop:** Your annotation gets heard by thousands of people. You get a notification: "47 people laughed at your comment during the red wedding scene." This creates a new kind of social currency around media literacy and humor.
- Studios could offer official "watch with the director" or "watch with the cast" annotation layers as premium content.

### 4. "Campfire Screening" -- Small Groups, High Ritual, Long Memory

Take the "Campfire" concept from the ephemeral moments research and apply it to co-viewing:

- A group of 3-6 friends commits to a recurring watch ritual: "Every Sunday night, we watch the next episode together." The app manages the schedule, the sync, and the memories.
- Before each screening: a 5-minute "gathering" phase with spatial audio chat while the app counts down. Anticipation is part of the experience.
- During: ambient presence (see idea #1). Minimal UI. Just the content and the feeling of your people.
- After: a 15-minute "campfire" discussion. The app captures the discussion, generates a summary, and adds it to the group's shared history.
- Over seasons and years, the group accumulates a rich archive: every show you watched together, every discussion you had, every reaction captured. Your shared cultural history, browsable and searchable.
- **Monetization:** Premium group features ($5/month per group). Physical artifacts (printed "year in review" of your watch group's history). Partnership with streaming services to recommend "your group's next show" based on collective taste.

### 5. "Sync Layer" -- A Protocol, Not a Product

The biggest co-viewing problem is structural: every solution is product-specific, locked to certain streaming services, and fragile. What if co-viewing were an open protocol instead?

- An open-source synchronization protocol that any streaming service, social platform, or third-party app can implement. Like how WebRTC standardized real-time communication, a "SyncLayer" protocol standardizes shared playback state.
- The protocol handles: playback synchronization, presence signaling, reaction events, annotation timestamps, and social graph interop.
- Any app can add a "Watch Together" button that works with any other app implementing the protocol. Netflix users and Disney+ users in the same watch party, each playing from their own subscription but perfectly synced.
- The business: the protocol is free and open. The company behind it monetizes through premium hosting (managed sync servers), enterprise support, and an ecosystem of tools and integrations built on the protocol.
- **Why this could work:** The fragmentation of streaming services means no single platform will build the definitive co-viewing experience. A protocol-level solution lets the ecosystem solve it collectively, the way email works across providers.

### 6. "Reaction Theater" -- Lean Into the Performance

The most popular co-viewing content on the internet isn't watch parties -- it's reaction videos. Millions of people watch strangers react to content on YouTube. This suggests that reactions themselves are entertainment.

- Build a product where the watch party IS a performance. A host (creator, critic, comedian) watches content live with an audience. The host's reactions, commentary, and energy are the product. The underlying content is just the substrate.
- Audience members see the host's face/reactions overlaid or picture-in-picture alongside the content. They can also see aggregated audience reactions (emoji storms, collective volume meter, chat).
- This is what Twitch Watch Parties tried to be, but without the licensing burden: the host doesn't stream the content. Each viewer plays it themselves. Only the host's face, voice, and reactions are streamed.
- **Differentiation from YouTube reaction videos:** It's live (not edited), synchronized (everyone is at the same moment), and interactive (audience shapes the host's experience via chat, polls, predictions).
- **Monetization:** Subscriptions to favorite hosts. Tipping. Studio sponsorships for premiere reaction events. Clip sharing for post-watch virality.

---

## Links

- [[live-event-participation]] — live events with audience agency go beyond passive co-viewing
- [[co-creation-at-scale]] — co-creation is the active extreme of the participation spectrum
- [[ephemeral-shared-moments]] — synchronized shared experiences; watch parties are one format

## Sources

- [Teleparty Official Site](https://www.teleparty.com/) -- features, supported platforms, freemium model details
- [Rave Official Site](https://rave.io/) -- mobile co-viewing app features and platform support
- [Scener Official Site](https://scener.com/) -- virtual movie theater concept, Agora SDK integration, premium tier
- [Kosmi Official Site](https://kosmi.io/) -- free virtual hangout platform, Techstars/Mozilla/Comcast backed
- [Hyperbeam Official Site](https://hyperbeam.com/) -- developer API for embeddable co-browsing, pricing model
- [Apple Vision Pro](https://www.apple.com/apple-vision-pro/) -- SharePlay spatial computing, Persona co-viewing, spatial audio
- [Apple SharePlay iPhone User Guide](https://support.apple.com/guide/iphone/shareplay-iph8d3017ced/ios) -- system-level synchronized playback
- [TechCrunch: Hulu Watch Party Launch](https://techcrunch.com/2020/05/28/) -- Hulu co-viewing feature timeline
- [TechCrunch: Amazon Watch Party on Smart TVs](https://techcrunch.com/2022/06/29/) -- Amazon feature expansion
- [a16z: Social Strikes Back](https://a16z.com/social-strikes-back/) -- social entertainment thesis, video as interactive experience, community-driven engagement
- [Twitch Blog: Watch Parties](https://blog.twitch.tv/) -- Twitch Watch Party feature (2020-2022, discontinued)
- [Discord Activities](https://discord.com/) -- Watch Together YouTube integration, 200M+ MAU distribution
- [Bigscreen VR](https://www.bigscreenvr.com/) -- social VR theater, $11M+ raised, Quest platform
- [Fortnite Events](https://www.epicgames.com/fortnite/) -- Travis Scott concert (12.3M concurrent), in-game premieres

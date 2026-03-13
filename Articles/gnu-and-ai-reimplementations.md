---
tags:
  - reading
  - domain-expansion
source:
  - https://antirez.com/news/162
  - https://lowendbox.com/blog/the-linux-kernel-will-soon-be-mit-licensed-and-copyleft-will-be-dead-within-5-years/
date: 2026-03-13
---

# GNU and the AI Reimplementations

## Summary

Antirez argues that AI-powered reimplementations of software are legally and ethically the same process the GNU project pioneered in the '80s — just drastically faster. Copyright protects expressions (code), not ideas or behavior. Reimplementations have always been fair game, and the people who cheered for GNU but oppose AI rewrites are applying the rules selectively.

## Key Ideas

- Stallman's playbook: reimplement UNIX tools without copying code, but make them recognizably different (faster, more featureful, scriptable). This created legal distance and genuine improvement simultaneously.
- Linux followed a similar chain: Linus was exposed to Minix (which Tanenbaum wrote with UNIX source knowledge), yet nobody seriously claimed copyright violation. Reimplementation through layers of indirection has always been accepted.
- Copyright law protects *expressions*, not *ideas or behavior*. Clean-room implementation is litigation optimization, not a legal requirement.
- AI doesn't change the legal nature of reimplementation — it collapses the cost. The "uncompressed copy" fear is largely illusory; agents produce code organically, diverging naturally through iteration.
- The power asymmetry inverts: previously only corporations could fund reimplementation at scale. Now small teams can reimplement corporate software systems.
- "The Stallman way" — reimplementations should evolve the original, not just replicate it. Fair but lazy vs. fair and valuable.
- Software was already suffering from commodification and bloat pre-AI. It's not obvious AI makes this worse; it may restore some craft by making ambitious projects feasible for small teams.

## Reaction

The historical framing is the strongest part. It's genuinely hard to argue that AI reimplementation is categorically different from what GNU, Linux, and decades of open source did. The legal mechanics are identical — the speed changed, the nature didn't.

The most interesting claim: the power inversion. GNU/Linux was *also* a power inversion (passionate individuals vs. AT&T/SCO), but it took decades and required genius-level contributors. AI collapses that to weekends. That's a qualitative shift even if the legal framework hasn't moved.

What he glosses over: the social contract. GNU reimplementations were celebrated because they *freed* users from proprietary lock-in. AI reimplementations can just as easily strip-mine open source to build proprietary clones. The legal argument is symmetric, but the ethical one isn't always.

**Our extension — reimplementing products, not just code:** If reimplementing code is cheap, reimplementing entire *products* becomes a viable business model. The playbook: take the known shape, strip the bloat, add a sharp opinion. Figma→Sketch, Linear→Jira — same pattern, pre-AI. What changes is the minimum viable team drops from 10-20 to 2-3 people with taste and domain knowledge. The bottleneck shifts entirely to knowing what's broken and having a real opinion about fixing it. Scratch your own itch becomes the ultimate reimplementation filter.

The dark version: SEO clone farms reimplementing SaaS with zero taste, undercutting on price. Fair but lazy. Race to zero.

## Connections

- [[sota-models-over-custom-ones]] — If anyone can reimplement anything, the moat is never the code. Value accrues to taste, ideas, and context engineering.
- [[ai-companies-fewer-people]] — The power inversion in action: 2-3 person teams reimplementing what used to require corporate engineering orgs. The 6x revenue-per-employee gap is partly this dynamic.
- [[commoditized-crawling-unlocks]] — Reimplementation is another instance of AI flattening execution costs, pushing value toward judgment and design.
- [[PRINCIPLES]] — "Scratch your own itch" as the reimplementation filter: the best targets are tools you use daily and are frustrated by, because you already carry the spec and the opinion.

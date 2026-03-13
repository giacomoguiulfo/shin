---
tags:
  - reading
  - domain-expansion
source: https://danielmiessler.com/blog/sota-models-over-custom-ones
date: 2026-03-13
---

# SOTA Models Over Custom Ones

## Summary

Daniel Miessler argues against building custom/fine-tuned AI models for specific tasks. Instead, organizations should use the best general-purpose (SOTA) models, which will keep getting cheaper — including open source — making the cost argument for small specialized models moot.

## Key Ideas

- Tasks that look specialized (email labeling, security event processing, report writing) actually benefit enormously from broad world knowledge. Narrow models miss this.
- "Anytime you think you're using a small model for a small task, there's usually a whole lot more going into a given decision than just that individual area of expertise."
- The human parallel: the best specialists aren't just deep — they have wide general experience that informs judgment. Same applies to AI.
- The future isn't "hundreds of tiny specialized models" — it's SOTA getting cheaper and commoditized.
- Use powerful general models with good context management rather than portfolios of custom solutions.

## Reaction

Mostly right, but arguing against a position that's already losing. The fine-tune-everything wave peaked in 2023-2024. The economics shifted faster than expected, and the fine-tuning tax (data curation, eval pipelines, drift management, retraining) turned out to be brutal.

The real gap in the argument: he undersells the **context engineering** problem. "Use SOTA with sophisticated context management" hand-waves over what is actually the hard part now. The model being smart enough was never the bottleneck — getting the right information in front of it at the right time is. That complexity doesn't disappear when you stop fine-tuning, it just moves.

Open questions:
- Is there a floor? Are there domains (medical imaging, chip design) where SOTA + context still can't match fine-tuned?
- The "small model" case is really a latency/cost case (sub-50ms at scale), not a capability case — Miessler doesn't address this.
- Open source is the strongest version of his argument but he only mentions it in passing.

## Connections

- The vault + worktree pipeline is this thesis in practice: invest in context infrastructure (CLAUDE.md, project notes, structured handoffs) to make a general model effective for specific domains, rather than customizing the model itself.
- [[ai-and-software-engineering]] — context engineering (CLAUDE.md, project notes, structured handoffs) is the successor to fine-tuning — same thesis from the constraints angle
- [[kanvify]] — Kanvify's AI features use frontier models with context, not fine-tuned models — this thesis in practice

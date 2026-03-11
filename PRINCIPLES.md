---
tags: principles, decision-framework
---

# Principles

Guiding principles for building and decision-making. Reference these when evaluating ideas, scoping work, or making trade-offs.

## Product & Idea Selection

**Scratch Your Own Itch** — Build things you personally need. You're the first user, the fastest feedback loop, and the most honest critic. If you don't feel the pain, you'll guess wrong about what matters.

## Naming

**Anime-Inspired Names** — Projects get named after anime techniques/powers that metaphorically match what the product does. Examples: Kage Bunshin (shadow clones → parallel job applications), Domain Expansion (JJK → expanding your knowledge domain).

## Building

**YAGNI (You Aren't Gonna Need It)** — Don't build for hypothetical future requirements. Build what's needed now. Features that "might be useful someday" almost never are, and they add maintenance burden today.

**KISS (Keep It Simple, Stupid)** — The simplest solution that works is the best solution. Complexity is a cost, not a feature. If you can't explain the architecture in one sentence, it's too complicated.

**DRY (Don't Repeat Yourself)** — Every piece of knowledge should have a single, unambiguous representation. When you change something, you should only need to change it in one place.

**WET (Write Everything Twice)** — The counterbalance to DRY. Don't abstract too early. It's fine to duplicate code until you've seen the pattern three times. Premature abstraction is worse than duplication — it couples things that shouldn't be coupled and makes future changes harder.

**No Python** — Avoid Python unless absolutely necessary (e.g., a library with no alternative, low-level ML work). Default to TypeScript/Node for scripting and tooling.

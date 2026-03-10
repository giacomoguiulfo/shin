---
tags:
  - til
  - pattern
  - tool-eval
date: 2026-03-10
---

# Tool Eval: Always Check Trust Before Recommending Adopt

## Context

Evaluated GrapeRoot and initially recommended "adopt (trial)" based on the concept alone. User rightly pushed back — it was a closed-source binary from an unverified solo dev with full codebase access.

## The Rule

Before recommending **adopt** or **trial**, always verify:

1. **Source availability** — Is the code open source? Can we audit it?
2. **Developer/org credibility** — Who built it? Track record? Community size?
3. **Access scope** — What does it touch? (codebase read, network, credentials, MCP server)
4. **Dependency weight** — What does it require? (runtimes, services, accounts)

The higher the access scope, the higher the trust bar. A CLI that reads your entire codebase via MCP is not the same as a color palette tool.

## The Fix

Never suggest adopt without doing the trust check first. Default to **revisit** if the concept is good but trust is unverified.

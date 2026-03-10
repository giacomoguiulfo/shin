---
name: tool-radar
description: "Evaluate a tool, framework, or library. Fetch its site, assess fit, run trust checks, and write a Tool-Eval note + Tool-Radar entry."
user-invocable: true
---

# Tool Radar

Evaluate a tool and decide: adopt, skip, or revisit.

---

## Input

The user provides a tool name, URL, or both after `/tool-radar`. Examples:
- `/tool-radar https://rwsdk.com/`
- `/tool-radar Bun`
- `/tool-radar https://some-tool.dev some context about why I'm looking at it`

## The Job

### 1. Research

- If a URL is provided, fetch the homepage and docs to understand what the tool does
- If only a name is given, use web search to find the official site, then fetch it
- Identify: what it is, what problem it solves, tech stack, key features

### 2. Trust Check (from [[Tool-Eval-Process-Checklist]])

Before recommending adopt, verify:
1. **Source availability** — Open source? Can we audit the code?
2. **Developer/org credibility** — Who built it? Track record? Community size?
3. **Access scope** — What does it touch? (codebase read, network, credentials, MCP server)
4. **Dependency weight** — What does it require? (runtimes, services, accounts)

The higher the access scope, the higher the trust bar.

### 3. Assess Fit

Consider against the user's existing stack and tools:
- Read `Tool-Radar.md` to see what's already evaluated
- Read `Profile.md` for preferences and context if relevant
- Does this overlap with something already adopted or available?
- Does it solve a real problem the user has, or is it a solution looking for a problem?

### 4. Verdict

Pick one:
- **Adopt** — Use it now or plan to. Must pass trust check.
- **Skip** — Doesn't fit, overlaps with existing tools, or trust issues.
- **Revisit** — Concept is good but timing, maturity, or fit isn't right yet. Include trigger condition ("revisit when...").

### 5. Write It Up

Create `TILs/Tool-Eval-<ToolName>.md` with this structure:

```markdown
---
tags:
  - tool-eval
  - <verdict>
date: <today>
verdict: <adopt|skip|revisit>
---

# <Tool Name>

## What It Is

One-liner + link.

## Problem It Solves

What gap does it fill?

## Key Observations

- 3-5 bullet points on what stood out

## Verdict

**<Verdict>.** 2-3 sentences on why. If skip/revisit, what would change the call.
```

Then add a one-liner to `Tool-Radar.md` under the appropriate section (Adopt / Skip / Revisit), following the existing format:
```
- [[Tool-Eval-<ToolName>]] — One-line summary. (<date>)
```

### 6. Discussion

After writing up, give the user a conversational summary and invite discussion. Don't just dump the note — share your actual take.

## Rules

- Always do the trust check before recommending adopt
- Default to **revisit** if the concept is good but trust is unverified
- Keep eval notes concise — this is a radar scan, not a deep dive
- If the tool is clearly irrelevant, skip the full write-up and just add to Tool-Radar.md under Skip with a one-liner explanation
- Do NOT create commits — just write the files

---
name: vault-review
description: "Scan the vault for orphaned notes, stale projects, weak links, and Profile gaps. Propose concrete fixes."
user-invocable: true
---

# Vault Review

Health check for the knowledge vault. Surfaces what's stale, disconnected, or missing.

---

## The Job

Run these checks in order and report findings:

### 1. Orphaned Notes
- Scan all `.md` files outside `Templates/`
- Flag any note that is neither linked to nor linked from another note (no `[[wikilinks]]` pointing to it, and it contains no outgoing `[[wikilinks]]`)
- Ignore `Home.md`, `Profile.md`, `Ideas.md`, `Brain-Dump.md`, and `CLAUDE.md`

### 2. Stale Projects
- Read every file in `Projects/`
- Flag any project whose `_Last updated:_` date is more than 14 days old
- Show the last-updated date and the project name

### 3. Profile Evidence Gaps
- Read `Profile.md`
- Flag any belief, like, dislike, or theme that has zero `[[wikilinks]]` as supporting evidence
- These should either get linked to an existing article or noted as needing one

### 4. Missing Cross-Links
- For each article in `Articles/`, check if it's linked from `Profile.md`
- For each belief/theme in `Profile.md`, check if it has at least one article link
- Suggest specific links that should be added

### 5. Suggested Connections
- Look for thematic overlap between notes that aren't currently linked
- Propose 2-3 new `[[wikilinks]]` that would strengthen the graph

## Output Format

```
## Vault Health Report

### Orphaned Notes
- (list or "None found")

### Stale Projects
- (list or "All current")

### Profile Evidence Gaps
- (list or "All beliefs have evidence")

### Missing Cross-Links
- (list or "All connected")

### Suggested Connections
- (2-3 proposed links with rationale)
```

## Rules

- Read files, don't modify them — only propose changes
- Ask before making any edits
- Keep the report concise — findings only, no filler
- If everything looks healthy, say so and keep it short

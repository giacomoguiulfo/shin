# Mind — Obsidian Vault

This is Giacomo's personal knowledge vault. It serves as a shared context layer between the user and Claude Code across sessions.

## How to Use This Vault

### Starting a Session
When the user says "let's work on [ProjectX]", read `Projects/[project].md` first. The `## Current State` section tells you where we left off.

### Ending a Session
Before wrapping up, update the project note's `## Current State` section with:
- What we did this session
- What's next
- Any open questions or blockers

**Domain Expansion auto-capture:** When ending a domain-expansion session, also capture any article notes and profile updates that haven't been saved yet before updating the project's Current State.

### Creating Projects
- Create the project note in `Projects/`
- Add it to `Home.md` under **Active Projects**

### Creating Notes
- Article/reading notes go in `Articles/`
- TILs and patterns go in `TILs/`
- Decisions, ideas, and other notes live as **flat notes in the root**
- Use frontmatter tags to categorize: `#til`, `#decision`, `#pattern`, `#idea`
- Link notes to projects with `#project/project-name` and `[[wikilinks]]`
- Use `Templates/` for consistent formatting

### Structure
```
mind/
├── Articles/       # Reading & domain-expansion notes
├── Projects/       # One note per project (stack, conventions, current state)
├── Templates/      # Note templates
├── TILs/           # Things I learned, patterns, snippets
└── *.md            # Decisions, ideas, and other flat notes
```

### Session Boundaries
- **Mind never writes project code.** Planning, decisions, and vault work only.
- When implementation is needed, create a worktree and dispatch a Claude session there (see [[worktree-pipeline]]).
- The prompt is the handoff — pre-digest all context the worker session needs.
- Multiple worktrees can run in parallel. Each is independent.

### Principles
- **Specs are migrations** — transient, not permanent. Code is the source of truth.
- **Notes capture durable knowledge** — decisions, learnings, patterns. Not work artifacts.
- **Minimal structure** — few folders, tags and links over hierarchy.
- **Project notes are onboarding docs** — everything Claude needs to pick up and go.

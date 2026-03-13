# Mind — Obsidian Vault

This is Giacomo's personal knowledge vault. It serves as a shared context layer between the user and Claude Code across sessions.

## How to Use This Vault

### Starting a Session
When the user says "let's work on [ProjectX]", read `Projects/[project].md` first. The `## Current State` section tells you where we left off.

**Reminders:** At the start of every session, check `Reminders.md` for items due today or overdue. Surface them before diving into work. Move completed items to the `## Done` section with the completion date.

### Ending a Session
Before wrapping up, update the project note's `## Current State` section with:
- What we did this session
- What's next
- Any open questions or blockers

**Article auto-capture:** When ending a session where articles were discussed, capture any article notes and profile updates that haven't been saved yet.

### Creating Projects
- Create the project note in `Projects/`
- Add it to `Home.md` under **Active Projects**

### Sharing Content (Articles, Posts, Links)
When Giacomo shares a link or article, **don't jump straight to capturing**. First, discuss it — react, push back, surface connections, ask questions. Have an actual conversation to discover what's interesting and what we think. Only offer to capture after we've engaged with the ideas.

**Assume Giacomo hasn't read the article.** He shares links to discuss, not to quiz. Lead with a clear summary of what the article says before reacting to it, so we're on the same page. Then discuss.

### Creating Notes
- Article/reading notes go in `Articles/`
- Research notes go in `Research/`
- TILs and patterns go in `TILs/`
- Decisions, ideas, and other notes live as **flat notes in the root**
- Use frontmatter tags to categorize: `#til`, `#decision`, `#pattern`, `#idea`
- Link notes to projects with `#project/project-name` and `[[wikilinks]]`
- Use `Templates/` for consistent formatting

### Structure
```
mind/
├── Articles/       # Reading & domain-expansion notes
├── Projects/       # One note per project (vision, decisions, connections, current state)
├── Research/       # Research notes & market analysis
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
- **Project notes are strategic, not technical** — what it is, why it matters, key decisions, and connections to research. Technical details (stack, conventions, directory structure, dev commands) live in each repo's own CLAUDE.md.
- See `[[PRINCIPLES]]` for building & decision-making principles (Scratch Your Own Itch, YAGNI, KISS, DRY/WET).

---
tags:
  - project/worktree-pipeline
  - pattern
status: planning
---

# Worktree Pipeline

Autonomous development orchestration system. Mind plans and dispatches; worktrees implement, review, and merge — each in isolated Zellij sessions with their own Claude instance, preview server, and ralph loop.

## Architecture

```
┌─────────────────────────────────────────────┐
│  MIND (orchestrator)                        │
│  Plans, dispatches, reviews results,        │
│  manages vault. Never writes project code.  │
├─────────────────────────────────────────────┤
│  WORKTREES (workers)                        │
│  Each: Zellij session + Claude + ralph loop │
│  + preview server. Long-lived, inspectable. │
├─────────────────────────────────────────────┤
│  MERGE QUEUE (integrator)                   │
│  Sequential rebase → test → merge to main   │
└─────────────────────────────────────────────┘
```

### Session boundaries

- **Mind never writes project code.** Planning, decisions, and vault work only.
- When implementation is needed, mind creates a worktree and dispatches a Claude session.
- The prompt is the handoff — mind pre-digests all context the worker needs.
- Multiple worktrees can run in parallel. Each is independent.

### Claude-mem scoping

Each worktree runs its own Claude process with `cwd` inside the worktree directory. Claude-mem tags observations by `path.basename(cwd)`, so worktree observations are scoped separately from mind. Mind observations stay clean (planning/decisions only).

## State

All worktree state lives in `~/.mind/worktrees.json`:

```json
{
  "facebook-metrics": {
    "project": "kanvify",
    "branch": "wt/facebook-metrics",
    "worktree_path": "~/Github/kanvify-wt/facebook-metrics",
    "port": 3001,
    "zellij_session": "wt-facebook-metrics",
    "status": "implementing",
    "task": "Fix Facebook metrics auth using Insights API",
    "created_at": "2026-03-10T09:00:00Z",
    "completed_at": null
  }
}
```

Statuses: `created → implementing → simplifying → reviewing → ready → merging → merged → failed → conflict`

## CLI: `wt`

Shell script(s) that manage the lifecycle. Mind calls these via Bash.

| Command | Phase | What it does |
|---------|-------|--------------|
| `wt create <project> <name> "<task>"` | 1 | Create git worktree, branch, allocate port, register in state |
| `wt destroy <name>` | 1 | Clean up worktree, free port, remove from state |
| `wt list` | 1 | Show all worktrees: name, status, port, branch |
| `wt start <name>` | 2 | Open Zellij session, launch Claude with task prompt |
| `wt attach <name>` | 2 | Attach to Zellij session (inspect/resume) |
| `wt server <name>` | 3 | Start preview server in worktree on allocated port |
| `wt review <name>` | 4 | Run quality pipeline: simplify → review → security-review |
| `wt merge [name]` | 5 | Rebase oldest `ready` worktree onto main, test, merge |
| `wt status` | 6 | Summary for mind: running, ready, blocked |

## Zellij layout per worktree

```kdl
layout {
    pane name="claude" focus=true
    pane name="server" size="20%" {
        command "bin/dev"
        args "-p" "$PORT"
    }
    pane name="logs" size="15%" {
        command "tail"
        args "-f" "log/development.log"
    }
}
```

Each worktree gets a Zellij session named `wt-<name>` with this layout. `wt attach` connects you directly.

## Worker session lifecycle

1. `wt start` launches Zellij session in worktree directory
2. Claude pane runs: `env -u CLAUDECODE claude --permission-mode acceptEdits`
3. Initial prompt contains the task (from mind's dispatch)
4. Ralph loop breaks task into stories, implements iteratively
5. On completion, a Stop hook updates `worktrees.json` status → `simplifying`
6. Quality pipeline runs automatically (Phase 4):
   - Fresh Claude session: `/simplify` on changed files
   - Fresh Claude session: code review
   - Fresh Claude session: security review
   - Each is a separate context window, focused task
7. All pass → status → `ready`
8. Any fail → status → `failed`, details logged for inspection

## Merge queue

Sequential, one at a time:

1. Pick oldest worktree with status `ready`
2. `git rebase main` in the worktree
3. If conflicts → status `conflict`, stop (user or Claude resolves)
4. Run test suite (`bin/rails test && pnpm test`)
5. If tests fail → status `failed`, stop
6. Fast-forward merge to main
7. Clean up worktree, status → `merged`
8. Next.

## Port allocation

Base port 3001, incrementing. State file tracks which ports are in use. `wt destroy` frees the port. Simple, no daemon needed.

## Roadmap

### Phase 1 — Worktree lifecycle ← start here
- [ ] `wt create` / `wt destroy` / `wt list`
- [ ] State file management (`~/.mind/worktrees.json`)
- [ ] Port allocation
- [ ] Git worktree + branch creation
- [ ] Add session boundary principle to mind's CLAUDE.md

### Phase 2 — Session dispatch
- [ ] Zellij layout template
- [ ] `wt start` — launch Zellij session + Claude with task prompt
- [ ] `wt attach` — connect to running session
- [ ] Stop hook to update state on session end
- [ ] Verify claude-mem scopes worktree observations correctly

### Phase 3 — Preview servers
- [ ] `wt server` — start dev server in worktree on allocated port
- [ ] Integrate into Zellij layout (auto-start in server pane)
- [ ] `wt list` shows preview URLs

### Phase 4 — Quality pipeline
- [ ] `wt review` — sequential simplify → review → security-review
- [ ] Each step is a fresh `claude -p` session in the worktree
- [ ] Auto-trigger on implementation completion
- [ ] Status progression through review stages

### Phase 5 — Merge queue
- [ ] `wt merge` — rebase, test, merge, cleanup
- [ ] Conflict detection and status update
- [ ] Test suite integration

### Phase 6 — Mind integration
- [ ] `wt status` summary for mind session context
- [ ] SessionStart hook or skill that reads worktrees.json
- [ ] Mind can dispatch new tasks while others run

## Dependencies

- **Zellij** — `brew install zellij`
- **Git worktrees** — built into git
- **claude-mem** — already installed, scopes by cwd basename

## Open questions

- Should the `wt` CLI be a shell script, a Ruby script, or a small Go binary? Shell is simplest to start.
- How does ralph-skills (prd.json story breakdown) integrate with `wt start`? Does mind generate the prd.json, or does the worker session break down the task itself?
- Kanvify already has `/.factory/` (Dark Factory) — is this an evolution of that, or a replacement?
- Worktree naming: `~/Github/kanvify-wt/<name>` or `~/Github/wt/<project>-<name>`? Affects claude-mem project naming.

## Current State

_Last updated: 2026-03-10_

**Status**: Planning complete. Roadmap defined.

**Next**: Phase 1 — build `wt create` / `wt destroy` / `wt list` and the state file format. Install Zellij.

**Decided**:
- Zellij over tmux (declarative layouts, named panes, WASM plugin potential)
- Mind never writes project code (session boundary principle)
- Prompt is the handoff (not the project note — enables parallelism)
- Local-only merge queue (no GitHub PRs for now)
- `env -u CLAUDECODE` to bypass nesting guard for dispatch

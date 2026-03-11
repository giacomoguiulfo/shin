---
tags:
  - tool-eval
  - adopt
date: 2026-03-11
verdict: adopt
---

# Lazygit

## What It Is

Terminal UI for git commands. A single Go binary that wraps git in an interactive, keyboard-driven interface. [GitHub](https://github.com/jesseduffield/lazygit)

## Problem It Solves

Git's CLI is powerful but has a steep surface area — interactive rebase, hunk staging, cherry-picking, and conflict resolution all require memorizing flags and editing temp files. Lazygit makes these operations visual and fast without leaving the terminal.

## Trust Check

- **Source:** Fully open source (MIT), 73.9k stars, 2.6k forks
- **Developer:** Jesse Duffield — also built lazydocker. Established track record in terminal tooling
- **Access scope:** Local only. Reads/writes git repos through standard git. No network access, no credentials beyond what git already has
- **Dependency weight:** Single Go binary. No runtime deps. Install via Homebrew or direct download

## Key Observations

- Worktree management built in — directly relevant to the worktree-heavy workflow we use with Claude Code
- Interactive rebase becomes drag-and-drop for commits — no more editing TODO files
- Hunk/line-level staging is visual and fast, better than `git add -p`
- Undo via reflog is surfaced as a first-class feature — safety net for risky operations
- Customizable keybindings and custom commands mean it adapts to any workflow

## Verdict

**Adopt.** Fits the terminal-native workflow perfectly, zero trust concerns (open source single binary, local-only access), and directly improves the git operations we do most — rebasing, worktree management, and selective staging. The 73.9k stars and active maintenance make this one of the most battle-tested terminal tools available.

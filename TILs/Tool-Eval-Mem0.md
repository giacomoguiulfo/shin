---
tags:
  - tool-eval
  - revisit
date: 2026-03-10
verdict: revisit
---

# Mem0

## What It Is

Managed memory layer for AI apps. Adds persistent memory (user prefs, conversation history, relational knowledge) to AI agents via a simple API. https://mem0.ai/

## Problem It Solves

AI agents are stateless by default — users repeat themselves, context is lost between sessions. Mem0 provides the persistence layer so agents remember.

## Key Observations

- Simple API: add/search/update/delete memories in a few lines
- Memory types: user-level, agent-level, session-level, plus graph memory for relational connections
- MCP integration — could plug into Claude Code or other MCP clients
- Managed infra: vector store, reranking, graph services all handled
- Multimodal support
- SOC 2 Type II, GDPR compliant
- Integrates with LangChain, CrewAI, Vercel AI SDK

## Verdict

**Revisit.** For personal dev workflow, the Obsidian vault already serves as a human-readable, version-controlled, structured memory layer — and it's not a black box. Mem0 shines for multi-user AI products (chatbots, support agents, AI features) where you need per-user persistent memory at scale. Worth revisiting if Kanvify or another project needs that.

## Notes

- Key tradeoff: opaque managed service vs. transparent git-backed vault
- The vault captures structured knowledge (decisions, TILs, project context); Mem0 captures conversational memory via embeddings and graphs — different use cases

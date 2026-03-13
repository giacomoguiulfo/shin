---
tags:
  - til
  - ai-agents
date: 2026-03-13
---

# Agent Directory as the Missing Layer

## Context

Meta acquired Moltbook (an "AI agent social network") — mostly an acqui-hire / marketing move. But the underlying concept of an **agent directory** is real.

## The Insight

MCP solves tool access (how an agent uses a service). But there's no standard for **agent discovery** — how agents find, authenticate with, and negotiate capabilities with *each other*. As agents proliferate, someone needs to own the registry/directory layer.

This is analogous to DNS for the web or service discovery in microservices (Consul, etcd). The agent ecosystem is missing this primitive.

## Why It Matters

- Whoever owns agent discovery owns the agent social graph — powerful network effects
- Meta buying into this makes sense: they already own identity + messaging surfaces (WhatsApp, Messenger)
- The pattern: tool access (MCP) is necessary but not sufficient. Discovery, trust, and negotiation between agents is the next layer up

## Connections

- [[worktree-pipeline]] — Our own agent orchestration needs a lightweight version of this: mind dispatching to worktree agents is a micro-directory problem
- [[collaborative-ai-business-building]] — Agent discovery is the infrastructure primitive that multi-agent business building needs at scale

---
title: "Google Reverse Proxy"
excerpt: "OpenAI-compatible reverse proxy for Google's AI products (Gemini CLI, Google AI Studio). Multi-account pool with quota balancing, failover, and a single bearer-token endpoint."
collection: projects
date: 2026-05-23
link: "https://github.com/david-courtis/google-reverse-proxy"
header:
  teaser: "google-reverse-proxy.png"
---

A Node.js / TypeScript proxy that exposes Google's Gemini CLI and Google AI Studio APIs behind an OpenAI-compatible interface, with multi-account pooling so heavy LLM workloads (Claude Code, OpenCode, custom agents) can transparently load-balance and survive per-account rate limits.

Features:

- **Multi-account pool** — combines OAuth (Gemini CLI) and API-key (AI Studio) credentials, with random / round-robin / failover selection strategies.
- **Quota awareness** — tracks per-account daily quotas, applies cooldowns, optionally auto-switches models when a preferred one is exhausted.
- **Gemini native tools** — opt-in passthrough for Google Search grounding and URL-context tools, with inline citation markers and grounding metadata on stream chunks.
- **Streaming thinking blocks** — surfaces Gemini's reasoning as DeepSeek-R1-style `<thinking>` blocks for clients that consume them.

Not yet published; under active development.

[GitHub](https://github.com/david-courtis/google-reverse-proxy)

---
title: "Discord LLM Chatbot"
excerpt: "Discord bot with multi-agent dialogue, vision, and per-channel chat memory. Wraps any OpenAI-compatible API so it can sit in front of self-hosted local LLMs."
collection: projects
date: 2025-08-19
link: "https://github.com/david-courtis/Discord-LLM-Chatbot"
header:
  teaser: "discord-llm-chatbot.png"
---

Long-running personal Discord bot with:

- **Multi-agent dialogue** — multiple personas can respond and interact within the same channel.
- **Vision support** — handles image attachments via vision-capable models.
- **Per-channel memory** — rolling context window per channel.
- **Trigger-word listening** — automatically replies to messages containing keywords (`why`, `how`, `?`, etc.) in designated channels, in addition to direct mentions.
- **OpenAI-compatible backend** — defaults to OpenAI, but configurable to wrap any local LLM API following the OpenAI completion format.

Built in Python with Poetry; uses `discord.py`.

[GitHub](https://github.com/david-courtis/Discord-LLM-Chatbot)

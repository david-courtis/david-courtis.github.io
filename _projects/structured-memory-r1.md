---
title: "StructMemoryR1 — Tree-Structured Memory with RL"
excerpt: "Three cooperating GRPO agents that build, query, and reason over a tree-structured memory of long multi-session dialogue. +9.0 F1 multi-hop and +13.8 F1 temporal vs. the strongest non-oracle baseline on LoCoMo."
collection: projects
date: 2026-04-24
link: "https://github.com/david-courtis/Structured-Memory-R1"
header:
  teaser: "structured-memory-r1.png"
---

Long-horizon conversational memory built as a *tree* rather than a flat embedding store, with three GRPO-trained agents cooperating on top of a Qwen2.5-3B-Instruct backbone:

- **Memory Manager** emits CRUD operations (`ADD` / `UPDATE` / `DELETE` / `NONE`) on the tree as dialogue arrives.
- **Retrieve Agent** issues a JSON search plan over the tree schema rather than scoring every memory independently.
- **Answer Agent** synthesises the final answer from the retrieved leaves.

Training is staged: the Answer Agent is trained first and frozen; the Retrieve Agent next with the frozen Answer Agent as the reward oracle; the Memory Manager last with both downstream agents frozen. All three are optimised with Group Relative Policy Optimization (GRPO).

On the LoCoMo benchmark (1:1:8 train/val/test, adversarial category excluded), StructMemoryR1 beats the strongest non-oracle baseline by **+9.0 F1 on multi-hop** and **+13.8 F1 on temporal** questions while remaining competitive on single-hop and open-domain.

[GitHub](https://github.com/david-courtis/Structured-Memory-R1)

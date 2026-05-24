---
title: "Multi-Directional Ablation of Refusal in LLMs"
excerpt: "Tests whether LLM refusal is mediated by multiple directions rather than a single one. Two-direction ablation outperforms the one-direction baseline — but not via the top-two ranked vectors."
collection: projects
date: 2024-12-18
link: "https://github.com/david-courtis/Multi-Directional-Ablation"
header:
  teaser: "multi-directional-ablation.png"
---

Extension of [*Refusal in Language Models Is Mediated by a Single Direction*](https://arxiv.org/abs/2406.11717) (Arditi et al., 2024). The original paper claims a single direction in activation space is sufficient to elicit / suppress refusal; this project tests whether **multiple** directions improve the ablation.

Key findings:

- Two-direction ablation improves refusal suppression over the one-direction baseline.
- The optimal pair is **not** the top-2 ranked candidate directions from the original method — interaction effects between directions matter.
- CE loss shows only a minor, linear increase as more directions are ablated, suggesting the additional directions are not load-bearing for general capabilities.

Built on top of [andyrdt/refusal_direction](https://github.com/andyrdt/refusal_direction). The original pipeline (direction extraction → selection → completion eval → CE loss) is extended to multi-vector ablation, with combinations evaluated by jailbreak score on a held-out harmful-prompt set.

[GitHub](https://github.com/david-courtis/Multi-Directional-Ablation) · [Reference paper (arXiv)](https://arxiv.org/abs/2406.11717)

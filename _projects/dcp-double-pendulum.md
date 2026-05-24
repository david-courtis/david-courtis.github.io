---
title: "DCP Tutorial #6 — Distributed Double Pendulums"
excerpt: "Tutorial showing how to compute thousands of chaotic double-pendulum simulations in parallel on the Distributive Compute Protocol. Each worker computes one pendulum's trajectory from a unique initial condition."
collection: projects
date: 2023-06-01
link: "https://colab.research.google.com/drive/1bdoYvrIDJMYfCfWZKZe1moWpyxWUZzkp?usp=sharing"
header:
  teaser: "dcp-double-pendulum.png"
---

Tutorial #6 in the Distributive Compute Protocol (DCP) series, packaged as a Google Colab notebook.

The double pendulum is the classic example of deterministic chaos — small differences in initial conditions diverge exponentially. This notebook computes many of them in parallel:

- **Input set** — initial polar angles and angular velocities of the blue and red planets, one row per pendulum.
- **Work function** — derives the equations of motion via the Lagrangian formulation, integrates, and converts to Cartesian coordinates for visualisation.
- **Output** — animated trajectories showing how nearby initial conditions diverge over time.

Each pendulum is computed by a separate DCP worker (browser, CLI, screensaver, or container), making this a clean demonstration of embarrassingly-parallel scientific computation on volunteer-style distributed compute.

[Google Colab notebook](https://colab.research.google.com/drive/1bdoYvrIDJMYfCfWZKZe1moWpyxWUZzkp?usp=sharing) · [DCP](https://dcp.cloud)

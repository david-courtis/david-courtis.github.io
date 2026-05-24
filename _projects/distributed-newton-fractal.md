---
title: "Distributed Newton Fractal"
excerpt: "Computes Newton–Raphson fractals on Distributive's web5 compute framework. Worker code is Python compiled to WebAssembly via Bifrost, so the same algorithm runs inside any browser-based DCP worker."
collection: projects
date: 2023-01-24
link: "https://github.com/david-courtis/DistributedCompute-NewtonFractal"
header:
  teaser: "distributed-newton-fractal.png"
---

Distributes Newton–Raphson fractal generation across [Distributive's](https://distributive.network/) web5 compute network. Each worker computes the basin of attraction for a chunk of the complex plane; the results are stitched into the final fractal image client-side.

The interesting bit is the toolchain: worker code is written in Python and compiled to WebAssembly via **Bifrost**, so the same algorithm runs inside any browser-based DCP worker without a Python runtime — turning every spare browser tab into a fractal-rendering node.

[GitHub](https://github.com/david-courtis/DistributedCompute-NewtonFractal) · [Distributive](https://distributive.network/)

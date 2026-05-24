---
permalink: /
title: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<style>
.timeline {
  margin: 1.5em 0 2em;
}
.timeline-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 1.6em;
}
.timeline-date {
  flex: 0 0 8.5rem;
  text-align: right;
  padding: 0.15em 1rem 0 0;
  font-size: 0.82em;
  font-weight: 600;
  color: var(--global-text-color-light);
  letter-spacing: 0.02em;
}
.timeline-marker {
  flex: 0 0 1.6rem;
  position: relative;
  align-self: stretch;
}
.timeline-marker::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0.55em;
  bottom: -1.6em;
  width: 2px;
  background: var(--global-border-color);
  transform: translateX(-50%);
}
.timeline-item:last-child .timeline-marker::before {
  display: none;
}
.timeline-marker::after {
  content: '';
  position: absolute;
  left: 50%;
  top: 0.45em;
  width: 0.7em;
  height: 0.7em;
  border-radius: 50%;
  background: var(--global-base-color);
  transform: translateX(-50%);
  z-index: 1;
}
.timeline-content {
  flex: 1;
  min-width: 0;
  padding-left: 0.6rem;
}
.timeline-title {
  font-weight: 700;
  font-size: 1.02em;
  color: var(--global-text-color);
  line-height: 1.3;
}
.timeline-org {
  font-size: 0.92em;
  color: var(--global-link-color);
  margin-top: 0.1em;
  margin-bottom: 0.4em;
}
.timeline-content ul {
  margin: 0.35em 0 0;
  padding-left: 1.2em;
  font-size: 0.92em;
  list-style: disc;
}
.timeline-content li {
  margin-bottom: 0.25em;
  line-height: 1.45;
}
@media (max-width: 700px) {
  .timeline-item { flex-direction: column; }
  .timeline-date {
    flex: 0 0 auto;
    text-align: left;
    padding: 0 0 0.2em 0;
  }
  .timeline-marker { display: none; }
  .timeline-content {
    padding-left: 0.9em;
    border-left: 2px solid var(--global-border-color);
  }
}
</style>

I'm a graduate researcher at the University of Toronto, working in the Data-Driven Decision Making Lab (D3M). My research is neuro-symbolic architectures that can verifiably reason and plan in open-world environments, with detours into interpretability, RL, and continual learning along the way.

## Current work

I'm currently building autonomous neuro-symbolic RL agents that discover the mechanics of unknown environments through systematic experimentation, knowledge representation, and world-model learning.

<video autoplay loop muted playsinline preload="auto" style="max-width: 420px; width: 100%; height: auto; display: block; margin: 1em 0;">
  <source src="/files/06-2026.mp4" type="video/mp4" />
  Your browser doesn't support embedded video. <a href="/files/06-2026.mp4">Download the video</a>.
</video>
<script>
  // Kick autoplay videos back into life on every page-show (handles bfcache
  // restores from back/forward nav and most "video stuck black" cases).
  (function () {
    var kick = function () {
      document.querySelectorAll('video[autoplay]').forEach(function (v) {
        try { v.load(); } catch (e) {}
        var p = v.play();
        if (p && p.catch) p.catch(function () {});
      });
    };
    kick();
    window.addEventListener('pageshow', kick);
    document.addEventListener('visibilitychange', function () {
      if (!document.hidden) kick();
    });
  })();
</script>

My first publication was accepted to **ICLR 2026** (Poster). We introduce a neurosymbolic planning framework that brings symbolic guarantees to LLM agents in partially-observable environments. It improves on previous baselines by 373% and attains state-of-the-art across central benchmarks.

*See:* [*Natural Language PDDL (NL-PDDL)*](https://openreview.net/forum?id=kWCNhRdcDI)

## Research interests

- Reinforcement learning
- World model building
- Mechanistic interpretability / XAI
- Verifiable formal reasoning
- Continual learning
- NLP and CV in neural space

## Experience

<div class="timeline">
{% for job in site.data.experience %}
  <div class="timeline-item">
    <div class="timeline-date">{{ job.date_range }}</div>
    <div class="timeline-marker"></div>
    <div class="timeline-content">
      <div class="timeline-title">{{ job.title }}</div>
      <div class="timeline-org">{% if job.org_url %}<a href="{{ job.org_url }}">{{ job.org }}</a>{% else %}{{ job.org }}{% endif %}{% if job.location %} · {{ job.location }}{% endif %}</div>
      <ul>
        {% assign bullets = job.bullets_short | default: job.bullets %}
        {% for b in bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines | strip }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
{% endfor %}
</div>

## Education

<div class="timeline">
{% for ed in site.data.education %}
  <div class="timeline-item">
    <div class="timeline-date">{{ ed.date_range }}</div>
    <div class="timeline-marker"></div>
    <div class="timeline-content">
      <div class="timeline-title">{{ ed.degree }}</div>
      <div class="timeline-org">{% if ed.institution_url %}<a href="{{ ed.institution_url }}">{{ ed.institution }}</a>{% else %}{{ ed.institution }}{% endif %}{% if ed.location %} · {{ ed.location }}{% endif %}</div>
      <ul>
        {% for b in ed.bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines | strip }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
{% endfor %}
</div>

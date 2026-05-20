---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download PDF version](/files/David_Courtis_CV.pdf){: .btn .btn--info}

Fields of Interest
======
Reinforcement Learning · World Model Building · Mechanistic Interpretability / XAI · Verifiable Formal Reasoning · Continual Learning · NLP and CV in Neural Space

Education
======
{% for ed in site.data.education %}
<h3>{% if ed.institution_url %}<a href="{{ ed.institution_url }}">{{ ed.institution }}</a>{% else %}{{ ed.institution }}{% endif %}{% if ed.degree %} — {{ ed.degree }}{% endif %} &nbsp; <em>({{ ed.date_range }})</em></h3>
<ul>
{% for b in ed.bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines | strip }}</li>
{% endfor %}</ul>
{% endfor %}

Industry & Research Experience
======
{% for job in site.data.experience %}{% if job.category == "industry" %}
<h3>{{ job.title }} &nbsp;·&nbsp; {% if job.org_url %}<a href="{{ job.org_url }}">{{ job.org }}</a>{% else %}{{ job.org }}{% endif %} &nbsp; <em>({{ job.date_range }})</em></h3>
<ul>
{% for b in job.bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines | strip }}</li>
{% endfor %}</ul>
{% endif %}{% endfor %}

Leadership & Projects
======
{% for job in site.data.experience %}{% if job.category == "leadership" %}
<h3>{{ job.title }} &nbsp;·&nbsp; {% if job.org_url %}<a href="{{ job.org_url }}">{{ job.org }}</a>{% else %}{{ job.org }}{% endif %} &nbsp; <em>({{ job.date_range }})</em></h3>
<ul>
{% for b in job.bullets %}<li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines | strip }}</li>
{% endfor %}</ul>
{% endif %}{% endfor %}

Talks and Volunteering
======
* **Coding Camp Organizer** &nbsp;·&nbsp; *Camp QMIND, Queen's University* &nbsp; *(2024)* — competitive event director, introducing and helping manage 90+ students in a pitch-style competitive coding and research event for a PhD panel of judges.
* **Workshop Host** &nbsp;·&nbsp; *QMIND Summer Workshops, Queen's University* &nbsp; *(2024)* — presented a guide to CI/CD and version management to 40+ students.
* **Guest Speaker** &nbsp;·&nbsp; *Queen's Arts and Science Undergraduate Society — Professional Development Weekend* &nbsp; *(2023)* — presented LinkedIn-profile guidance to 20+ students.
* **Orientation Leader** &nbsp;·&nbsp; *Computing Student's Association, Queen's University* &nbsp; *(2021)* — one of 12 orientation leaders for the 2021 and 2022 computing cohorts.
* **First-Year Mentor** &nbsp;·&nbsp; *Computing Student's Association, Queen's University* &nbsp; *(2021)* — coached incoming first-year students through bi-weekly meetings on PD and general advice.

Technical Skills
======
* **Python ML stack** — PyTorch, scikit-learn, Pandas, HuggingFace
* **Model training & inference** — reinforcement/fine-tuning, LoRA, distributed inference across LLM, VLM, VLA, Diffusion, and CNN architectures (incl. ONNX)
* **Agentic and MCP stack** — Pydantic/AI/LangChain · FastAPI · OpenTelemetry/Logfire
* **Deep-learning architectures** — Transformers, Diffusion, Flow, LSTM, Mixture of Experts, GAN
* **DevOps and tooling** — Git/GitLab CI/CD, ONNX, JWT, production ML deployment, code review

Also [active in 6+ national hackathons](https://devpost.com/david-huangp9033) in AI and full-stack distributed computing.

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

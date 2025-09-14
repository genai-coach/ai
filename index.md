---
layout: default
title: "GenAI Coach"
---

<div class="hero">
  <h1>Professional AI training that actually ships</h1>
  <p>Hands-on courses and playbooks for teams adopting GenAI and agents.</p>
  <p>
    <a class="btn btn-primary" href="{{ '/courses/' | relative_url }}">Explore courses</a>
    <a class="btn btn-outline" href="{{ '/projects/' | relative_url }}">See projects</a>
  </p>
</div>

<div class="cards">
  <div class="card"><h3>Agentic workflows</h3><p>Build small, durable automations.</p></div>
  <div class="card"><h3>Practical ops</h3><p>Versioning, prompts, evals—without drama.</p></div>
  <div class="card"><h3>Exec-friendly</h3><p>Clear ROI, risk, and governance.</p></div>
</div>

## Quick start
```bash
git lfs install && git lfs pull
bundle install
bundle exec jekyll serve --host 0.0.0.0 --port 4000
# http://localhost:4000{{ site.baseurl }}
```
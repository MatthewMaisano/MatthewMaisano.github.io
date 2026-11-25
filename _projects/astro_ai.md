---
layout: project
title: AI applied to astrophysics.
description: Statistics, machine learning and neural networks on real and simulated astrophysical data — 20 notebooks with their results.
lede: "Twenty Python notebooks from the Astrostatistics and Machine Learning course at the University of Milano-Bicocca (Prof. Davide Gerosa): from Monte Carlo methods and Bayesian inference to clustering, classification and neural networks, applied to quasars, supernovae, black holes and gravitational waves."
kind: Machine learning · Data analysis
year: 2025
thumb: assets/img/thumbs/astro-ai.jpg
importance: 1
category: work
related_publications: false
github: https://github.com/MatthewMaisano/Astrostatistics-Laboratory
stack: [Python, scikit-learn, PyTorch, emcee, dynesty, astroML, NumPy, SciPy]
links:
  - label: View the code
    url: https://github.com/MatthewMaisano/Astrostatistics-Laboratory
    icon: fa-brands fa-github
    primary: true
highlights:
  - value: "20"
    label: notebooks, each with a plain-language summary of the result
  - value: "93.75%"
    label: accuracy of my neural network predicting gravitational-wave detectability
  - value: "≈ 98%"
    label: galaxies vs quasars classified from their colours
  - value: "235 : 1"
    label: Bayesian evidence for the burst model of a cosmic transient
---

Modern astrophysics produces far more data than anyone can look at by hand: millions of galaxies, thousands of gravitational-wave candidates, light curves of transient events. Each card below summarises **what problem I tackled** and **what came out of it**; the link opens the full notebook with code and plots.

{% for section in site.data.astro_ai %}

<h2>{{ section.name }}</h2>
<p class="nb-section-desc">{{ section.description }}</p>
<div class="nb-grid">
  {%- for nb in section.notebooks -%}
  <div class="nb-card">
    {%- if nb.img != "" -%}
    <a class="nb-card-img" href="{{ nb.img | relative_url }}" target="_blank" rel="noopener"><img src="{{ nb.img | relative_url }}" alt="{{ nb.title }} — result plot" loading="lazy"></a>
    {%- endif -%}
    <div class="nb-card-body">
      <div class="nb-card-head">
        <h3 class="nb-card-title">{{ nb.title }}</h3>
        <span class="nb-lecture">{{ nb.lecture }}</span>
      </div>
      <ul class="pj-chips">{% for tag in nb.tags %}<li>{{ tag }}</li>{% endfor %}</ul>
      <p>{{ nb.what }}</p>
      <p class="nb-result"><strong>Result.</strong> {{ nb.result }}</p>
      <div class="nb-links">
        <a href="{{ nb.url }}" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Open notebook</a>
        {%- for x in nb.extra -%}
        <a href="{{ x.url }}" target="_blank" rel="noopener">{{ x.title }}</a>
        {%- endfor -%}
      </div>
    </div>
  </div>
  {%- endfor -%}
</div>
{% endfor %}

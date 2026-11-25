---
layout: page
title: AI applied to astrophysics.
description: Statistics, machine learning and neural networks on real and simulated astrophysical data — 20 notebooks with their results.
img:
importance: 3
category: work
related_publications: false
github: https://github.com/MatthewMaisano/Astrostatistics-Laboratory
---

**Code: [github.com/MatthewMaisano/Astrostatistics-Laboratory](https://github.com/MatthewMaisano/Astrostatistics-Laboratory)**

**The idea.** Modern astrophysics produces far more data than anyone can look at by hand: millions of galaxies, thousands of gravitational-wave candidates, light curves of transient events. This collection gathers the exercises I solved during the _Astrostatistics and Machine Learning_ course at the University of Milano-Bicocca (Prof. Davide Gerosa), going from the basics of probability and Monte Carlo methods to Bayesian inference, unsupervised learning and neural networks. Each card below summarises, in plain words, **what problem I tackled** and **what came out of it**; the button opens the full Python notebook with code and plots.

**Tools.** Python · NumPy · SciPy · scikit-learn · PyTorch · emcee · dynesty · astroML · pandas · Matplotlib

<div class="astro-ai">
<style>
  .astro-section {
    margin-top: 2.5rem;
  }
  .astro-section h2 {
    margin-bottom: 0.2rem;
  }
  .astro-section .section-desc {
    color: var(--global-text-color-light);
    margin-bottom: 1rem;
  }
  .astro-card {
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  .astro-card .card-img-top {
    background: #fff;
    border-bottom: 1px solid var(--global-divider-color);
    object-fit: contain;
    height: 230px;
    width: 100%;
    padding: 0.4rem;
  }
  .astro-card .card-body {
    display: flex;
    flex-direction: column;
  }
  .astro-card .card-title {
    font-size: 1.15rem;
    font-weight: 600;
    margin-bottom: 0.4rem;
  }
  .astro-card .lecture {
    font-size: 0.75rem;
    color: var(--global-text-color-light);
    float: right;
  }
  .astro-card .astro-tag {
    display: inline-block;
    font-size: 0.72rem;
    padding: 0.1rem 0.5rem;
    margin: 0 0.25rem 0.4rem 0;
    border-radius: 1rem;
    border: 1px solid var(--global-theme-color);
    color: var(--global-theme-color);
  }
  .astro-card p {
    font-size: 0.92rem;
    margin-bottom: 0.6rem;
  }
  .astro-card .result {
    border-left: 3px solid var(--global-theme-color);
    padding-left: 0.6rem;
  }
  .astro-card .links {
    margin-top: auto;
    font-size: 0.85rem;
  }
  .astro-card .links a {
    margin-right: 0.8rem;
  }
</style>
{%- for section in site.data.astro_ai -%}

<div class="astro-section">
  <h2>{{ section.name }}</h2>
  <p class="section-desc">{{ section.description }}</p>
  <div class="row row-cols-1 row-cols-md-2">
    {%- for nb in section.notebooks -%}
      <div class="col mb-4">
        <div class="card astro-card hoverable">
          {%- if nb.img != "" -%}
            <a href="{{ nb.img | relative_url }}" target="_blank" rel="noopener">
              <img class="card-img-top" src="{{ nb.img | relative_url }}" alt="{{ nb.title }} — result plot" loading="lazy">
            </a>
          {%- endif -%}
          <div class="card-body">
            <div class="card-title">
              <span class="lecture">{{ nb.lecture }}</span>
              {{ nb.title }}
            </div>
            <div>
              {%- for tag in nb.tags -%}<span class="astro-tag">{{ tag }}</span>{%- endfor -%}
            </div>
            <p><strong>What I did.</strong> {{ nb.what }}</p>
            <p class="result"><strong>Result.</strong> {{ nb.result }}</p>
            <div class="links">
              <a href="{{ nb.url }}" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Open notebook</a>
              {%- for x in nb.extra -%}
                <a href="{{ x.url }}" target="_blank" rel="noopener">{{ x.title }}</a>
              {%- endfor -%}
            </div>
          </div>
        </div>
      </div>
    {%- endfor -%}
  </div>
</div>
{%- endfor %}
</div>

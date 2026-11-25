---
layout: project
title: Stats.
description: A single search bar that sends you straight to the official source for any statistic.
kind: Web app
year: 2026
thumb: assets/img/thumbs/stats.jpg
importance: 4
category: work
related_publications: false
stack: [HTML, CSS, JavaScript, Data indexing]
links:
  - label: Try the live demo
    url: /stats/
    icon: fa-solid fa-arrow-up-right-from-square
    primary: true
highlights:
  - value: "24"
    label: common statistics indexed, with English and Italian aliases
  - value: "9"
    label: official sources, from Istat and Eurostat to the IMF and FRED
  - value: "1 box"
    label: no menus or filters to dig through
---

## The idea

Every time you need a specific statistic — unemployment rate, inflation, GDP growth, life expectancy — you end up hunting through a different institutional website depending on the country or the topic: [Istat](https://www.istat.it/) for Italy, Eurostat for the EU, the OECD, the World Bank, the IMF, the UN… **Stats.** removes that friction: type the name of a statistic and get back a curated list of links to the primary sources where it is published, so you land on the right page instead of a generic search result.

<figure class="pj-figure">
  <a href="{{ '/stats/' | relative_url }}"><img src="{{ 'assets/img/thumbs/stats.jpg' | relative_url }}" alt="Stats. search interface" loading="lazy"></a>
  <figcaption>The live interface: one search box and the list of indexed sources.</figcaption>
</figure>

## How it works

<div class="pj-features">
  <div class="pj-feature"><strong>One search box</strong><p>No menus or filters to dig through first: just type what you are looking for.</p></div>
  <div class="pj-feature"><strong>Curated index</strong><p>Keywords, synonyms and translations are mapped to the official pages of national statistical offices and international bodies.</p></div>
  <div class="pj-feature"><strong>Straight to the source</strong><p>Results link out directly to the publisher, rather than hosting or re-publishing the data.</p></div>
</div>

## Why it's interesting to build

It's a small, self-contained project that touches on things I care about professionally: structuring and indexing data cleanly, designing a fast and simple search/matching layer, and thinking about how to present quantitative information so it's actually usable.

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Status</span>
Working v1: a curated index of 24 common statistics mapped to 9 official sources — Istat, Eurostat, OECD, the World Bank, the IMF, UN Data, FRED, Banca d'Italia and Trading Economics — plus a fallback that generates a live search link on every source for anything not yet in the list. **Next:** grow the index, and pull a few headline numbers in directly rather than only linking out.
</div>

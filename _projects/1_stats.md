---
layout: page
title: Stats.
description: A search bar that finds you the right official source for any statistic.
img:
importance: 1
category: work
related_publications: false
---

<div class="badge-planned" style="display:inline-block; padding: 2px 10px; border-radius: 12px; background:#f0ad4e; color:#000; font-size: 0.8rem; margin-bottom: 1rem;">
🚧 In progress — concept &amp; design phase
</div>

**The idea.** Every time you need a specific statistic — unemployment rate, inflation, GDP growth, life expectancy — you end up hunting through a different institutional website depending on the country or the topic: [ISTAT](https://www.istat.it/) for Italy, Eurostat for the EU, the OECD, the World Bank, the IMF, the UN... Stats. is a single search bar that removes that friction: type in the name of a statistic and get back a curated list of links to the primary sources where it is published and can be explored, so you land on the right page instead of a generic search result.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <strong>How it works</strong>
        <ul>
            <li>One search box, no menus or filters to dig through first</li>
            <li>A curated index maps statistic keywords (and their synonyms/translations) to the official source pages that publish them — national statistical offices as well as international bodies</li>
            <li>Results link out directly to the source, rather than hosting or re-publishing the data itself</li>
        </ul>
    </div>
</div>

**Why it's interesting to build.** It's a small, self-contained project that touches on things I care about professionally: structuring and indexing data cleanly, designing a fast and simple search/matching layer, and thinking about how to present quantitative information so it's actually usable.

**Status.** Currently in the design and data-source mapping phase — deciding which sources to index first (starting with Italian and major international statistical bodies) and how the search/matching should work. Code and a live demo will be linked here once available.

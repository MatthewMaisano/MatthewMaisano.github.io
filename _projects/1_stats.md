---
layout: page
title: Stats.
description: A search bar that finds you the right official source for any statistic.
img:
importance: 1
category: work
related_publications: false
---

**Live demo: [matthewmaisano.github.io/stats](/stats/)**

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

**Status.** Working v1: a curated index of 24 common statistics (with English/Italian aliases) mapped to 9 official sources — Istat, Eurostat, OECD, the World Bank, the IMF, UN Data, FRED, Banca d'Italia and Trading Economics — plus a fallback that generates a live search link on every source for anything not yet in the curated list. Next: grow the curated index, and look at pulling a few headline numbers in directly rather than only linking out.

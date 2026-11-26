---
layout: page
title: Projects
permalink: /projects/
description: Research, simulations and side projects — from black holes and lattice QCD to machine learning and small web tools.
nav: true
nav_order: 2
horizontal: false
---

<!-- pages/projects.md -->
{% assign sorted_projects = site.projects | sort: "importance" %}
<div class="pj-grid">
{% for project in sorted_projects %}
  {% include projects.liquid %}
{% endfor %}
</div>

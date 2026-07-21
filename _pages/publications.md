---
layout: default
permalink: /publications/
title: Publications
description: Publications by categories in reverse chronological order.
nav: true
nav_order: 2
---

<!-- Custom Clean Header -->
<div class="header-bar mb-4">
  <h1 class="header-title">Publications</h1>
  <p class="header-subtitle">Selected journal papers, conference proceedings, and preprints from WAVESLAB.</p>
</div>

<div class="publications">

  <!-- Interactive Search Bar for Publications -->
  {% include bib_search.liquid %}

  <!-- Jekyll-Scholar Auto-Generated Bibliography -->
  {% bibliography %}

</div>

<!-- Page-Specific Theme Link -->
<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
---
layout: page
title: Explainable AI for ECG-based Screening of Cardiomyopathies 
description: This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures associated with contrast-enhanced cardiac magnetic resonance imaging features.
img: assets/img/asugi.png
logo: true
external_link: https://asugi.sanita.fvg.it/it/schede/UniTS/index.html
importance: 1
category: work
preview: assets/img/news/asugi.png
project_tag: ecg-screening
---

This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures associated with cardiomyopathies, currently detectable only through contrast-enhanced cardiac magnetic resonance imaging. If successful, the project would provide a low-cost, non-invasive proxy based on routine ECG recordings to support early risk stratification and guide referral to specialised, more expensive and invasive diagnostic pathways only for patients with suspicious ECG profiles. The study is carried out in collaboration with ASUGI–Cattinara.

![Asugi]({{ 'assets/img/asugi.png' | relative_url }})

{% if page.external_link or page.redirect %}
  {% assign ext_url = page.external_link | default: page.redirect %}
  <div class="my-4">
    <a href="{{ ext_url }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-primary" style="background-color: #0f3460; border-color: #0f3460; font-weight: 600; padding: 0.4rem 1rem;">
      Visit External Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
    </a>
  </div>
{% endif %}

---

### Related Publications

<div class="publications">
{% assign has_papers = false %}
{% for entry in site.data.citations %}
  {% if entry.keywords contains page.project_tag or entry.tags contains page.project_tag or entry.project == page.project_tag %}
    {% assign has_papers = true %}
    {% reference entry.key %}
  {% endif %}
{% endfor %}
</div>

<style>
  .publications h2.bibliography,
  h2.references {
    display: none !important;
  }
</style>
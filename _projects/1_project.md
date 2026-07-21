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
related_publications:
  - sharifi2026waveslab
---

This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures associated with cardiomyopathies, currently detectable only through contrast-enhanced cardiac magnetic resonance imaging. If successful, the project would provide a low-cost, non-invasive proxy based on routine ECG recordings to support early risk stratification and guide referral to specialised, more expensive and invasive diagnostic pathways only for patients with suspicious ECG profiles. The study is carried out in collaboration with ASUGI–Cattinara.

![Asugi]({{ 'assets/img/asugi.png' | relative_url }})

<!-- don't modify the below part  -->

{% if page.external_link or page.redirect %}
  {% assign ext_url = page.external_link | default: page.redirect %}
  <div class="my-4">
    <a href="{{ ext_url }}" 
       target="_blank" 
       rel="noopener noreferrer" 
       class="btn btn-sm text-white fw-semibold rounded-2" 
       style="background-color: #0f3460; border: 1px solid #0f3460; padding: 0.35rem 0.85rem;">
      External Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
    </a>
  </div>
{% endif %}

---

### Related Publications

{% for key in page.related_publications %}
* {% reference key %}
{% endfor %}
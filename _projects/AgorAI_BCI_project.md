---
layout: page
title: Edge AI-enabled BCI for Speech Rehabilitation
description: Speech and language impairments following neurological damage, developmental conditions, or neurodegenerative diseases often require intensive and repeated rehabilitation. Although technology-based and home-based interventions are increasingly available, current approaches provide limited objective multimodal feedback (mostly a numerical score) and personalized real-time adaptation. Moreover, access to specialist rehabilitation services remains challenging in rural and resource-constrained settings. These limitations motivate the development of an affordable, privacy-preserving, real-time rehabilitation system deployable beyond clinical environments, enhanced by a local LLM providing personalized natural-language feedback. The expected impact is more accessible, personalized home rehabilitation and longitudinal monitoring, with sensitive data processed locally and reduced dependence on reliable connectivity.
img: assets/img/AgorAI_project_scheme.png
logo: true
external_link: https://www.agorai.it/en/agorai
importance: 1
category: work
preview: assets/img/AgorAI_project_scheme.png
---

The project starts on January, 1st 2027. More details to come..







<!-- don't modify the below part  -->

{% if page.external_link or page.redirect %}
  {% assign ext_url = page.external_link | default: page.redirect %}
  <div class="my-4">
    <a href="{{ ext_url }}" 
       target="_blank" 
       rel="noopener noreferrer" 
       class="btn btn-sm text-white fw-semibold rounded-2" 
       style="background-color: #cbd1d7; border: 1px solid #0f3460; padding: 0.35rem 0.85rem;">
      External Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
    </a>
  </div>
{% endif %}

---

### Related Publications

{% for key in page.related_publications %}
* {% reference key %}
{% endfor %}
---
layout: default
permalink: /collaborations/
title: Collaborations
description: Building interdisciplinary bridges across academic institutions, research hospitals, and industry leaders.
nav: true
nav_order: 8
---

<style>
  .collab-card {
    background: #ffffff;
    border-radius: 14px;
    border: 1px solid #e2e8f0 !important;
    padding: 1.75rem !important;
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .collab-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 24px rgba(15, 52, 96, 0.08) !important;
  }

  .collab-title {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.2rem;
    margin-bottom: 0.25rem;
  }

  .collab-department {
    color: #334155;
    font-weight: 500;
    font-size: 0.9rem;
  }

  .collab-institution {
    color: #0f3460;
    font-weight: 600;
    font-size: 0.95rem;
  }

  .collab-location {
    color: #64748b;
    font-size: 0.88rem;
  }

  .collab-address {
    color: #475569;
    font-size: 0.85rem;
    margin-top: 0.25rem;
  }

  .collab-social-icon {
    color: #0f3460 !important;
    font-size: 1.05rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border-radius: 50%;
    background-color: #f1f5f9;
    transition: all 0.2s ease;
    text-decoration: none !important;
  }

  .collab-social-icon:hover {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    transform: translateY(-2px) scale(1.05);
  }

  .collab-img-wrapper {
    width: 70px;
    height: 70px;
    min-width: 70px;
    border-radius: 50%;
    overflow: hidden;
    border: 3px solid #f1f5f9;
    box-shadow: 0 4px 10px rgba(15, 52, 96, 0.1);
  }

  .collab-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* Outline Toggle Button */
  .btn-collab-pub {
    background-color: transparent !important;
    color: #0f3460 !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.3rem 0.75rem;
    font-size: 0.82rem;
    display: inline-flex;
    align-items: center;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .btn-collab-pub:hover,
  .btn-collab-pub.active {
    background-color: #0f3460 !important;
    color: #ffffff !important;
  }

  /* Expandable Joint Publication Drawer */
  .collab-pub-box {
    display: none;
    background-color: #f8fafc;
    border: 1px solid #cbd5e1;
    border-left: 4px solid #0f3460;
    border-radius: 8px;
    padding: 0.85rem 1rem;
    margin-top: 0.75rem;
    font-size: 0.85rem;
    color: #1e293b;
  }

  .collab-pub-box.open {
    display: block;
  }

  .collab-pub-list {
    list-style: none !important;
    padding-left: 0 !important;
    margin: 0 !important;
  }

  .collab-pub-item {
    display: flex;
    align-items: flex-start;
    gap: 0.5rem;
  }

  .collab-pub-bullet {
    font-weight: 700;
    color: #0f3460;
    min-width: 0.85rem;
    flex-shrink: 0;
    line-height: 1.4;
  }

  /* Keep al-folio bib.liquid compact inside the drawer */
  .collab-pub-box .row {
    display: block !important;
    margin: 0 !important;
  }

  .collab-pub-box .abbr,
  .collab-pub-box .preview,
  .collab-pub-box .badges {
    display: none !important;
  }

  .collab-pub-box .col-sm-8,
  .collab-pub-box .col-sm-10 {
    width: 100% !important;
    max-width: 100% !important;
    padding: 0 !important;
  }

  .collab-pub-box .title {
    font-weight: 700 !important;
    color: #0f3460 !important;
    margin-bottom: 0.2rem !important;
  }

  .collab-pub-box .links a.btn {
    padding: 0.15rem 0.5rem !important;
    font-size: 0.75rem !important;
    margin-top: 0.35rem !important;
    border: 1px solid #0f3460 !important;
    color: #0f3460 !important;
    border-radius: 4px !important;
    text-decoration: none !important;
    display: inline-block !important;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Collaborations</h1>
  <p class="header-subtitle">Building interdisciplinary bridges across academic institutions, research hospitals, and industry leaders.</p>
</div>

<!-- 1. ACADEMIA SECTION -->
{% if site.data.collaborations.academia %}
  <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-graduation-cap me-2" style="color: #0f3460;"></i> Academia &amp; Universities
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for partner in site.data.collaborations.academia %}
      <div class="col">
        <div class="collab-card d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex justify-content-between align-items-start gap-3 mb-3">
              <div class="d-flex align-items-center gap-3">
                {% if partner.image and partner.image != "" %}
                  {% assign img_path = partner.image | prepend: 'assets/img/' %}
                  <div class="collab-img-wrapper">
                    <img src="{{ img_path | relative_url }}" class="collab-img" alt="{{ partner.name }}">
                  </div>
                {% endif %}
                <div>
                  <h3 class="collab-title mb-0">{{ partner.name }}</h3>
                  {% if partner.department and partner.department != "" %}
                    <div class="collab-department">{{ partner.department }}</div>
                  {% endif %}
                  <div class="collab-institution">{{ partner.institution }}</div>
                  {% if partner.location and partner.location != "" %}
                    <div class="collab-location"><i class="fa-solid fa-location-dot me-1"></i>{{ partner.location }}</div>
                  {% endif %}
                </div>
              </div>

              <!-- Contact & Social Icons Bar -->
              <div class="d-flex align-items-center gap-2 flex-wrap justify-content-end">
                {% if partner.website and partner.website != "" %}
                  <a href="{{ partner.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="collab-social-icon">
                    <i class="fa-solid fa-globe"></i>
                  </a>
                {% endif %}
                {% if partner.linkedin and partner.linkedin != "" %}
                  <a href="https://linkedin.com/in/{{ partner.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" class="collab-social-icon">
                    <i class="fa-brands fa-linkedin-in"></i>
                  </a>
                {% endif %}
                {% if partner.github and partner.github != "" %}
                  <a href="https://github.com/{{ partner.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="collab-social-icon">
                    <i class="fa-brands fa-github"></i>
                  </a>
                {% endif %}
                {% if partner.scholar and partner.scholar != "" %}
                  <a href="https://scholar.google.com/citations?user={{ partner.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" class="collab-social-icon">
                    <i class="fa-solid fa-graduation-cap"></i>
                  </a>
                {% endif %}
                {% if partner.email and partner.email != "" %}
                  <a href="mailto:{{ partner.email }}" title="Email" class="collab-social-icon">
                    <i class="fa-solid fa-envelope"></i>
                  </a>
                {% endif %}
                {% if partner.phone and partner.phone != "" %}
                  <a href="tel:{{ partner.phone }}" title="Phone: {{ partner.phone }}" class="collab-social-icon">
                    <i class="fa-solid fa-phone"></i>
                  </a>
                {% endif %}
              </div>
            </div>

            {% if partner.address and partner.address != "" %}
              <div class="collab-address mb-2">
                <i class="fa-solid fa-building-user me-1"></i> {{ partner.address }}
              </div>
            {% endif %}

            {% if partner.description and partner.description != "" %}
              <p class="text-secondary small mt-3 pt-2 border-top mb-0">{{ partner.description }}</p>
            {% endif %}
          </div>

          <!-- Joint Publications Toggle & Drawer -->
          {% if partner.related_publications and partner.related_publications.size > 0 %}
            <div class="pt-3 mt-3 border-top">
              <button type="button" class="btn-collab-pub" onclick="toggleCollabPub('acad-pub-{{ forloop.index }}', this)">
                <i class="fa-solid fa-book-bookmark me-1"></i>
                Joint Publication{% if partner.related_publications.size > 1 %}s ({{ partner.related_publications.size }}){% endif %}
                <i class="fa-solid fa-chevron-down fa-xs ms-2"></i>
              </button>

              <div id="acad-pub-{{ forloop.index }}" class="collab-pub-box">
                <ul class="collab-pub-list">
                  {% for key in partner.related_publications %}
                    {% assign clean_key = key | strip %}
                    <li class="collab-pub-item {% unless forloop.last %}mb-2 pb-2 border-bottom{% endunless %}">
                      <span class="collab-pub-bullet">&bull;</span>
                      <div class="flex-grow-1">
                        {% reference clean_key %}
                      </div>
                    </li>
                  {% endfor %}
                </ul>
              </div>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<!-- 2. CLINICAL & HOSPITALS SECTION -->
{% if site.data.collaborations.hospitals %}
  <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-hospital me-2" style="color: #0f3460;"></i> Clinical &amp; Research Hospitals
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for partner in site.data.collaborations.hospitals %}
      <div class="col">
        <div class="collab-card d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex justify-content-between align-items-start gap-3 mb-3">
              <div class="d-flex align-items-center gap-3">
                {% if partner.image and partner.image != "" %}
                  {% assign img_path = partner.image | prepend: 'assets/img/' %}
                  <div class="collab-img-wrapper">
                    <img src="{{ img_path | relative_url }}" class="collab-img" alt="{{ partner.name }}">
                  </div>
                {% endif %}
                <div>
                  <h3 class="collab-title mb-0">{{ partner.name }}</h3>
                  {% if partner.department and partner.department != "" %}
                    <div class="collab-department">{{ partner.department }}</div>
                  {% endif %}
                  <div class="collab-institution">{{ partner.institution }}</div>
                  {% if partner.location and partner.location != "" %}
                    <div class="collab-location"><i class="fa-solid fa-location-dot me-1"></i>{{ partner.location }}</div>
                  {% endif %}
                </div>
              </div>

              <!-- Contact & Social Icons Bar -->
              <div class="d-flex align-items-center gap-2 flex-wrap justify-content-end">
                {% if partner.website and partner.website != "" %}
                  <a href="{{ partner.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="collab-social-icon">
                    <i class="fa-solid fa-globe"></i>
                  </a>
                {% endif %}
                {% if partner.linkedin and partner.linkedin != "" %}
                  <a href="https://linkedin.com/in/{{ partner.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" class="collab-social-icon">
                    <i class="fa-brands fa-linkedin-in"></i>
                  </a>
                {% endif %}
                {% if partner.github and partner.github != "" %}
                  <a href="https://github.com/{{ partner.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="collab-social-icon">
                    <i class="fa-brands fa-github"></i>
                  </a>
                {% endif %}
                {% if partner.scholar and partner.scholar != "" %}
                  <a href="https://scholar.google.com/citations?user={{ partner.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" class="collab-social-icon">
                    <i class="fa-solid fa-graduation-cap"></i>
                  </a>
                {% endif %}
                {% if partner.email and partner.email != "" %}
                  <a href="mailto:{{ partner.email }}" title="Email" class="collab-social-icon">
                    <i class="fa-solid fa-envelope"></i>
                  </a>
                {% endif %}
                {% if partner.phone and partner.phone != "" %}
                  <a href="tel:{{ partner.phone }}" title="Phone: {{ partner.phone }}" class="collab-social-icon">
                    <i class="fa-solid fa-phone"></i>
                  </a>
                {% endif %}
              </div>
            </div>

            {% if partner.address and partner.address != "" %}
              <div class="collab-address mb-2">
                <i class="fa-solid fa-building-user me-1"></i> {{ partner.address }}
              </div>
            {% endif %}

            {% if partner.description and partner.description != "" %}
              <p class="text-secondary small mt-3 pt-2 border-top mb-0">{{ partner.description }}</p>
            {% endif %}
          </div>

          <!-- Joint Publications Toggle & Drawer -->
          {% if partner.related_publications and partner.related_publications.size > 0 %}
            <div class="pt-3 mt-3 border-top">
              <button type="button" class="btn-collab-pub" onclick="toggleCollabPub('hosp-pub-{{ forloop.index }}', this)">
                <i class="fa-solid fa-book-bookmark me-1"></i>
                Joint Publication{% if partner.related_publications.size > 1 %}s ({{ partner.related_publications.size }}){% endif %}
                <i class="fa-solid fa-chevron-down fa-xs ms-2"></i>
              </button>

              <div id="hosp-pub-{{ forloop.index }}" class="collab-pub-box">
                <ul class="collab-pub-list">
                  {% for key in partner.related_publications %}
                    {% assign clean_key = key | strip %}
                    <li class="collab-pub-item {% unless forloop.last %}mb-2 pb-2 border-bottom{% endunless %}">
                      <span class="collab-pub-bullet">&bull;</span>
                      <div class="flex-grow-1">
                        {% reference clean_key %}
                      </div>
                    </li>
                  {% endfor %}
                </ul>
              </div>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<!-- 3. INDUSTRY PARTNERS SECTION -->
{% if site.data.collaborations.companies %}
  <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-building me-2" style="color: #0f3460;"></i> Industry &amp; Corporate Partners
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for partner in site.data.collaborations.companies %}
      <div class="col">
        <div class="collab-card d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex justify-content-between align-items-start gap-3 mb-3">
              <div class="d-flex align-items-center gap-3">
                {% if partner.image and partner.image != "" %}
                  {% assign img_path = partner.image | prepend: 'assets/img/' %}
                  <div class="collab-img-wrapper">
                    <img src="{{ img_path | relative_url }}" class="collab-img" alt="{{ partner.name }}">
                  </div>
                {% endif %}
                <div>
                  <h3 class="collab-title mb-0">{{ partner.name }}</h3>
                  {% if partner.department and partner.department != "" %}
                    <div class="collab-department">{{ partner.department }}</div>
                  {% endif %}
                  <div class="collab-institution">{{ partner.institution }}</div>
                  {% if partner.location and partner.location != "" %}
                    <div class="collab-location"><i class="fa-solid fa-location-dot me-1"></i>{{ partner.location }}</div>
                  {% endif %}
                </div>
              </div>

              <!-- Contact & Social Icons Bar -->
              <div class="d-flex align-items-center gap-2 flex-wrap justify-content-end">
                {% if partner.website and partner.website != "" %}
                  <a href="{{ partner.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="collab-social-icon">
                    <i class="fa-solid fa-globe"></i>
                  </a>
                {% endif %}
                {% if partner.linkedin and partner.linkedin != "" %}
                  <a href="https://linkedin.com/in/{{ partner.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" class="collab-social-icon">
                    <i class="fa-brands fa-linkedin-in"></i>
                  </a>
                {% endif %}
                {% if partner.github and partner.github != "" %}
                  <a href="https://github.com/{{ partner.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="collab-social-icon">
                    <i class="fa-brands fa-github"></i>
                  </a>
                {% endif %}
                {% if partner.scholar and partner.scholar != "" %}
                  <a href="https://scholar.google.com/citations?user={{ partner.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" class="collab-social-icon">
                    <i class="fa-solid fa-graduation-cap"></i>
                  </a>
                {% endif %}
                {% if partner.email and partner.email != "" %}
                  <a href="mailto:{{ partner.email }}" title="Email" class="collab-social-icon">
                    <i class="fa-solid fa-envelope"></i>
                  </a>
                {% endif %}
                {% if partner.phone and partner.phone != "" %}
                  <a href="tel:{{ partner.phone }}" title="Phone: {{ partner.phone }}" class="collab-social-icon">
                    <i class="fa-solid fa-phone"></i>
                  </a>
                {% endif %}
              </div>
            </div>

            {% if partner.address and partner.address != "" %}
              <div class="collab-address mb-2">
                <i class="fa-solid fa-building-user me-1"></i> {{ partner.address }}
              </div>
            {% endif %}

            {% if partner.description and partner.description != "" %}
              <p class="text-secondary small mt-3 pt-2 border-top mb-0">{{ partner.description }}</p>
            {% endif %}
          </div>

          <!-- Joint Publications Toggle & Drawer -->
          {% if partner.related_publications and partner.related_publications.size > 0 %}
            <div class="pt-3 mt-3 border-top">
              <button type="button" class="btn-collab-pub" onclick="toggleCollabPub('comp-pub-{{ forloop.index }}', this)">
                <i class="fa-solid fa-book-bookmark me-1"></i>
                Joint Publication{% if partner.related_publications.size > 1 %}s ({{ partner.related_publications.size }}){% endif %}
                <i class="fa-solid fa-chevron-down fa-xs ms-2"></i>
              </button>

              <div id="comp-pub-{{ forloop.index }}" class="collab-pub-box">
                <ul class="collab-pub-list">
                  {% for key in partner.related_publications %}
                    {% assign clean_key = key | strip %}
                    <li class="collab-pub-item {% unless forloop.last %}mb-2 pb-2 border-bottom{% endunless %}">
                      <span class="collab-pub-bullet">&bull;</span>
                      <div class="flex-grow-1">
                        {% reference clean_key %}
                      </div>
                    </li>
                  {% endfor %}
                </ul>
              </div>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<script>
  function toggleCollabPub(boxId, btn) {
    const box = document.getElementById(boxId);
    if (!box) return;
    box.classList.toggle('open');
    btn.classList.toggle('active');
    const icon = btn.querySelector('.fa-chevron-down, .fa-chevron-up');
    if (icon) {
      icon.classList.toggle('fa-chevron-down');
      icon.classList.toggle('fa-chevron-up');
    }
  }
</script>

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
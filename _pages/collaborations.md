---
layout: default
permalink: /collaborations/
title: Collaborations
description: Academic, clinical, and industrial partners collaborating with WAVESLAB.
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
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Collaborations</h1>
  <p class="header-subtitle">Building interdisciplinary bridges across academic institutions, research hospitals, and industry leaders.</p>
</div>

{% assign sections = "academia|Academia & Universities|fa-graduation-cap,hospitals|Clinical & Research Hospitals|fa-hospital,companies|Industry & Corporate Partners|fa-building" | split: "," %}

{% for sec in sections %}
  {% assign sec_parts = sec | split: "|" %}
  {% assign key = sec_parts[0] %}
  {% assign title = sec_parts[1] %}
  {% assign icon = sec_parts[2] %}
  {% assign partners = site.data.collaborations[key] %}

  {% if partners %}
    <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
      <i class="fa-solid {{ icon }} me-2" style="color: #0f3460;"></i> {{ title }}
    </h2>

    <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
      {% for partner in partners %}
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

              <!-- Address Details if specified -->
              {% if partner.address and partner.address != "" %}
                <div class="collab-address mb-2">
                  <i class="fa-solid fa-building-user me-1"></i> {{ partner.address }}
                </div>
              {% endif %}

              <!-- Collaboration Focus / Description -->
              {% if partner.description and partner.description != "" %}
                <p class="text-secondary small mt-3 pt-2 border-top mb-0">{{ partner.description }}</p>
              {% endif %}
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% endif %}
{% endfor %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
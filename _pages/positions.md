---
layout: default
permalink: /Join us/
title: Open Positions & Theses
description: Join WAVESLAB as a Ph.D. researcher, Postdoc, or Master/Bachelor thesis student.
nav: true
nav_order: 9
---

<style>
  .pos-card {
    background: #ffffff;
    border-radius: 14px;
    border: 1px solid #e2e8f0 !important;
    padding: 1.75rem !important;
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .pos-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 24px rgba(15, 52, 96, 0.08) !important;
  }

  .pos-title {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.25rem;
    margin-bottom: 0.3rem;
  }

  .badge-open {
    background-color: #dcfce7;
    color: #166534;
    font-weight: 600;
    font-size: 0.8rem;
    padding: 0.3rem 0.75rem;
    border-radius: 20px;
    border: 1px solid #bbf7d0;
  }

  .badge-tag {
    background-color: #f1f5f9;
    color: #0f3460;
    font-weight: 600;
    font-size: 0.8rem;
    padding: 0.25rem 0.65rem;
    border-radius: 6px;
    border: 1px solid #cbd5e1;
  }

  .apply-box {
    background: #f8fafc;
    border-left: 4px solid #0f3460;
    border-radius: 8px;
    padding: 1.5rem;
  }

  .btn-apply {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    font-weight: 600;
    padding: 0.4rem 1rem;
    border-radius: 6px;
    text-decoration: none !important;
    display: inline-block;
    transition: background-color 0.2s ease;
  }

  .btn-apply:hover {
    background-color: #16213e !important;
    color: #ffffff !important;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Open Positions & Thesis Topics</h1>
  <p class="header-subtitle">Explore research opportunities, Ph.D./Postdoc openings, and Bachelor/Master thesis projects at WAVESLAB.</p>
</div>

<!-- Application Guidelines Banner -->
{% if site.data.positions.application_info %}
  <div class="apply-box mb-5 shadow-sm">
    <div class="d-flex flex-column flex-md-row justify-content-between align-items-md-center gap-3">
      <div>
        <h4 class="mb-1" style="color: #0f3460; font-weight: 700;">Interested in Joining WAVESLAB?</h4>
        <p class="text-secondary small mb-2">We welcome passionate students and researchers with backgrounds in Biomedical Engineering, Data Science, Electrical Engineering, or Computer Science.</p>
        
        <div class="small text-muted">
          <strong>To apply, please email:</strong>
          {% if site.data.positions.application_info.requirements %}
            <ul>
              {% for req in site.data.positions.application_info.requirements %}
                <li>{{ req }}</li>
              {% endfor %}
            </ul>
          {% endif %}
        </div>
      </div>

      <div>
        <a href="mailto:{{ site.data.positions.application_info.email }}?subject=WAVESLAB%20Application" class="btn-apply text-nowrap">
          Submit Application <i class="fa-solid fa-paper-plane ms-1"></i>
        </a>
      </div>
    </div>
  </div>
{% endif %}

<!-- 1. OPEN RESEARCH ROLES (Ph.D., Postdoc, Fellowships) -->
{% if site.data.positions.open_roles %}
  <h2 class="mt-4 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-briefcase me-2" style="color: #0f3460;"></i> Open Research Positions
  </h2>

  <div class="row row-cols-1 g-4 mb-5">
    {% for role in site.data.positions.open_roles %}
      <div class="col">
        <div class="pos-card">
          <div class="d-flex flex-column flex-md-row justify-content-between align-items-md-start gap-2 mb-3">
            <div>
              <div class="d-flex align-items-center gap-2 mb-1">
                <span class="badge-tag">{{ role.type }}</span>
                {% if role.status == "Open" %}
                  <span class="badge-open"><i class="fa-solid fa-circle-dot me-1"></i> {{ role.status }}</span>
                {% endif %}
              </div>
              <h3 class="pos-title mt-2">{{ role.title }}</h3>
            </div>

            <div class="text-secondary small text-md-end">
              {% if role.location %}<div><i class="fa-solid fa-location-dot me-1"></i> {{ role.location }}</div>{% endif %}
              {% if role.deadline %}<div><i class="fa-solid fa-clock me-1"></i> Deadline: {{ role.deadline }}</div>{% endif %}
            </div>
          </div>

          <p class="text-secondary small mb-3">{{ role.description }}</p>

          {% if role.requirements %}
            <div class="pt-2 border-top">
              <strong class="small text-dark">Key Requirements:</strong>
              <ul class="small text-secondary mb-0 mt-1">
                {% for req in role.requirements %}
                  <li>{{ req }}</li>
                {% endfor %}
              </ul>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<!-- 2. AVAILABLE THESIS TOPICS -->
{% if site.data.positions.thesis_topics %}
  <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-book-open-reader me-2" style="color: #0f3460;"></i> Available Thesis Opportunities
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for thesis in site.data.positions.thesis_topics %}
      <div class="col">
        <div class="pos-card d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <span class="badge-tag">{{ thesis.level }}</span>
            </div>

            <h3 class="pos-title">{{ thesis.title }}</h3>

            {% if thesis.advisor %}
              <div class="small text-muted mb-2">
                <i class="fa-solid fa-user-graduate me-1"></i> <strong>Advisor:</strong> {{ thesis.advisor }}
              </div>
            {% endif %}

            <p class="text-secondary small mb-3">{{ thesis.description }}</p>
          </div>

          {% if thesis.prerequisites %}
            <div class="pt-2 border-top mt-2">
              <span class="small text-muted"><strong>Prerequisites:</strong> {{ thesis.prerequisites }}</span>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
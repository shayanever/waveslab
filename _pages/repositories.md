---
layout: default
permalink: /repositories/
title: repositories
description: Open-source code, toolboxes, and software packages developed by WAVESLAB.
nav: true
nav_order: 4
---

<div class="header-bar mb-4">
  <h1 class="header-title">Repositories</h1>
  <p class="header-subtitle">Open-source code, toolboxes, and software packages developed at WAVESLAB.</p>
</div>

{% if site.data.repositories.github_users %}
  <h2 class="mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    GitHub Organization & Profiles
  </h2>

  <div class="repositories row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for user in site.data.repositories.github_users %}
      <div class="col">
        {% include repository/repo_user.liquid username=user %}
      </div>
    {% endfor %}
  </div>

  {% if site.repo_trophies.enabled %}
    {% for user in site.data.repositories.github_users %}
      {% if site.data.repositories.github_users.size > 1 %}
        <h4 class="mt-4 mb-3">{{ user }}</h4>
      {% endif %}
      <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center mb-4">
        {% include repository/repo_trophies.liquid username=user %}
      </div>
    {% endfor %}
  {% endif %}
{% endif %}

{% if site.data.repositories.github_repos %}
  <h2 class="mt-5 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    Featured Repositories
  </h2>

  <div class="repositories row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for item in site.data.repositories.github_repos %}
      {% if item.repo %}
        {% assign repo_path = item.repo %}
        {% assign pub_keys = item.related_publications %}
      {% else %}
        {% assign repo_path = item %}
        {% assign pub_keys = nil %}
      {% endif %}

      <div class="col d-flex flex-column justify-content-between align-items-start">
        <div class="w-100">
          {% include repository/repo.liquid repository=repo_path %}
        </div>
        
        <!-- Related Publications Link for Repository -->
        {% if pub_keys %}
          <div class="mt-2 ms-1">
            {% for key in pub_keys %}
              <a href="{{ '/publications/' | relative_url }}#{{ key }}" class="btn btn-sm btn-theme-outline" style="border: 1px solid #0f3460; color: #0f3460; border-radius: 6px; padding: 0.25rem 0.65rem; font-size: 0.85rem; text-decoration: none;">
                Related Publication <i class="fa-solid fa-book-bookmark fa-xs ms-1"></i>
              </a>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
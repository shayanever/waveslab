---
layout: default
permalink: /repositories/
title: repositories
description: Open-source code, toolboxes, and software packages developed by WAVESLAB.
nav: true
nav_order: 4
---

<style>
  .btn-theme-outline {
    background-color: transparent !important;
    color: #0f3460 !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.3rem 0.75rem;
    font-size: 0.85rem;
    text-decoration: none !important;
    display: inline-block;
  }

  .btn-theme-outline:hover {
    background-color: #0f3460 !important;
    color: #ffffff !important;
  }

  .repo-item {
    margin-bottom: 2rem;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Repositories</h1>
  <p class="header-subtitle">Open-source code, toolboxes, and software packages developed at WAVESLAB.</p>
</div>

{% if site.data.repositories.github_users %}
  <h2 class="mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    GitHub Profiles
  </h2>

  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center mb-5">
    {% for user in site.data.repositories.github_users %}
      {% include repository/repo_user.liquid username=user %}
    {% endfor %}
  </div>
{% endif %}

{% if site.data.repositories.github_repos %}
  <h2 class="mt-5 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    Featured Repositories
  </h2>

  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center mb-5">
    {% for item in site.data.repositories.github_repos %}
      {% if item.repo %}
        {% assign repo_path = item.repo %}
        {% assign pub_keys = item.related_publications %}
      {% else %}
        {% assign repo_path = item %}
        {% assign pub_keys = nil %}
      {% endif %}

      <div class="repo-item w-100" style="max-width: 480px;">
        {% include repository/repo.liquid repository=repo_path %}
        
        {% if pub_keys %}
          <div class="mt-2 ms-1">
            {% for key in pub_keys %}
              <a href="{{ '/publications/' | relative_url }}#{{ key }}" class="btn-theme-outline">
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
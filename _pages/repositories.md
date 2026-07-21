---
layout: default
permalink: /repositories/
title: Repos
description: Open-source code, toolboxes, and software packages developed by WAVESLAB.
nav: true
nav_order: 4
---

<style>
  .repo-card {
    background: #ffffff;
    border-radius: 12px;
    border: 1px solid #e2e8f0 !important;
    padding: 1.25rem;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .repo-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(15, 52, 96, 0.08) !important;
  }

  .repo-title {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.15rem;
    text-decoration: none !important;
  }

  .repo-title:hover {
    color: #16213e !important;
    text-decoration: underline !important;
  }

  /* Primary Button (Solid Dark Blue) */
  .btn-theme-primary {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.3rem 0.75rem;
    font-size: 0.85rem;
    text-decoration: none !important;
    display: inline-block;
  }

  .btn-theme-primary:hover {
    background-color: #16213e !important;
    color: #ffffff !important;
  }

  /* Outline Button */
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

  .user-badge {
    background-color: #f1f5f9;
    border: 1px solid #cbd5e1;
    border-radius: 20px;
    padding: 0.4rem 1rem;
    font-weight: 600;
    color: #0f172a;
    text-decoration: none !important;
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .user-badge:hover {
    background-color: #e2e8f0;
    color: #0f3460;
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

  <div class="d-flex flex-wrap gap-2 mb-5">
    {% for user in site.data.repositories.github_users %}
      <a href="https://github.com/{{ user }}" target="_blank" rel="noopener noreferrer" class="user-badge">
        <i class="fa-brands fa-github"></i> @{{ user }}
      </a>
    {% endfor %}
  </div>
{% endif %}

{% if site.data.repositories.github_repos %}
  <h2 class="mt-4 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    Featured Repositories
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for item in site.data.repositories.github_repos %}
      {% if item.name %}
        {% assign repo_user = item.user %}
        {% assign repo_name = item.name %}
        {% assign repo_desc = item.description %}
        {% assign pub_keys = item.related_publications %}
      {% else %}
        {% assign parts = item | split: "/" %}
        {% assign repo_user = parts[0] %}
        {% assign repo_name = parts[1] %}
        {% assign repo_desc = "" %}
        {% assign pub_keys = nil %}
      {% endif %}

      <div class="col d-flex align-items-stretch">
        <div class="repo-card w-100 d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex align-items-center justify-content-between mb-2">
              <a href="https://github.com/{{ repo_user }}/{{ repo_name }}" target="_blank" rel="noopener noreferrer" class="repo-title">
                <i class="fa-solid fa-book-bookmark me-1"></i> {{ repo_user }}/{{ repo_name }}
              </a>
              <a href="https://github.com/{{ repo_user }}/{{ repo_name }}" target="_blank" rel="noopener noreferrer" class="text-secondary small">
                <i class="fa-brands fa-github fa-lg"></i>
              </a>
            </div>

            {% if repo_desc != "" %}
              <p class="text-secondary small mb-3">{{ repo_desc }}</p>
            {% endif %}
          </div>

          <!-- Buttons Container -->
          <div class="pt-2 mt-2 border-top d-flex flex-wrap gap-2">
            <!-- GitHub Repository Direct Link Button -->
            <a href="https://github.com/{{ repo_user }}/{{ repo_name }}" target="_blank" rel="noopener noreferrer" class="btn-theme-primary">
              View Repository <i class="fa-brands fa-github fa-xs ms-1"></i>
            </a>

            <!-- Related Publication Buttons -->
            {% if pub_keys %}
              {% for key in pub_keys %}
                <a href="{{ '/publications/' | relative_url }}#{{ key }}" class="btn-theme-outline">
                  Related Publication <i class="fa-solid fa-book-bookmark fa-xs ms-1"></i>
                </a>
              {% endfor %}
            {% endif %}
          </div>

        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
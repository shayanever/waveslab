---
layout: default
title: projects
permalink: /projects/
description: A growing collection of research initiatives and active projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<style>
  .project-card {
    background: #ffffff;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid #e2e8f0 !important;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    cursor: pointer;
  }

  .project-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(15, 52, 96, 0.08) !important;
  }

  .project-card .card-title {
    color: var(--global-theme-color, #0f3460) !important;
  }

  /* Overlay link to make the entire card box clickable */
  .project-card-link {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
  }

  /* Primary Theme Button (Solid Dark Blue) */
  .btn-theme-primary {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.35rem 0.85rem;
  }

  .btn-theme-primary:hover {
    background-color: #16213e !important;
    color: #ffffff !important;
  }

  /* Secondary Theme Button (Outline Dark Blue) */
  .btn-theme-outline {
    background-color: transparent !important;
    color: #0f3460 !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.35rem 0.85rem;
  }

  .btn-theme-outline:hover {
    background-color: #0f3460 !important;
    color: #ffffff !important;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Projects</h1>
  <p class="header-subtitle">Active research initiatives, tools, and ongoing studies at WAVESLAB.</p>
</div>

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Categorized Projects Loop -->
  {% for category in page.display_categories %}
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% if categorized_projects.size > 0 %}
    <a id="{{ category }}" href=".#{{ category }}">
      <h2 class="category mt-4 mb-3" style="text-transform: capitalize; color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">{{ category }}</h2>
    </a>
    {% assign sorted_projects = categorized_projects | sort: "importance" %}
    
    <div class="row row-cols-1 g-4 mb-5">
      {% for project in sorted_projects %}
        <div class="col">
          <div class="card project-card h-100 shadow-sm border-0 position-relative">
            
            <!-- Full Overlay Link pointing to Internal Project Details Page -->
            <a href="{{ project.url | relative_url }}" class="project-card-link" aria-label="{{ project.title }}"></a>

            <div class="row g-0 align-items-center">
              {% if project.img %}
                {% if project.logo %}
                  <!-- Logo Layout: Centered with padding & light background -->
                  <div class="col-md-4 p-4 text-center d-flex align-items-center justify-content-center" style="background-color: #f8fafc; border-top-left-radius: 12px; border-bottom-left-radius: 12px; min-height: 200px;">
                    <img src="{{ project.img | relative_url }}" class="img-fluid" alt="{{ project.title }}" style="max-height: 160px; object-fit: contain;">
                  </div>
                {% else %}
                  <!-- Photo Layout: Full-bleed cover image -->
                  <div class="col-md-4 overflow-hidden h-100" style="min-height: 220px;">
                    <img src="{{ project.img | relative_url }}" class="img-fluid w-100 h-100" alt="{{ project.title }}" style="object-fit: cover; border-top-left-radius: 12px; border-bottom-left-radius: 12px;">
                  </div>
                {% endif %}
                <div class="col-md-8">
              {% else %}
                <div class="col-md-12">
              {% endif %}
                <div class="card-body p-4">
                  <h3 class="card-title font-weight-bold mb-2" style="font-size: 1.35rem;">
                    {{ project.title }}
                  </h3>
                  <p class="card-text text-secondary my-3">{{ project.description }}</p>
                  
                  <div class="d-flex align-items-center flex-wrap gap-2 mt-3" style="gap: 10px; position: relative; z-index: 10;">
                    <!-- Read Details Button -->
                    <a href="{{ project.url | relative_url }}" class="btn btn-sm btn-theme-outline">
                      Read Details
                    </a>

                    <!-- Optional External Link Button -->
                    {% if project.redirect %}
                    <a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-theme-primary">
                      External Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
                    </a>
                    {% endif %}

                    <!-- Optional Related Publications Anchor Jump Button -->
                    {% if project.related_publications %}
                    <a href="{{ '/publications/' | relative_url }}#{{ project.related_publications }}" class="btn btn-sm btn-theme-outline">
                      Related Publications <i class="fa-solid fa-book-bookmark fa-xs ms-1"></i>
                    </a>
                    {% endif %}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  {% endif %}
  {% endfor %}

{% else %}

  <!-- Uncategorized Projects Fallback Loop -->
  {% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="row row-cols-1 g-4 mb-5">
    {% for project in sorted_projects %}
      <div class="col">
        <div class="card project-card h-100 shadow-sm border-0 position-relative">
          
          <!-- Full Overlay Link -->
          <a href="{{ project.url | relative_url }}" class="project-card-link" aria-label="{{ project.title }}"></a>

          <div class="row g-0 align-items-center">
            {% if project.img %}
              {% if project.logo %}
                <div class="col-md-4 p-4 text-center d-flex align-items-center justify-content-center" style="background-color: #f8fafc; border-top-left-radius: 12px; border-bottom-left-radius: 12px; min-height: 200px;">
                  <img src="{{ project.img | relative_url }}" class="img-fluid" alt="{{ project.title }}" style="max-height: 160px; object-fit: contain;">
                </div>
              {% else %}
                <div class="col-md-4 overflow-hidden h-100" style="min-height: 220px;">
                  <img src="{{ project.img | relative_url }}" class="img-fluid w-100 h-100" alt="{{ project.title }}" style="object-fit: cover; border-top-left-radius: 12px; border-bottom-left-radius: 12px;">
                </div>
              {% endif %}
              <div class="col-md-8">
            {% else %}
              <div class="col-md-12">
            {% endif %}
              <div class="card-body p-4">
                <h3 class="card-title font-weight-bold mb-2" style="font-size: 1.35rem;">
                  {{ project.title }}
                </h3>
                <p class="card-text text-secondary my-3">{{ project.description }}</p>
                
                <div class="d-flex align-items-center flex-wrap gap-2 mt-3" style="gap: 10px; position: relative; z-index: 10;">
                  <a href="{{ project.url | relative_url }}" class="btn btn-sm btn-theme-outline">
                    Read Details
                  </a>

                  {% if project.redirect %}
                  <a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-theme-primary">
                    External Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
                  </a>
                  {% endif %}

                  {% if project.related_publications %}
                  <a href="{{ '/publications/' | relative_url }}#{{ project.related_publications }}" class="btn btn-sm btn-theme-outline">
                    Related Publications <i class="fa-solid fa-book-bookmark fa-xs ms-1"></i>
                  </a>
                  {% endif %}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}
</div>

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
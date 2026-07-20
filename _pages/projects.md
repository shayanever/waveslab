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

<div class="header-bar mb-4">
  <h1 class="header-title">Projects</h1>
  <p class="header-subtitle">Active research initiatives, tools, and ongoing studies at WAVESLAB.</p>
</div>

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Categorized Projects -->
  {% for category in page.display_categories %}
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% if categorized_projects.size > 0 %}
    <a id="{{ category }}" href=".#{{ category }}">
      <h2 class="category mt-4 mb-3" style="text-transform: capitalize; color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">{{ category }}</h2>
    </a>
    {% assign sorted_projects = categorized_projects | sort: "importance" %}
    
    <!-- Forces 1 project per column/row -->
    <div class="row row-cols-1 g-4 mb-5">
      {% for project in sorted_projects %}
        <div class="col">
          <div class="card h-100 shadow-sm border-0 position-relative hoverable" style="background: #ffffff; border-radius: 12px; overflow: hidden; border: 1px solid #e2e8f0 !important; transition: transform 0.2s ease, box-shadow 0.2s ease;">
            
            <!-- Entire Card Clickable Area -> Internal Project Page -->
            <a href="{{ project.url | relative_url }}" class="text-decoration-none text-reset stretched-link"></a>

            <div class="row g-0 align-items-center">
              {% if project.img %}
              <div class="col-md-4 p-3 text-center" style="z-index: 1;">
                <img src="{{ project.img | relative_url }}" class="img-fluid rounded" alt="{{ project.title }}" style="max-height: 220px; object-fit: contain;">
              </div>
              <div class="col-md-8">
              {% else %}
              <div class="col-md-12">
              {% endif %}
                <div class="card-body p-4">
                  <h3 class="card-title font-weight-bold" style="color: #0f172a; font-size: 1.35rem;">{{ project.title }}</h3>
                  <p class="card-text text-secondary my-3">{{ project.description }}</p>
                  
                  <div class="d-flex align-items-center gap-2 mt-3" style="gap: 10px; position: relative; z-index: 2;">
                    <!-- Read Details Tag -->
                    <span class="btn btn-sm btn-outline-primary" style="font-weight: 600; border-radius: 6px; pointer-events: none;">
                      Read Details
                    </span>

                    <!-- External Link / Read More button (clicks independently to external URL) -->
                    {% if project.redirect %}
                    <a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-primary" style="background-color: #0f3460; border-color: #0f3460; font-weight: 600; border-radius: 6px;">
                      Read More <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
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

  <!-- Uncategorized Projects -->
  {% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="row row-cols-1 g-4 mb-5">
    {% for project in sorted_projects %}
      <div class="col">
        <div class="card h-100 shadow-sm border-0 position-relative hoverable" style="background: #ffffff; border-radius: 12px; overflow: hidden; border: 1px solid #e2e8f0 !important; transition: transform 0.2s ease, box-shadow 0.2s ease;">
          
          <!-- Entire Card Clickable Area -> Internal Project Page -->
          <a href="{{ project.url | relative_url }}" class="text-decoration-none text-reset stretched-link"></a>

          <div class="row g-0 align-items-center">
            {% if project.img %}
            <div class="col-md-4 p-3 text-center" style="z-index: 1;">
              <img src="{{ project.img | relative_url }}" class="img-fluid rounded" alt="{{ project.title }}" style="max-height: 220px; object-fit: contain;">
            </div>
            <div class="col-md-8">
            {% else %}
            <div class="col-md-12">
            {% endif %}
              <div class="card-body p-4">
                <h3 class="card-title font-weight-bold" style="color: #0f172a; font-size: 1.35rem;">{{ project.title }}</h3>
                <p class="card-text text-secondary my-3">{{ project.description }}</p>
                
                <div class="d-flex align-items-center gap-2 mt-3" style="gap: 10px; position: relative; z-index: 2;">
                  <!-- Read Details Tag -->
                  <span class="btn btn-sm btn-outline-primary" style="font-weight: 600; border-radius: 6px; pointer-events: none;">
                    Read Details
                  </span>

                  {% if project.redirect %}
                  <a href="{{ project.redirect }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-primary" style="background-color: #0f3460; border-color: #0f3460; font-weight: 600; border-radius: 6px;">
                    Read More <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-1"></i>
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
---
layout: page
permalink: /team/
title: Team
description: Meet the researchers, students, and collaborators at WAVESLAB.
nav: true
nav_order: 7

profiles:
  - name: "Giulia Cisotto, Ph.D."
    role: "Assistant Professor / Lab Director"
    align: left
    image: giulia_cisotto.jpg
    content: _people/about_giulia.md
    image_circular: true
    email: "giulia.cisotto@units.it"
    github: "CisottoGiulia"
    scholar: "YOUR_SCHOLAR_ID"
    more_info: >
      <p><i class="fa-solid fa-building-user me-2"></i> Department of Engineering and Architecture</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>

  - name: "Shayan Sharifi"
    role: "Ph.D. Researcher"
    align: left
    image: shayan_sharifi.jpg
    content: _people/about_shayan.md
    image_circular: true
    email: "shayan.sharifi@units.it"
    github: "shayanever"
    more_info: >
      <p><i class="fa-solid fa-laptop-code me-2"></i> WAVESLAB Member</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>
---

<style>
  .team-card {
    background: #ffffff;
    border-radius: 12px;
    border: 1px solid #e2e8f0 !important;
    overflow: hidden;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .team-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(15, 52, 96, 0.08) !important;
  }

  .team-img-wrapper {
    width: 140px;
    height: 140px;
    min-width: 140px;
    margin: 0 auto;
    overflow: hidden;
    position: relative;
    border: 3px solid #0f3460;
  }

  .team-img-wrapper.circular {
    border-radius: 50%;
  }

  .team-img-wrapper.square {
    border-radius: 12px;
  }

  .team-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .team-name {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.3rem;
  }

  .team-role {
    color: #475569;
    font-weight: 600;
    font-size: 0.95rem;
  }

  .team-social-icon {
    color: #0f3460 !important;
    font-size: 1.1rem;
    transition: color 0.2s ease;
  }

  .team-social-icon:hover {
    color: #16213e !important;
  }

  .more-info p {
    margin-bottom: 0.3rem;
    font-size: 0.88rem;
    color: #64748b;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Team</h1>
  <p class="header-subtitle">Researchers, engineers, and students advancing biomedical signal processing and AI at WAVESLAB.</p>
</div>

{% if page.profiles %}
  <div class="row row-cols-1 g-4 mb-5">
    {% for profile in page.profiles %}
      <div class="col">
        <div class="team-card p-4">
          <div class="row align-items-center g-4">
            
            <!-- Profile Photo -->
            <div class="col-md-3 text-center">
              {% if profile.image %}
                {% assign profile_image_path = profile.image | prepend: 'assets/img/' %}
                <div class="team-img-wrapper {% if profile.image_circular %}circular{% else %}square{% endif %} shadow-sm">
                  <img src="{{ profile_image_path | relative_url }}" class="team-img" alt="{{ profile.name }}">
                </div>
              {% endif %}
            </div>

            <!-- Profile Info & Bio -->
            <div class="col-md-9">
              <div class="d-flex flex-column flex-md-row justify-content-between align-items-md-start gap-2 mb-2">
                <div>
                  <h3 class="team-name mb-1">{{ profile.name }}</h3>
                  {% if profile.role %}
                    <div class="team-role mb-2">{{ profile.role }}</div>
                  {% endif %}
                </div>

                <!-- Social Links -->
                <div class="d-flex align-items-center gap-3">
                  {% if profile.email %}
                    <a href="mailto:{{ profile.email }}" title="Email" class="team-social-icon">
                      <i class="fa-solid fa-envelope"></i>
                    </a>
                  {% endif %}
                  {% if profile.github %}
                    <a href="https://github.com/{{ profile.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="team-social-icon">
                      <i class="fa-brands fa-github"></i>
                    </a>
                  {% endif %}
                  {% if profile.scholar %}
                    <a href="https://scholar.google.com/citations?user={{ profile.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" class="team-social-icon">
                      <i class="fa-solid fa-graduation-cap"></i>
                    </a>
                  {% endif %}
                </div>
              </div>

              <!-- Extra Info / Location -->
              {% if profile.more_info %}
                <div class="more-info mb-3">
                  {{ profile.more_info }}
                </div>
              {% endif %}

              <!-- Included Markdown Bio Content -->
              {% if profile.content %}
                <div class="profile-content text-secondary small">
                  {% capture profile_content %}{% include_relative {{ profile.content }} %}{% endcapture %}
                  {{ profile_content | markdownify }}
                </div>
              {% endif %}

            </div>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
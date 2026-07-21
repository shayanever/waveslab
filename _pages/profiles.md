---
layout: default
permalink: /team/
title: Team
description: Meet the researchers, students, and collaborators at WAVESLAB.
nav: true
nav_order: 7

profiles:
  - name: "Giulia Cisotto, Ph.D."
    role: "Assistant Professor / Lab Director"
    image: giulia_cisotto.jpg
    content: _people/about_giulia.md
    image_circular: true
    email: "giulia.cisotto@units.it"
    website: "https://sites.google.com/view/giulia-cisotto"
    github: "CisottoGiulia"
    scholar: "CuSEKIsAAAAJ"
    more_info: >
      <p><i class="fa-solid fa-building-user me-2"></i> Department of Mathematics, Informatics, and Geosciences</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>

  - name: "Shayan Sharifi"
    role: "Ph.D. Researcher"
    image: shayan_sharifi.jpg
    content: _people/about_shayan.md
    image_circular: true
    email: "shayan.sharifi@phd.units.it"
    website: "https://shayansharifi.net"
    github: "shayanever"
    scholar: "Juzc7T8AAAAJ"

    more_info: >
      <p><i class="fa-solid fa-laptop-code me-2"></i> WAVESLAB Member</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>

alumni:
  - name: "Alberto Zancanaro, PhD"
    role: "Former PhD Student"
    period: "2021 – 2024"
    next_position: "Postdoc researcher at University of Luxemburg"
    website: 
    github: "jesus-333"
    email: 

  - name: "Alessandro Minutolo, Msc"
    role: "Former Master Student"
    period: "2025 – 2026"
    next_position: "Researcher in Berlin"
    website: 
    github: 
    email: 
---

<style>
  .team-card {
    background: #ffffff;
    border-radius: 14px;
    border: 1px solid #e2e8f0 !important;
    overflow: hidden;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .team-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 24px rgba(15, 52, 96, 0.08) !important;
  }

  .team-img-wrapper {
    width: 150px;
    height: 150px;
    min-width: 150px;
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
    font-size: 1.35rem;
  }

  .team-role {
    color: #475569;
    font-weight: 600;
    font-size: 0.95rem;
  }

  /* Social Icons Styling & Smooth Hover Effects */
  .team-social-icon {
    color: #0f3460 !important;
    font-size: 1.25rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: #f1f5f9;
    transition: all 0.2s ease-in-out;
    text-decoration: none !important;
  }

  .team-social-icon:hover {
    color: #ffffff !important;
    background-color: #0f3460 !important;
    transform: translateY(-3px) scale(1.08);
    box-shadow: 0 4px 10px rgba(15, 52, 96, 0.25);
  }

  .more-info p {
    margin-bottom: 0.35rem;
    font-size: 0.9rem;
    color: #64748b;
  }

  .alumni-card {
    background: #ffffff;
    border-radius: 10px;
    border: 1px solid #e2e8f0;
    padding: 1.25rem 1.5rem;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Team</h1>
  <p class="header-subtitle">Researchers, engineers, and students advancing biomedical signal processing and AI at WAVESLAB.</p>
</div>

<!-- Active Members Section -->
{% if page.profiles %}
  <div class="row row-cols-1 g-4 mb-5">
    {% for profile in page.profiles %}
      <div class="col">
        <!-- Added extra internal padding (p-4 p-md-5) -->
        <div class="team-card p-4 p-md-5">
          <div class="row align-items-center g-4">
            
            <!-- Profile Photo -->
            <div class="col-md-3 text-center pe-md-4">
              {% if profile.image %}
                {% assign profile_image_path = profile.image | prepend: 'assets/img/' %}
                <div class="team-img-wrapper {% if profile.image_circular %}circular{% else %}square{% endif %} shadow-sm">
                  <img src="{{ profile_image_path | relative_url }}" class="team-img" alt="{{ profile.name }}">
                </div>
              {% endif %}
            </div>

            <!-- Profile Info & Bio -->
            <div class="col-md-9 ps-md-4">
              <div class="d-flex flex-column flex-md-row justify-content-between align-items-md-start gap-3 mb-3">
                <div>
                  <h3 class="team-name mb-1">{{ profile.name }}</h3>
                  {% if profile.role %}
                    <div class="team-role mb-2">{{ profile.role }}</div>
                  {% endif %}
                </div>

                <!-- Social Icons Bar -->
                <div class="d-flex align-items-center gap-2">
                  {% if profile.website %}
                    <a href="{{ profile.website }}" target="_blank" rel="noopener noreferrer" title="Personal Website" class="team-social-icon">
                      <i class="fa-solid fa-globe"></i>
                    </a>
                  {% endif %}
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

              <!-- Location & Extra Info -->
              {% if profile.more_info %}
                <div class="more-info mb-3">
                  {{ profile.more_info }}
                </div>
              {% endif %}

              <!-- Bio Content -->
              {% if profile.content %}
                <div class="profile-content text-secondary mt-3">
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

<!-- Past Members / Alumni Section -->
{% if page.alumni %}
  <h2 class="mt-5 mb-4" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    Past Lab Members & Alumni
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for person in page.alumni %}
      <div class="col">
        <div class="alumni-card d-flex justify-content-between align-items-center">
          <div>
            <h5 class="mb-1" style="color: #0f3460; font-weight: 700;">{{ person.name }}</h5>
            <p class="text-secondary small mb-1">{{ person.role }} {% if person.period %}({{ person.period }}){% endif %}</p>
            {% if person.next_position %}
              <p class="text-muted small mb-0"><em>Next: {{ person.next_position }}</em></p>
            {% endif %}
          </div>

          <div class="d-flex align-items-center gap-2">
            {% if person.website %}
              <a href="{{ person.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="team-social-icon">
                <i class="fa-solid fa-globe"></i>
              </a>
            {% endif %}
            {% if person.email %}
              <a href="mailto:{{ person.email }}" title="Email" class="team-social-icon">
                <i class="fa-solid fa-envelope"></i>
              </a>
            {% endif %}
            {% if person.github %}
              <a href="https://github.com/{{ person.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="team-social-icon">
                <i class="fa-brands fa-github"></i>
              </a>
            {% endif %}
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
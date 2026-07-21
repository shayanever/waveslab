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
    phone: "+39040 558 2644" # Optional phone number
    website: "https://sites.google.com/view/giulia-cisotto"
    linkedin: "giuliacisotto"
    github: "CisottoGiulia"
    scholar: "CuSEKIsAAAAJ"
    more_info: >
      <p><i class="fa-solid fa-building-user me-2"></i> Department of Mathematics, Informatics, and Geosciences</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>

  - name: "Shayan Sharifi"
    role: "Ph.D. Researcher"
    image: shayan_sharifi.png
    content: _people/about_shayan.md
    image_circular: true
    email: "shayan.sharifi@phd.units.it"
    phone: "" # Leave empty if not needed
    website: "https://shayansharifi.net"
    linkedin: "sharifi-shayan"
    github: "shayanever"
    scholar: "Juzc7T8AAAAJ"
    more_info: >
      <p><i class="fa-solid fa-laptop-code me-2"></i> WAVESLAB Member</p>
      <p><i class="fa-solid fa-location-dot me-2"></i> University of Trieste, Italy</p>

alumni:
  - name: "Alberto Zancanaro, PhD"
    role: "Former PhD Student"
    period: "2021 – 2024"
    image: alberto_zancanaro.jpg
    next_position: "Postdoc researcher at University of Luxembourg"
    linkedin: "alberto-zancanaro"
    github: "jesus-333"
    email: "alberto@example.com"
    phone: ""
    more_info: "Worked on federated learining and EEG signal processing."

  - name: "Alessandro Minutolo, MSc"
    role: "Former Master Student"
    period: "2025 – 2026"
    next_position: "Researcher in Berlin"
    linkedin: 
---

<style>
  /* Active Member Card Styling */
  .team-card {
    background: #ffffff;
    border-radius: 16px;
    border: 1px solid #e2e8f0 !important;
    padding: 2.25rem !important;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .team-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 28px rgba(15, 52, 96, 0.09) !important;
  }

  .team-img-wrapper {
    width: 160px;
    height: 160px;
    min-width: 160px;
    margin: 0 auto;
    overflow: hidden;
    position: relative;
    border: 4px solid #f1f5f9;
    box-shadow: 0 6px 16px rgba(15, 52, 96, 0.12);
  }

  .team-img-wrapper.circular {
    border-radius: 50%;
  }

  .team-img-wrapper.square {
    border-radius: 16px;
  }

  .team-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .team-name {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.4rem;
  }

  .team-role {
    color: #0f3460;
    font-weight: 600;
    font-size: 0.98rem;
    margin-bottom: 0.75rem;
  }

  /* Social Icons */
  .team-social-icon {
    color: #0f3460 !important;
    font-size: 1.15rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    background-color: #f1f5f9;
    transition: all 0.2s ease-in-out;
    text-decoration: none !important;
  }

  .team-social-icon:hover {
    color: #ffffff !important;
    background-color: #0f3460 !important;
    transform: translateY(-2px) scale(1.05);
    box-shadow: 0 4px 10px rgba(15, 52, 96, 0.2);
  }

  .more-info p {
    margin-bottom: 0.35rem;
    font-size: 0.92rem;
    color: #475569;
  }

  /* Alumni Card Styling */
  .alumni-card {
    background: #ffffff;
    border-radius: 12px;
    border: 1px solid #e2e8f0;
    padding: 1.5rem !important;
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .alumni-card:hover {
    box-shadow: 0 8px 20px rgba(15, 52, 96, 0.06);
  }

  .alumni-img-wrapper {
    width: 70px;
    height: 70px;
    min-width: 70px;
    border-radius: 50%;
    overflow: hidden;
    border: 2px solid #e2e8f0;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Team</h1>
  <p class="header-subtitle">Researchers, engineers, and students at WAVESLAB.</p>
</div>

<!-- Active Members Section -->
{% if page.profiles %}
  <div class="row row-cols-1 g-4 mb-5">
    {% for profile in page.profiles %}
      <div class="col">
        <div class="team-card">
          <div class="row align-items-center g-4">
            
            <!-- Member Headshot -->
            <div class="col-md-3 text-center pe-md-4">
              {% if profile.image %}
                {% assign profile_image_path = profile.image | prepend: 'assets/img/' %}
                <div class="team-img-wrapper {% if profile.image_circular %}circular{% else %}square{% endif %}">
                  <img src="{{ profile_image_path | relative_url }}" class="team-img" alt="{{ profile.name }}">
                </div>
              {% endif %}
            </div>

            <!-- Member Details & Description -->
            <div class="col-md-9 ps-md-3">
              <div class="d-flex flex-column flex-md-row justify-content-between align-items-md-start gap-3 mb-2">
                <div>
                  <h3 class="team-name mb-1">{{ profile.name }}</h3>
                  {% if profile.role %}
                    <div class="team-role">{{ profile.role }}</div>
                  {% endif %}
                </div>

                <!-- Social & Contact Icons Bar -->
                <div class="d-flex align-items-center gap-2">
                  {% if profile.website and profile.website != "" %}
                    <a href="{{ profile.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="team-social-icon">
                      <i class="fa-solid fa-globe"></i>
                    </a>
                  {% endif %}
                  {% if profile.linkedin and profile.linkedin != "" %}
                    <a href="https://linkedin.com/in/{{ profile.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" class="team-social-icon">
                      <i class="fa-brands fa-linkedin-in"></i>
                    </a>
                  {% endif %}
                  {% if profile.email and profile.email != "" %}
                    <a href="mailto:{{ profile.email }}" title="Email" class="team-social-icon">
                      <i class="fa-solid fa-envelope"></i>
                    </a>
                  {% endif %}
                  {% if profile.phone and profile.phone != "" %}
                    <a href="tel:{{ profile.phone }}" title="Phone: {{ profile.phone }}" class="team-social-icon">
                      <i class="fa-solid fa-phone"></i>
                    </a>
                  {% endif %}
                  {% if profile.github and profile.github != "" %}
                    <a href="https://github.com/{{ profile.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="team-social-icon">
                      <i class="fa-brands fa-github"></i>
                    </a>
                  {% endif %}
                  {% if profile.scholar and profile.scholar != "" %}
                    <a href="https://scholar.google.com/citations?user={{ profile.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" class="team-social-icon">
                      <i class="fa-solid fa-graduation-cap"></i>
                    </a>
                  {% endif %}
                </div>
              </div>

              <!-- Location & Affiliation -->
              {% if profile.more_info %}
                <div class="more-info my-2">
                  {{ profile.more_info }}
                </div>
              {% endif %}

              <!-- Bio Markdown Content -->
              {% if profile.content %}
                <div class="profile-content text-secondary mt-3 pt-2 border-top">
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
        <div class="alumni-card d-flex align-items-start gap-3">
          
          <!-- Optional Alumni Image -->
          {% if person.image %}
            {% assign alumni_image_path = person.image | prepend: 'assets/img/' %}
            <div class="alumni-img-wrapper">
              <img src="{{ alumni_image_path | relative_url }}" class="team-img" alt="{{ person.name }}">
            </div>
          {% endif %}

          <div class="w-100">
            <div class="d-flex justify-content-between align-items-start gap-2">
              <div>
                <h5 class="mb-1" style="color: #0f3460; font-weight: 700;">{{ person.name }}</h5>
                <p class="text-secondary small mb-1">{{ person.role }} {% if person.period %}({{ person.period }}){% endif %}</p>
              </div>

              <!-- Alumni Contact & Social Links -->
              <div class="d-flex align-items-center gap-2">
                {% if person.website and person.website != "" %}
                  <a href="{{ person.website }}" target="_blank" rel="noopener noreferrer" title="Website" class="team-social-icon" style="width: 32px; height: 32px; font-size: 0.95rem;">
                    <i class="fa-solid fa-globe"></i>
                  </a>
                {% endif %}
                {% if person.linkedin and person.linkedin != "" %}
                  <a href="https://linkedin.com/in/{{ person.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" class="team-social-icon" style="width: 32px; height: 32px; font-size: 0.95rem;">
                    <i class="fa-brands fa-linkedin-in"></i>
                  </a>
                {% endif %}
                {% if person.email and person.email != "" %}
                  <a href="mailto:{{ person.email }}" title="Email" class="team-social-icon" style="width: 32px; height: 32px; font-size: 0.95rem;">
                    <i class="fa-solid fa-envelope"></i>
                  </a>
                {% endif %}
                {% if person.phone and person.phone != "" %}
                  <a href="tel:{{ person.phone }}" title="Phone: {{ person.phone }}" class="team-social-icon" style="width: 32px; height: 32px; font-size: 0.95rem;">
                    <i class="fa-solid fa-phone"></i>
                  </a>
                {% endif %}
                {% if person.github and person.github != "" %}
                  <a href="https://github.com/{{ person.github }}" target="_blank" rel="noopener noreferrer" title="GitHub" class="team-social-icon" style="width: 32px; height: 32px; font-size: 0.95rem;">
                    <i class="fa-brands fa-github"></i>
                  </a>
                {% endif %}
              </div>
            </div>

            {% if person.next_position %}
              <p class="text-muted small mb-1"><em>Next: {{ person.next_position }}</em></p>
            {% endif %}

            {% if person.more_info %}
              <p class="text-secondary small mb-0 mt-2 pt-2 border-top">{{ person.more_info }}</p>
            {% endif %}
          </div>

        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
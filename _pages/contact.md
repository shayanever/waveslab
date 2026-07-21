---
layout: default
permalink: /contact/
title: Contact
description: Get in touch with WAVESLAB or visit our facilities at the University of Trieste.
nav: true
nav_order: 10
---

<style>
  .contact-card {
    background: #ffffff;
    border-radius: 14px;
    border: 1px solid #e2e8f0 !important;
    padding: 2rem !important;
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .contact-card:hover {
    box-shadow: 0 10px 24px rgba(15, 52, 96, 0.08) !important;
  }

  .contact-icon-box {
    width: 48px;
    height: 48px;
    min-width: 48px;
    border-radius: 50%;
    background-color: #f1f5f9;
    color: #0f3460;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.25rem;
  }

  .social-link-btn {
    color: #0f3460 !important;
    font-size: 1.2rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 42px;
    height: 42px;
    border-radius: 50%;
    background-color: #f1f5f9;
    border: 1px solid #cbd5e1;
    transition: all 0.2s ease-in-out;
    text-decoration: none !important;
  }

  .social-link-btn:hover {
    color: #ffffff !important;
    background-color: #0f3460 !important;
    border-color: #0f3460 !important;
    transform: translateY(-3px) scale(1.08);
    box-shadow: 0 4px 12px rgba(15, 52, 96, 0.22);
  }

  .btn-theme-primary {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    font-weight: 600;
    padding: 0.5rem 1.25rem;
    border-radius: 6px;
    text-decoration: none !important;
    display: inline-block;
    transition: background-color 0.2s ease;
  }

  .btn-theme-primary:hover {
    background-color: #16213e !important;
    color: #ffffff !important;
  }

  .map-container {
    border-radius: 14px;
    overflow: hidden;
    border: 1px solid #e2e8f0;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Contact Us</h1>
  <p class="header-subtitle">Find us at the University of Trieste or send us a message for research inquiries and collaborations.</p>
</div>

<div class="row row-cols-1 row-cols-lg-2 g-4 mb-5">
  
  <!-- Column 1: Address, General Contact Details & Social Media -->
  <div class="col">
    <div class="contact-card d-flex flex-column justify-content-between">
      <div>
        <h3 class="mb-4" style="color: #0f3460; font-weight: 700;">
          <i class="fa-solid fa-location-dot me-2"></i> Location & Office
        </h3>

        {% assign loc = site.data.contact.contact_info %}
        {% assign info = site.data.contact.location %}

        <!-- Address Info -->
        <div class="d-flex align-items-start gap-3 mb-4">
          <div class="contact-icon-box">
            <i class="fa-solid fa-building-columns"></i>
          </div>
          <div>
            <h5 class="mb-1" style="color: #0f172a; font-weight: 700;">{{ info.lab_name }}</h5>
            <div class="text-secondary small">{{ info.department }}</div>
            <div class="text-secondary small"><strong>{{ info.institution }}</strong></div>
            <div class="text-muted small mt-1">
              {{ info.building }}<br>
              {{ info.street }}<br>
              {{ info.city_zip }}
            </div>
          </div>
        </div>

        <hr class="my-4" style="border-color: #e2e8f0;">

        <!-- Email & Phone -->
        <h3 class="mb-4" style="color: #0f3460; font-weight: 700;">
          <i class="fa-solid fa-envelope me-2"></i> Enquiries & Hours
        </h3>

        <div class="d-flex align-items-start gap-3 mb-3">
          <div class="contact-icon-box">
            <i class="fa-solid fa-at"></i>
          </div>
          <div>
            <h6 class="mb-0" style="color: #0f172a; font-weight: 700;">Email Contacts</h6>
            {% if loc.general_email %}
              <div class="small"><a href="mailto:{{ loc.general_email }}" class="text-decoration-none" style="color: #0f3460;">{{ loc.general_email }}</a></div>
            {% endif %}
            {% if loc.secondary_email %}
              <div class="small"><a href="mailto:{{ loc.secondary_email }}" class="text-decoration-none" style="color: #0f3460;">{{ loc.secondary_email }}</a></div>
            {% endif %}
          </div>
        </div>

        {% if loc.phone %}
          <div class="d-flex align-items-start gap-3 mb-3">
            <div class="contact-icon-box">
              <i class="fa-solid fa-phone"></i>
            </div>
            <div>
              <h6 class="mb-0" style="color: #0f172a; font-weight: 700;">Phone</h6>
              <div class="small text-secondary"><a href="tel:{{ loc.phone }}" class="text-decoration-none text-secondary">{{ loc.phone }}</a></div>
            </div>
          </div>
        {% endif %}

        {% if loc.office_hours %}
          <div class="d-flex align-items-start gap-3 mb-4">
            <div class="contact-icon-box">
              <i class="fa-solid fa-clock"></i>
            </div>
            <div>
              <h6 class="mb-0" style="color: #0f172a; font-weight: 700;">Office Hours</h6>
              <div class="small text-secondary">{{ loc.office_hours }}</div>
            </div>
          </div>
        {% endif %}

        <!-- Social Media Section -->
        {% if site.data.contact.social_media %}
          <hr class="my-4" style="border-color: #e2e8f0;">
          <h5 class="mb-3" style="color: #0f3460; font-weight: 700;">Connect With Us</h5>
          <div class="d-flex align-items-center gap-2 flex-wrap">
            {% for item in site.data.contact.social_media %}
              {% if item.url and item.url != "" %}
                <a href="{{ item.url }}" target="_blank" rel="noopener noreferrer" title="{{ item.name }}" class="social-link-btn">
                  <i class="{{ item.icon }}"></i>
                </a>
              {% endif %}
            {% endfor %}
          </div>
        {% endif %}

      </div>

      {% if info.google_maps_url %}
        <div class="mt-4 pt-3 border-top">
          <a href="{{ info.google_maps_url }}" target="_blank" rel="noopener noreferrer" class="btn-theme-primary w-100 text-center">
            Open in Google Maps <i class="fa-solid fa-arrow-up-right-from-square ms-1"></i>
          </a>
        </div>
      {% endif %}
    </div>
  </div>

  <!-- Column 2: Interactive Map Embed & Directions -->
  <div class="col d-flex flex-column gap-4">
    <!-- Map Frame -->
    <div class="map-container shadow-sm h-100" style="min-height: 320px;">
      <iframe 
        title="WAVESLAB Location"
        src="https://maps.google.com/maps?q=Piazzale+Europa+1,+Trieste&t=&z=16&ie=UTF8&iwloc=&output=embed" 
        width="100%" 
        height="100%" 
        style="border:0; min-height: 320px;" 
        allowfullscreen="" 
        loading="lazy" 
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>

    <!-- Travel/Visiting Guidelines -->
    {% if site.data.contact.visiting_guidelines %}
      <div class="contact-card p-4">
        <h4 class="mb-3" style="color: #0f3460; font-weight: 700;">
          <i class="fa-solid fa-route me-2"></i> How to Reach Us
        </h4>
        <div class="d-flex flex-column gap-2">
          {% for guide in site.data.contact.visiting_guidelines %}
            <div class="small">
              <strong style="color: #0f172a;">{{ guide.title }}:</strong>
              <span class="text-secondary">{{ guide.detail }}</span>
            </div>
          {% endfor %}
        </div>
      </div>
    {% endif %}
  </div>

</div>

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
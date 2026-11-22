---
layout: default
permalink: /Events/
title: Events
description: Course materials, schedules, and resources for classes taught.
nav: true
nav_order: 8
calendar: true
---
<style>
  .event-card {
    background: #ffffff;
    border-radius: 14px;
    border: 1px solid #e2e8f0 !important;
    padding: 1.5rem !important;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    height: 100%;
  }

  .event-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 24px rgba(15, 52, 96, 0.08) !important;
  }

  .event-card-incoming {
    border-left: 5px solid #0f3460 !important;
  }

  /* Clean Right-Aligned Photo Frame */
  .event-photo-box {
    width: 165px;
    height: 195px;
    min-width: 165px;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid #e2e8f0;
    box-shadow: 0 4px 12px rgba(15, 52, 96, 0.08);
    background-color: #f8fafc;
  }

  .event-photo-box-past {
    width: 120px;
    height: 145px;
    min-width: 120px;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid #e2e8f0;
    box-shadow: 0 4px 10px rgba(15, 52, 96, 0.06);
    background-color: #f8fafc;
  }

  .event-photo-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center 15%;
  }

  .event-badge-incoming {
    background-color: #0f3460;
    color: #ffffff;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    padding: 0.25rem 0.7rem;
    border-radius: 999px;
    text-transform: uppercase;
    display: inline-block;
  }

  .event-badge-past {
    background-color: #f1f5f9;
    color: #475569;
    border: 1px solid #cbd5e1;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    padding: 0.22rem 0.65rem;
    border-radius: 999px;
    text-transform: uppercase;
    display: inline-block;
  }

  .event-title {
    color: #0f3460 !important;
    font-weight: 700;
    font-size: 1.2rem;
    margin-top: 0.5rem;
    margin-bottom: 0.65rem;
    line-height: 1.35;
  }

  /* Clear, Stacked Metadata Rows */
  .event-meta-list {
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
    background-color: #f8fafc;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 0.65rem 0.85rem;
    margin-bottom: 0.75rem;
  }

  .event-meta-row {
    display: flex;
    align-items: center;
    gap: 0.55rem;
    font-size: 0.88rem;
    color: #1e293b;
    line-height: 1.35;
  }

  .event-meta-row i {
    color: #0f3460;
    width: 16px;
    text-align: center;
    flex-shrink: 0;
  }

  /* Primary Theme Button (Solid Dark Blue) */
  .btn-theme-primary {
    background-color: #0f3460 !important;
    color: #ffffff !important;
    border: 1px solid #0f3460 !important;
    font-weight: 600;
    border-radius: 6px;
    padding: 0.4rem 0.95rem;
    font-size: 0.85rem;
    text-decoration: none !important;
    display: inline-flex;
    align-items: center;
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
    font-size: 0.85rem;
    text-decoration: none !important;
    display: inline-flex;
    align-items: center;
  }

  .btn-theme-outline:hover {
    background-color: #0f3460 !important;
    color: #ffffff !important;
  }
</style>

<div class="header-bar mb-4">
  <h1 class="header-title">Events</h1>
  <p class="header-subtitle">Collection of courses with detailed schedules, talks and scientific events of the lab</p>
</div>

<!-- 1. INCOMING / UPCOMING EVENTS (FULL WIDTH, PHOTO ON RIGHT) -->
{% if site.data.events.upcoming and site.data.events.upcoming.size > 0 %}
  <h2 class="mt-4 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-calendar-check me-2" style="color: #0f3460;"></i> Incoming Events
  </h2>

  <div class="row row-cols-1 g-4 mb-5">
    {% for event in site.data.events.upcoming %}
      <div class="col">
        <div class="event-card event-card-incoming">
          <div class="d-flex flex-column flex-md-row align-items-start justify-content-between gap-4">
            <!-- Left Side: Badge, Title, Separate Meta Lines, Description & Button -->
            <div class="flex-grow-1">
              <span class="event-badge-incoming">Incoming</span>
              <h3 class="event-title" style="font-size: 1.32rem;">{{ event.title }}</h3>

              <div class="event-meta-list">
                {% if event.speaker and event.speaker != "" %}
                  <div class="event-meta-row">
                    <i class="fa-solid fa-user-tie"></i>
                    <span><strong>Speaker:</strong> {{ event.speaker }}</span>
                  </div>
                {% endif %}

                {% if event.date_time and event.date_time != "" %}
                  <div class="event-meta-row">
                    <i class="fa-regular fa-clock"></i>
                    <span><strong>Date &amp; Time:</strong> {{ event.date_time }}</span>
                  </div>
                {% endif %}

                {% if event.location and event.location != "" %}
                  <div class="event-meta-row">
                    <i class="fa-solid fa-location-dot"></i>
                    <span><strong>Location:</strong> {{ event.location }}</span>
                  </div>
                {% endif %}
              </div>

              {% if event.description and event.description != "" %}
                <p class="text-secondary mb-3" style="font-size: 0.93rem; line-height: 1.6;">{{ event.description }}</p>
              {% endif %}

              {% if event.registration_link and event.registration_link != "" %}
                <div>
                  <a href="{{ event.registration_link }}" target="_blank" rel="noopener noreferrer" class="btn-theme-primary">
                    Registration Form <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-2"></i>
                  </a>
                </div>
              {% endif %}
            </div>

            <!-- Right Side: Framed Photo -->
            {% if event.image and event.image != "" %}
              {% assign img_path = event.image | prepend: 'assets/img/' %}
              <div class="event-photo-box align-self-center align-self-md-start">
                <img src="{{ img_path | relative_url }}" class="event-photo-img" alt="{{ event.title }}">
              </div>
            {% endif %}
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<!-- 2. PAST EVENTS (2-COLUMN GRID, PHOTO ON RIGHT) -->
{% if site.data.events.past and site.data.events.past.size > 0 %}
  <h2 class="mt-4 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
    <i class="fa-solid fa-clock-rotate-left me-2" style="color: #0f3460;"></i> Past Events
  </h2>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    {% for event in site.data.events.past %}
      <div class="col">
        <div class="event-card d-flex flex-column justify-content-between">
          <div>
            <div class="d-flex align-items-start justify-content-between gap-3 mb-2">
              <div class="flex-grow-1">
                <span class="event-badge-past">Past Event</span>
                <h3 class="event-title">{{ event.title }}</h3>
              </div>

              {% if event.image and event.image != "" %}
                {% assign img_path = event.image | prepend: 'assets/img/' %}
                <div class="event-photo-box-past">
                  <img src="{{ img_path | relative_url }}" class="event-photo-img" alt="{{ event.title }}">
                </div>
              {% endif %}
            </div>

            <div class="event-meta-list">
              {% if event.speaker and event.speaker != "" %}
                <div class="event-meta-row">
                  <i class="fa-solid fa-user-tie"></i>
                  <span><strong>Speaker:</strong> {{ event.speaker }}</span>
                </div>
              {% endif %}

              {% if event.date_time and event.date_time != "" %}
                <div class="event-meta-row">
                  <i class="fa-regular fa-clock"></i>
                  <span><strong>Date &amp; Time:</strong> {{ event.date_time }}</span>
                </div>
              {% endif %}

              {% if event.location and event.location != "" %}
                <div class="event-meta-row">
                  <i class="fa-solid fa-location-dot"></i>
                  <span><strong>Location:</strong> {{ event.location }}</span>
                </div>
              {% endif %}
            </div>

            {% if event.description and event.description != "" %}
              <p class="text-secondary small mb-0" style="line-height: 1.55;">{{ event.description }}</p>
            {% endif %}
          </div>

          {% if event.registration_link and event.registration_link != "" %}
            <div class="pt-3 mt-3 border-top">
              <a href="{{ event.registration_link }}" target="_blank" rel="noopener noreferrer" class="btn-theme-outline">
                Event Details / Link <i class="fa-solid fa-arrow-up-right-from-square fa-xs ms-2"></i>
              </a>
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% endif %}

<!-- 3. CALENDAR & COURSES -->
<h2 class="mt-4 mb-3" style="color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem;">
  <i class="fa-regular fa-calendar me-2" style="color: #0f3460;"></i> Lab Calendar &amp; Courses
</h2>

<div class="calendar-container my-4">
  <iframe 
    src="https://calendar.google.com/calendar/embed?src=en.italian%23holiday%40group.v.calendar.google.com&ctz=Europe%2FRome" 
    style="border: 0; width: 100%; height: 600px; border-radius: 8px;" 
    frameborder="0" 
    scrolling="no">
  </iframe>
</div>

{% include courses.liquid %}

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
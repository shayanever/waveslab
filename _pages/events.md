---
layout: default
permalink: /events/
title: events
description: Course materials, schedules, and resources for classes taught.
nav: true
nav_order: 6
calendar: true
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
  <h1 class="header-title">ٍEvents</h1>
  <p class="header-subtitle">Collection of courses with detailed schedules, talks and scientific events of the lab</p>
</div>


{% include calendar.liquid calendar_id='test@gmail.com' timezone='Asia/Shanghai' %}

{% include courses.liquid %}
<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
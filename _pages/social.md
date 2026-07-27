---
layout: default
permalink: /social/
title: Social Media
description: Connect with WavesLab across our official social media channels.
nav: true
nav_order: 9
---

<div class="header-bar mb-4">
  <h1 class="header-title">Social Media</h1>
  <p class="header-subtitle">Connect with WavesLab across our official social media channels.</p>
</div>

<div class="post">


  <h3 class="font-weight-bold mb-4">Featured Videos</h3>

  <div class="row">
    {% for video in site.data.videos %}
      <div class="col-md-6 mb-4">
        <div class="card h-100 border shadow-sm p-3">
          <!-- Video Title & Presenter -->
          <div class="text-center mb-3">
            <h5 class="font-weight-bold mb-1">{{ video.title }}</h5>
            {% if video.presenter %}
              <p class="text-muted small mb-0">
                <i class="fa-solid fa-user-tie mr-1"></i> Speaker: <strong>{{ video.presenter }}</strong>
              </p>
            {% endif %}
          </div>

          <!-- Video Embed -->
          <div class="embed-responsive embed-responsive-16by9 rounded shadow-sm">
            <iframe 
              class="embed-responsive-item" 
              src="https://www.youtube.com/embed/{{ video.youtube_id }}" 
              title="{{ video.title }}" 
              allowfullscreen>
            </iframe>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>

  <hr class="my-5">

  <h3 class="font-weight-bold mb-4">Official Channels</h3>

  <div class="row">
    <!-- YouTube Card -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-youtube fa-3x text-danger mb-3"></i>
            <h4 class="card-title font-weight-bold">YouTube</h4>
            <p class="card-text text-muted small">Watch recorded research talks, tutorials, and project demonstrations.</p>
          </div>
          <span class="badge badge-pill badge-secondary px-3 py-2 mt-3">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- LinkedIn Card -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-linkedin fa-3x mb-3" style="color: #0A66C2;"></i>
            <h4 class="card-title font-weight-bold">LinkedIn</h4>
            <p class="card-text text-muted small">Follow our official page for lab news, vacancies, and academic achievements.</p>
          </div>
          <span class="badge badge-pill badge-secondary px-3 py-2 mt-3">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- ResearchGate Card -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-researchgate fa-3x mb-3" style="color: #00CCBB;"></i>
            <h4 class="card-title font-weight-bold">ResearchGate</h4>
            <p class="card-text text-muted small">Discover preprint updates, project logs, and full publication texts.</p>
          </div>
          <span class="badge badge-pill badge-secondary px-3 py-2 mt-3">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- X (Twitter) Card -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-x-twitter fa-3x mb-3 text-dark"></i>
            <h4 class="card-title font-weight-bold">X (Twitter)</h4>
            <p class="card-text text-muted small">Get real-time updates on conference presentations and paper releases.</p>
          </div>
          <span class="badge badge-pill badge-secondary px-3 py-2 mt-3">Coming Soon</span>
        </div>
      </div>
    </div>
  </div>

</div>

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
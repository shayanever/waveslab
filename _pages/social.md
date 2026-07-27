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

  <h3 class="font-weight-bold mb-4" style="color: #0f3460;">Featured Videos</h3>

  <div class="row">
    {% for video in site.data.videos %}
      <div class="col-md-6 mb-4">
        <div class="card h-100 border shadow-sm p-3 d-flex flex-column justify-content-center" style="border-radius: 8px;">
          
          <!-- Video Title & Presenter -->
          <div class="text-center mb-3">
            <h6 class="font-weight-bold mb-1" style="color: #0f3460;">{{ video.title }}</h6>
            {% if video.presenter %}
              <p class="text-muted small mb-0">
                <i class="fa-solid fa-user-tie mr-1" style="color: #0f3460;"></i> Speaker: <strong>{{ video.presenter }}</strong>
              </p>
            {% endif %}
          </div>

          <!-- Video Embed -->
          <div class="embed-responsive embed-responsive-16by9 rounded shadow-sm w-100">
            <iframe 
              class="embed-responsive-item w-100 h-100" 
              src="https://www.youtube.com/embed/{{ video.youtube_id }}" 
              title="{{ video.title }}" 
              style="border: 0;"
              allowfullscreen>
            </iframe>
          </div>

        </div>
      </div>
    {% endfor %}
  </div>

  <hr class="my-5" style="border-top: 1px solid rgba(15, 52, 96, 0.15);">

  <h3 class="font-weight-bold mb-4" style="color: #0f3460;">Official Channels</h3>

  <div class="row">
    <!-- YouTube Card (Official Red) -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3" style="border-radius: 8px;">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-youtube fa-3x mb-3" style="color: #FF0000;"></i>
            <h4 class="card-title font-weight-bold" style="color: #0f3460;">YouTube</h4>
            <p class="card-text text-muted small">Watch recorded research talks, tutorials, and project demonstrations.</p>
          </div>
          <span class="badge badge-pill px-3 py-2 mt-3" style="background-color: #0f3460; color: #ffffff;">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- LinkedIn Card (Official LinkedIn Blue) -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3" style="border-radius: 8px;">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-linkedin fa-3x mb-3" style="color: #0A66C2;"></i>
            <h4 class="card-title font-weight-bold" style="color: #0f3460;">LinkedIn</h4>
            <p class="card-text text-muted small">Follow our official page for lab news, vacancies, and academic achievements.</p>
          </div>
          <span class="badge badge-pill px-3 py-2 mt-3" style="background-color: #0f3460; color: #ffffff;">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- ResearchGate Card (Official ResearchGate Teal) -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3" style="border-radius: 8px;">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-researchgate fa-3x mb-3" style="color: #00CCBB;"></i>
            <h4 class="card-title font-weight-bold" style="color: #0f3460;">ResearchGate</h4>
            <p class="card-text text-muted small">Discover preprint updates, project logs, and full publication texts.</p>
          </div>
          <span class="badge badge-pill px-3 py-2 mt-3" style="background-color: #0f3460; color: #ffffff;">Coming Soon</span>
        </div>
      </div>
    </div>

    <!-- X / Twitter Card (Official Black) -->
    <div class="col-md-6 mb-4">
      <div class="card h-100 border shadow-sm text-center p-3" style="border-radius: 8px;">
        <div class="card-body d-flex flex-column justify-content-between align-items-center">
          <div>
            <i class="fa-brands fa-x-twitter fa-3x mb-3" style="color: #000000;"></i>
            <h4 class="card-title font-weight-bold" style="color: #0f3460;">X (Twitter)</h4>
            <p class="card-text text-muted small">Get real-time updates on conference presentations and paper releases.</p>
          </div>
          <span class="badge badge-pill px-3 py-2 mt-3" style="background-color: #0f3460; color: #ffffff;">Coming Soon</span>
        </div>
      </div>
    </div>
  </div>

</div>

<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
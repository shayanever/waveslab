---
layout: default
title: Home
permalink: /
---

<style>
  /* --- Global Reset & Page Scroll Setup --- */
html, body {
    margin: 0;
    padding: 0;
    width: 100%;
    max-width: 100%;
    overflow-x: hidden !important; /* Prevents horizontal scroll entirely */
    background-color: #f8fafc !important;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  }

  .content-section {
    max-width: 960px;
    margin: 0 auto;
    padding: 4rem 1.5rem;
  }

  /* --- Fullscreen Interactive Waves Banner --- */
  .banner-container {
    position: relative;
    width: 100%;
    height: 100vh;
    margin-left: 0;
    margin-top: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #f8f9fa !important;
    overflow: hidden;
    border-bottom: 1px solid #e2e8f0;
  }

  canvas#waveCanvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
  }

  /* --- Central Content Wrapper --- */
  .logo-wrapper {
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 40px 60px 60px 60px;
    
    /* Shift logo upward visually */
    margin-top: -110px; 
    
    /* Radial soft fade effect so the wave behind the logo diminishes cleanly */
    background: radial-gradient(circle, rgba(248, 249, 250, 0.95) 62%, rgba(248, 249, 250, 0) 75%);
    border-radius: 50%;
    pointer-events: auto;
  }

  /* Entrance Animation Container */
  .logo-overlay {
    max-width: 620px; /* Enlarged logo size */
    width: 85%;
    opacity: 0;
    cursor: pointer;
    animation: fadeInLogo 1.2s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
    animation-delay: 0.2s;
  }

  /* Hover effect separated on <img> to prevent CSS keyframe conflicts */
  .logo-overlay img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
    will-change: transform;
  }

  .logo-overlay:hover img {
    transform: scale(1.08); /* Scales up logo smoothly on mouse hover */
  }

  @keyframes fadeInLogo {
    from {
      opacity: 0;
      transform: translateY(12px) scale(0.98);
    }
    to {
      opacity: 1;
      transform: translateY(0) scale(1);
    }
  }

  /* Subtitle Typewriter Styling */
  .subtitle {
    margin-top: 18px;
    font-size: 0.9rem;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: #0f3460;
    min-height: 1.4em;
    text-align: center;
  }

  /* Blinking cursor for the typewriter effect */
  .typewriter-cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background-color: #0f3460;
    margin-left: 2px;
    vertical-align: middle;
    animation: blink 0.8s infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  /* --- Scroll-Driven Fade In for Page Elements --- */
  .reveal-on-scroll {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.8s cubic-bezier(0.165, 0.84, 0.44, 1), transform 0.8s cubic-bezier(0.165, 0.84, 0.44, 1);
    will-change: opacity, transform;
  }

  .reveal-on-scroll.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* --- Premium Section Styling --- */
  .section-block {
    margin-bottom: 5rem;
  }
  .section-title {
    font-size: 1.85rem;
    font-weight: 800;
    color: #0f172a;
    margin-bottom: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    padding-bottom: 0.75rem;
  }
  .section-title::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 60px;
    height: 4px;
    background: linear-gradient(90deg, #00779b, #6a1b9a);
    border-radius: 2px;
  }
  .btn-more {
    font-size: 0.85rem;
    font-weight: 600;
    color: #00779b;
    text-decoration: none;
    border: 2px solid #e2e8f0;
    padding: 0.4rem 1.1rem;
    border-radius: 9999px;
    background-color: #ffffff;
    transition: all 0.3s ease;
  }
  .btn-more:hover {
    background-color: #00779b;
    border-color: #00779b;
    color: #ffffff !important;
    text-decoration: none;
    box-shadow: 0 4px 12px rgba(0, 119, 155, 0.15);
    transform: translateY(-1px);
  }

  /* Intro Section Card */
  .intro-card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 16px;
    padding: 3rem 2.5rem;
    box-shadow: 0 10px 30px rgba(15, 23, 42, 0.04);
    position: relative;
    z-index: 10;
  }

  /* Card-Based News Styling */
  .news-card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 14px;
    padding: 1.5rem;
    margin-bottom: 1.25rem;
    display: flex;
    gap: 1.5rem;
    align-items: center;
    transition: all 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.01), 0 2px 4px -1px rgba(0, 0, 0, 0.01);
  }
  .news-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 20px -3px rgba(15, 23, 42, 0.08);
    border-color: #cbd5e1;
  }
  .news-date-badge {
    background: linear-gradient(135deg, #f1f5f9 0%, #e2e8f0 100%);
    color: #475569;
    padding: 1rem;
    border-radius: 10px;
    min-width: 90px;
    text-align: center;
    font-weight: 700;
    line-height: 1.2;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .news-date-badge .day {
    font-size: 1.5rem;
    color: #0f172a;
  }
  .news-date-badge .month {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  .news-thumbnail {
    width: 90px;
    height: 90px;
    object-fit: cover;
    border-radius: 10px;
    border: 1px solid #e2e8f0;
  }
  .news-content {
    flex-grow: 1;
  }

  /* Projects Grid */
  .research-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.75rem;
  }
  .research-card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 14px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.01);
  }
  .research-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 16px 24px -4px rgba(15, 23, 42, 0.08);
    border-color: #cbd5e1;
  }

  /* Publication Wrapper */
  .publication-wrapper {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 14px;
    padding: 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.01);
  }
</style>

<!-- 1. Full-Screen Interactive Waves Banner -->
<div class="banner-container" id="banner">
  <canvas id="waveCanvas"></canvas>
  <div class="logo-wrapper">
    <div class="logo-overlay">
      <img src="{{ '/assets/img/waveslab_logo.png' | relative_url }}" alt="WAVESLAB Logo">
    </div>
    <div class="subtitle" id="typewriterSubtitle"></div>
  </div>
</div>

<div class="content-section">
  
  <!-- 2. Introduction Card -->
  <div class="section-block reveal-on-scroll">
    <div class="intro-card text-center">
      <h2 class="text-3xl font-extrabold mb-4" style="color: #0f172a; letter-spacing: -0.02em;">Welcome to WAVESLAB</h2>
      <p class="text-lg text-slate-600 leading-relaxed mb-4 max-w-2xl mx-auto">
        We develop advanced methods for biosignal preprocessing, analysis, and modeling, with a focus on electroencephalography (EEG) and electrocardiography (ECG).
      </p>
      <p class="text-base text-slate-500 leading-relaxed max-w-2xl mx-auto font-medium">
        A central goal of our lab is to address critical data-quality issues and build machine learning models that are robust to the intrinsic variability of biological signals.
      </p>
    </div>
  </div>

  <!-- 3. Dynamic Latest News Stream -->
  <div class="section-block reveal-on-scroll">
    <div class="section-title">
      <span>Latest News</span>
      <a href="{{ '/blog/' | relative_url }}" class="btn-more">View All News &rarr;</a>
    </div>
    <div class="news-container">
      {% if site.posts and site.posts.size > 0 %}
        {% for post in site.posts limit: 3 %}
          <div class="news-card">
            {% if post.preview %}
              <img src="{{ post.preview | relative_url }}" class="news-thumbnail" alt="News Image">
            {% else %}
              <div class="news-date-badge">
                <span class="day">{{ post.date | date: "%d" }}</span>
                <span class="month">{{ post.date | date: "%b" }}</span>
              </div>
            {% endif %}
            <div class="news-content">
              <span class="text-xs font-semibold uppercase tracking-wider text-slate-400 block mb-1">
                {{ post.date | date: "%B %Y" }}
              </span>
              <h4 class="text-lg font-bold text-slate-800 mb-1 hover:text-blue-600" style="transition: color 0.2s;">
                <a href="{{ post.url | relative_url }}" style="color: inherit; text-decoration: none;">{{ post.title }}</a>
              </h4>
              <p class="text-slate-500 text-sm leading-relaxed m-0">
                {{ post.description | default: post.excerpt | strip_html | truncatewords: 25 }}
              </p>
            </div>
          </div>
        {% endfor %}
      {% else %}
        <div class="news-card">
          <div class="news-date-badge">
            <span class="day">15</span>
            <span class="month">Jul</span>
          </div>
          <div class="news-content">
            <h4 class="text-lg font-bold text-slate-800">Launch of the WAVESLAB Space</h4>
            <p class="text-slate-500 text-sm">Create markdown files inside your "_posts" directory to dynamically populate this timeline.</p>
          </div>
        </div>
      {% endif %}
    </div>
  </div>

  <!-- 4. Research Tracks Component -->
  <div class="section-block reveal-on-scroll">
    <div class="section-title">
      <span>Active Research Tracks</span>
      <a href="{{ '/projects/' | relative_url }}" class="btn-more">Explore Projects &rarr;</a>
    </div>
    <div class="research-grid">
      {% if site.projects and site.projects.size > 0 %}
        {% for project in site.projects limit: 3 %}
          <div class="research-card">
            <div>
              <h4 class="text-xl font-extrabold text-slate-800 mb-2">
                <a href="{{ project.url | relative_url }}" class="hover:text-blue-600" style="color: inherit; text-decoration: none;">{{ project.title }}</a>
              </h4>
              <p class="text-slate-500 text-sm leading-relaxed mb-4">{{ project.description | strip_html | truncatewords: 20 }}</p>
            </div>
            <a href="{{ project.url | relative_url }}" class="text-sm font-bold text-sky-700 hover:text-sky-900 text-decoration-none">Learn track details &rarr;</a>
          </div>
        {% endfor %}
      {% else %}
        <div class="research-card">
          <div>
            <h4 class="text-xl font-extrabold text-slate-800 mb-2">Brain–Computer Interfaces</h4>
            <p class="text-slate-500 text-sm mb-4">Investigating EEG decoding techniques for intuitive movement control and next-generation neural interfaces.</p>
          </div>
        </div>
        <div class="research-card">
          <div>
            <h4 class="text-xl font-extrabold text-slate-800 mb-2">Clinical Decision Support</h4>
            <p class="text-slate-500 text-sm mb-4">Developing intelligent signal analysis systems to enhance diagnostic monitoring and patient care pipelines.</p>
          </div>
        </div>
      {% endif %}
    </div>
  </div>

  <!-- 5. Bibliography Pipeline -->
  <div class="section-block reveal-on-scroll">
    <div class="section-title">
      <span>Featured Publications</span>
      <a href="{{ '/publications/' | relative_url }}" class="btn-more">Full Bibliography &rarr;</a>
    </div>
    <div class="publication-wrapper">
      {% bibliography --query @*[selected=true]* %}
    </div>
  </div>

</div>

<!-- Scripts -->
<script>
  // --- 1. Wave Canvas Pipeline ---
  const canvas = document.getElementById('waveCanvas');
  const ctx = canvas.getContext('2d');

  function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  resizeCanvas();
  window.addEventListener('resize', resizeCanvas);

  const mouse = {
    x: -1000,
    y: (canvas.height / 2) - 70,
    targetX: -1000,
    targetY: (canvas.height / 2) - 70
  };

  window.addEventListener('mousemove', (e) => {
    mouse.targetX = e.clientX;
    mouse.targetY = e.clientY;
  });

  window.addEventListener('mouseleave', () => {
    mouse.targetX = -1000;
  });

  let phase = 0;

  function animate() {
    requestAnimationFrame(animate);
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    mouse.x += (mouse.targetX - mouse.x) * 0.1;
    mouse.y += (mouse.targetY - mouse.y) * 0.1;

    // Wave line shifted up by 70px to align with .logo-wrapper margin-top
    const centerY = (canvas.height / 2) - 70;

    const gradient = ctx.createLinearGradient(0, 0, canvas.width, 0);
    gradient.addColorStop(0.1, '#0f3460');
    gradient.addColorStop(0.5, '#6a1b9a');
    gradient.addColorStop(0.9, '#e61246');

    ctx.beginPath();
    ctx.moveTo(0, centerY);

    for (let x = 0; x <= canvas.width; x += 2) {
      const distToMouse = Math.abs(x - mouse.x);
      const spread = 180;
      const influence = Math.exp(-Math.pow(distToMouse / spread, 2));

      const baseWave = Math.sin(x * 0.003 + phase) * 8;
      const spikeFrequency = 0.04;
      const spike = Math.sin(x * spikeFrequency - phase * 3) * (influence * 60);

      const y = centerY + baseWave + spike;
      ctx.lineTo(x, y);
    }

    ctx.strokeStyle = gradient;
    ctx.lineWidth = 2.5;
    ctx.lineCap = 'round';
    ctx.stroke();

    phase += 0.03;
  }

  animate();

  // --- 2. Typewriter Effect for Subtitle ---
  const textToType = "Since November 2025 · Trieste";
  const subtitleContainer = document.getElementById('typewriterSubtitle');
  let charIndex = 0;

  function typeWriter() {
    if (charIndex === 0) {
      subtitleContainer.innerHTML = '<span id="typedText"></span><span class="typewriter-cursor"></span>';
    }
    
    if (charIndex < textToType.length) {
      document.getElementById('typedText').textContent += textToType.charAt(charIndex);
      charIndex++;
      setTimeout(typeWriter, 50); // Speed of typing in ms
    }
  }

  // Delay typewriter slightly to synchronize with logo fade-in
  setTimeout(typeWriter, 800);

  // --- 3. Intersection Observer for Scroll Fade-In ---
  const observerOptions = {
    root: null,
    threshold: 0.15
  };

  const revealObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, observerOptions);

  document.querySelectorAll('.reveal-on-scroll').forEach(element => {
    revealObserver.observe(element);
  });
</script>
<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
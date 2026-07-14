<!-- ---
layout: about
title: about
permalink: /
subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Motto. Etc.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>555 your office number</p>
    <p>123 your address street</p>
    <p>Your City, State 12345</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

Write your biography here. Tell the world about yourself. Link to your favorite [subreddit](https://www.reddit.com). You can put a picture in, too. The code is already in, just name your picture `prof_pic.jpg` and put it in the `img/` folder.

Put your address / P.O. box / other info right below your picture. You can also disable any of these elements by editing `profile` property of the YAML header of your `_pages/about.md`. Edit `_bibliography/papers.bib` and Jekyll will render your [publications page](/al-folio/publications/) automatically.

Link to your social media connections, too. This theme is set up to use [Font Awesome icons](https://fontawesome.com/) and [Academicons](https://jpswalsh.github.io/academicons/), like the ones below. Add your Facebook, Twitter, LinkedIn, Google Scholar, or just disable all of them. -->


---
layout: about
title: About
permalink: /
---

<style>
  .banner-container {
    position: relative;
    width: 100vw;
    height: 75vh;
    margin-left: calc(-50vw + 50%);
    margin-top: -2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ffffff;
    overflow: hidden;
  }
  canvas#waveCanvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    pointer-events: none;
  }
  .logo-overlay {
    position: relative;
    z-index: 2;
    max-width: 45%;
    min-width: 280px;
    user-select: none;
    pointer-events: auto;
    transition: transform 0.3s ease;
  }
  .logo-overlay:hover {
    transform: scale(1.03);
  }
  .logo-overlay img {
    width: 100%;
    height: auto;
    display: block;
  }
</style>

<div class="banner-container" id="banner">
  <canvas id="waveCanvas"></canvas>
  <div class="logo-overlay">
    <img src="{{ '/assets/img/unnamed (1).png' | relative_url }}" alt="WAVESLAB Logo">
  </div>
</div>

<script>
  const canvas = document.getElementById("waveCanvas");
  if (canvas) {
    const ctx = canvas.getContext("2d");
    const container = document.getElementById("banner");

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = container.clientHeight;
    }
    resizeCanvas();
    window.addEventListener("resize", resizeCanvas);

    const mouse = {
      x: window.innerWidth / 2,
      y: container.clientHeight / 2,
      targetX: window.innerWidth / 2,
      targetY: container.clientHeight / 2,
    };

    container.addEventListener("mousemove", (e) => {
      const rect = container.getBoundingClientRect();
      mouse.targetX = e.clientX - rect.left;
      mouse.targetY = e.clientY - rect.top;
    });

    let increment = 0;
    const waveColors = [
      "rgba(15, 52, 96, 0.15)", /* Dark Blue */
      "rgba(106, 27, 154, 0.1)", /* Purple/Magenta */
      "rgba(230, 18, 70, 0.08)", /* Pink/Red */
    ];

    function animate() {
      requestAnimationFrame(animate);
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      mouse.x += (mouse.targetX - mouse.x) * 0.05;
      mouse.y += (mouse.targetY - mouse.y) * 0.05;

      waveColors.forEach((color, index) => {
        ctx.beginPath();
        const baseAmplitude = 60 + index * 20;
        const mouseInfluenceY = (1 - mouse.y / canvas.height) * 80;
        const amplitude = baseAmplitude + mouseInfluenceY;
        const frequency = 0.003 + index * 0.001 + mouse.x * 0.000005;

        ctx.moveTo(0, canvas.height / 2);

        for (let i = 0; i < canvas.width; i++) {
          const y =
            canvas.height / 2 +
            Math.sin(i * frequency + increment + index * 2) * amplitude;
          ctx.lineTo(i, y);
        }

        ctx.strokeStyle = color;
        ctx.lineWidth = 3 - index * 0.5;
        ctx.stroke();
      });

      increment += 0.015;
    }

    animate();
  }
</script>

<hr class="my-5">

### Welcome to WAVESLAB

This is where your introductory text can be added using plain Markdown.
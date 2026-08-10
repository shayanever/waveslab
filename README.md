
Conversation with Gemini
change it to readme.md

Image Location: Upload preview/thumbnail images into assets/img/.

2. Team & Members (_pages/_profile.md & _pages/_people/)
Section A: Updating Member Roster (_pages/_profile.md)
Open _pages/_profile.md and add or update team entries in YAML format:

YAML
- name: "Dr. Jane Doe"
  role: "Postdoctoral Researcher"
  avatar: "/assets/img/team/jane_doe.jpg"
  bio: "Focuses on high-density EEG artifact removal and signal modeling."
  email: "jane.doe@units.it"
  google_scholar: "[https://scholar.google.com/](https://scholar.google.com/)..."
  github: "janedoe"
Section B: Individual Detailed Bio Pages (_pages/_people/)
For long-form biographies or detailed research profiles:

Create a new .md file inside _pages/_people/ (e.g., jane_doe.md).

Upload headshot images to assets/img/.

Ensure the person is referenced inside _pages/_profile.md so the profile link connects properly.

3. Publications (_bibliography/papers.bib)
The bibliography is dynamically built from standard BibTeX format. Open _bibliography/papers.bib and paste the new publication's BibTeX entry at the bottom:

Code snippet
@article{PhysRev.47.777,
  abbr              = {PhysRev},
  title             = {Can Quantum-Mechanical Description of Physical Reality Be Considered Complete?},
  author            = {Einstein*†, A. and Podolsky*, B. and Rosen*, N.},
  abstract          = {In a complete theory there is an element complete.},
  journal           = {Phys. Rev.},
  location          = {New Jersey},
  volume            = {47},
  issue             = {10},
  pages             = {777--780},
  year              = {1935},
  month             = {May},
  publisher         = {aps},
  doi               = {10.1103/PhysRev.47.777},
  url               = {[https://link.aps.org/doi/10.1103/PhysRev.47.777](https://link.aps.org/doi/10.1103/PhysRev.47.777)},
  google_scholar_id = {qyhmnyLat1gC},
  video             = {[https://www.youtube-nocookie.com/embed/aqz-KE-bpKQ](https://www.youtube-nocookie.com/embed/aqz-KE-bpKQ)},
  additional_info   = {. *More Information* can be [found here](https://github.com/...)},
  selected          = {true},
  preview           = {brownian-motion.gif}
}
Key Toggle: Adding selected={true} automatically features the paper in the Featured Publications section on the Home Page. Removing selected={true} keeps it listed exclusively on the main Publications page.

4. Active Research Projects (_projects/)
Projects are displayed on the Home Page grid and the main /projects/ page.

Where to find files: _projects/

File Naming Format: project-title.md (e.g., ecg-cardiomyopathies.md)

Markdown
---
layout: page
title: "Explainable AI for ECG-based Screening of Cardiomyopathies"
description: "This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures..."
img: assets/img/asugi.png
logo: true
external_link: [https://asugi.sanita.fvg.it/it/schede/UniTS/index.html](https://asugi.sanita.fvg.it/it/schede/UniTS/index.html)
importance: 1
category: work
preview: assets/img/news/asugi.png
related_publications:
  - sharifi2026waveslab
---

This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures associated with cardiomyopathies... The study is carried out in collaboration with ASUGI–Cattinara.
Note: importance: 1 places the project at the top of the list. Higher numbers appear further down. To connect a publication, list its BibTeX key under related_publications.

5. GitHub & Software Repositories (_data/repositories.yml)
Displays open-source codebases, tools, and datasets created by WAVESLAB. Open _data/repositories.yml and update user/repo lists:

YAML
github_users:
  - shayanever
  - CisottoGiulia
  - jesus-333

repo_description_lines_max: 2

github_repos:
  - name: EEG-EMG-analytics
    user: CisottoGiulia
    description: "Analytics pipeline and toolsets for synchronized EEG and EMG signal processing."
    related_publications:
      - sharifi2026waveslab

  - name: Variational-Autoencoder-for-EEG-analysis
    user: jesus-333
    description: "Deep learning architecture based on VAEs for feature extraction from EEG data."
    related_publications:
      - sharifi2026waveslab

  - name: ecg-Rpeak-validation-neurokit
    user: shayanever
    description: "Validation tools for ECG R-peak detection benchmarking against NeuroKit2."
    related_publications:
      - sharifi2026waveslab

  - name: Sleep-Apnea-and-Hypopnea-Detection
    user: shayanever
    description: "Machine learning framework for automated sleep apnea and hypopnea detection."
    related_publications:
      - sharifi2026waveslab
6. Collaborations (_pages/collaborations.md)
Manages partner institutions, clinical partners, and university lab networks categorized by group (e.g., Academia, Hospitals). Open _pages/collaborations.md and add collaborator blocks under the appropriate section header:

YAML
- name: "Prof. Leonardo Badia"
  institution: "University of Padova"
  location: "Padova, Italy"
  address: "Via Gradenigo 6/b, 35131 Padova, Italy"
  image: "" # e.g., badia.jpg in assets/img/
  website: "[https://www.dei.unipd.it/~badia/](https://www.dei.unipd.it/~badia/)"
  linkedin: "leonardo-badia"
  github: ""
  scholar: ""
  email: "badia@dei.unipd.it"
  phone: ""
  description: "Collaborating on bio-signal processing algorithms and communication frameworks."
7. Join Us / Opportunities (_data/positions.yml)
Houses open calls for PhD candidates, postdocs, master's thesis projects, and visiting researchers. Open _data/positions.yml and add or edit position listings:

YAML
- title: "PhD Position in Neural Signal Modeling"
  deadline: "October 15, 2026"
  location: "Trieste, Italy"
  description: "We are seeking a motivated PhD candidate with a strong background in biomedical engineering or machine learning..."
8. Contact Information (_data/contact.yml)
Contains lab location, directions, and official contact email addresses. Open _data/contact.yml and update the values:

YAML
address: "Department of Engineering and Architecture, University of Trieste, Italy"
email: "info@waveslab.org"
9. Social Media & Videos (_data/videos.yml & _pages/social.md)
Adding Featured YouTube Videos
Open _data/videos.yml and add a new video block:

YAML
- title: "QUALI SONO I MISTERI DELL'EEG?"
  presenter: "Dr. Giulia Cisotto"
  youtube_id: "CGOohNAe868"

- title: "Comprendere o calcolare? Al confine tra intelligenza umana e artificiale"
  presenter: "Dr. Giulia Cisotto and Dr. F. Anselmi"
  youtube_id: "WEGKDRCsB6U"
youtube_id: The unique string at the end of the YouTube URL (e.g., in youtube.com/watch?v=CGOohNAe868, the ID is CGOohNAe868).

Updating Social Links
Open _pages/social.md to update official channel URLs or change status badges when accounts go live.

10. Events, Seminars & Courses (_pages/events.md & _teachings/)
Calendar Integration (_pages/events.md)
To change the embedded Google Calendar, open _pages/events.md and swap the src attribute inside the <iframe> tag:

HTML
<div class="calendar-container my-4">
  <iframe 
    src="[https://calendar.google.com/calendar/embed?src=en.italian%23holiday%40group.v.calendar.google.com&amp;ctz=Europe%2FRome](https://calendar.google.com/calendar/embed?src=en.italian%23holiday%40group.v.calendar.google.com&amp;ctz=Europe%2FRome)" 
    style="border: 0; width: 100%; height: 600px; border-radius: 8px;" 
    frameborder="0" 
    scrolling="no">
  </iframe>
</div>
Course & Teaching Details (_teachings/)
To add detailed course syllabi, lecture notes, or workshop materials:

Navigate to _teachings/.

Create a new .md file (e.g., biosignal-processing-2026.md).

Fill in course metadata and content using standard Markdown like samples.

Quick Markdown Formatting Cheat Sheet
Style	Syntax Example	Output Result
Bold Text	**sample text**	sample text
Italic Text	*sample text*	sample text
Header Level 2	## Section Title	Sub-section heading
Header Level 3	### Subsection Title	Minor section heading
Web Link	[WavesLab Website](https://shayansharifi.net/waveslab/)	WavesLab Website
Bullet Points	
- First item


- Second item

• First item


• Second item

Summary Cheatsheet: File Locations & Formats
Menu Item	File / Directory	Format	Key Function
Home	index.html / _includes/	HTML / JS	Banner text & main landing page cards
News	_posts/	Markdown (.md)	Posts announcements & talk details
Team	_pages/_profile.md & _pages/_people/	YAML / Markdown	Member roster & bio pages
Publications	_bibliography/papers.bib	BibTeX (.bib)	Dynamic publication library
Projects	_projects/	Markdown (.md)	Research track descriptions
GitHub	_data/repositories.yml	YAML (.yml)	Open-source GitHub repositories
Collaborations	_pages/collaborations.md	Markdown / YAML	Partner institutions & researchers
Join us	_data/positions.yml	YAML (.yml)	Open PhD & Postdoc vacancy calls
Contact	_data/contact.yml	YAML (.yml)	Lab address & email details
Social Media	_data/videos.yml & _pages/social.md	YAML / Markdown	Featured talks & official channel links
Events	_pages/events.md & _teachings/	HTML / Markdown	Google Calendar & course materials
with open("readme.md", "w", encoding="utf-8") as f:
f.write(markdown_content)

print("readme.md file successfully created.")


```text?code_stdout&code_event_index=1
readme.md file successfully created.

Your Markdown file is ready:

MD icon
readme
 MD 
Open
The HTML content has been converted into clean standard Markdown and saved as readme.md.




Gemini is AI and can make mistakes, including about people. Your privacy & GeminiOpens in a new window

# WAVESLAB Complete Website Administration Guide

Welcome to the official administrative guide for **WAVESLAB**. This document explains how to add, edit, or remove content across every section of the website. All site content is managed through simple text files (Markdown `.md` files) or data files (YAML `.yml` / BibTeX `.bib` files) in the GitHub repository without needing programming experience.

---

## Essential Rules for Editing Files

- **Maintain Formatting & Indentation:** YAML files rely on precise spacing. Do not delete spaces or tabs at the beginning of lines.
- **Use Quotation Marks:** Wrap titles, names, descriptions, and string fields in quotation marks (e.g., `"Dr. Giulia Cisotto"`).
- **Save Your Changes:** Always click the **Commit changes...** button after editing a file on GitHub.
- **Automated Live Deployment:** Once changes are committed, GitHub Pages will automatically rebuild and publish the site live in **1–2 minutes**.

---

## 1. News (`_posts/`)

News items automatically populate on both the Home Page stream and the main `/blog/` page.

- **Where to find files:** `_posts/`
- **File Naming Format:** `YYYY-MM-DD-title.md` (e.g., `2026-07-14-autoresearch-talk.md`)

```markdown
---
layout: post
title: "Brief Talk on AutoResearch by Dr. Alberto Zancanaro"
date: 2026-07-14 14:00:00
description: "Former lab member Dr. Alberto Zancanaro will give a brief talk on AutoResearch on July 16th at 10 am."
thumbnail: assets/img/alberto_zancanaro.jpg
preview: assets/img/alberto_zancanaro.jpg
---

<div class="float-right mr-4 mb-3" style="max-width: 300px;">
  {% include figure.liquid loading="eager" path="assets/img/alberto_zancanaro.jpg" class="img-fluid rounded z-depth-1" alt="Talk" %}
</div>

Our former lab member, **Dr. Alberto Zancanaro**, will give a brief talk on **AutoResearch** on **July 16th at 10:00 AM**. 

Wish to listen? You can [attend the talk here](https://teams.microsoft.com/...).
```

- **Image Location:** Upload preview/thumbnail images into `assets/img/`.

---

## 2. Team & Members (`_pages/_profile.md` & `_pages/_people/`)

### Section A: Updating Member Roster (`_pages/_profile.md`)

Open `_pages/_profile.md` and add or update team entries in YAML format:

```yaml
- name: "Dr. Jane Doe"
  role: "Postdoctoral Researcher"
  avatar: "/assets/img/team/jane_doe.jpg"
  bio: "Focuses on high-density EEG artifact removal and signal modeling."
  email: "jane.doe@units.it"
  google_scholar: "https://scholar.google.com/..."
  github: "janedoe"
```

### Section B: Individual Detailed Bio Pages (`_pages/_people/`)

For long-form biographies or detailed research profiles:

1. Create a new `.md` file inside `_pages/_people/` (e.g., `jane_doe.md`).
2. Upload headshot images to `assets/img/`.
3. Ensure the person is referenced inside `_pages/_profile.md` so the profile link connects properly.

---

## 3. Publications (`_bibliography/papers.bib`)

The bibliography is dynamically built from standard BibTeX format. Open `_bibliography/papers.bib` and paste the new publication's BibTeX entry at the bottom:

```bibtex
@article{PhysRev.47.777,
  abbr              = {PhysRev},
  title             = {Can Quantum-Mechanical Description of Physical Reality Be Considered Complete?},
  author            = {Einstein*†, A. and Podolsky*, B. and Rosen*, N.},
  abstract          = {In a complete theory there is an element complete.},
  journal           = {Phys. Rev.},
  location          = {New Jersey},
  volume            = {47},
  issue             = {10},
  pages             = {777--780},
  year              = {1935},
  month             = {May},
  publisher         = {aps},
  doi               = {10.1103/PhysRev.47.777},
  url               = {https://link.aps.org/doi/10.1103/PhysRev.47.777},
  google_scholar_id = {qyhmnyLat1gC},
  video             = {https://www.youtube-nocookie.com/embed/aqz-KE-bpKQ},
  additional_info   = {. *More Information* can be [found here](https://github.com/...)},
  selected          = {true},
  preview           = {brownian-motion.gif}
}
```

- **Key Toggle:** Adding `selected={true}` automatically features the paper in the **Featured Publications** section on the Home Page. Removing `selected={true}` keeps it listed exclusively on the main Publications page.

---

## 4. Active Research Projects (`_projects/`)

Projects are displayed on the Home Page grid and the main `/projects/` page.

- **Where to find files:** `_projects/`
- **File Naming Format:** `project-title.md` (e.g., `ecg-cardiomyopathies.md`)

```markdown
---
layout: page
title: "Explainable AI for ECG-based Screening of Cardiomyopathies"
description: "This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures..."
img: assets/img/asugi.png
logo: true
external_link: https://asugi.sanita.fvg.it/it/schede/UniTS/index.html
importance: 1
category: work
preview: assets/img/news/asugi.png
related_publications:
  - sharifi2026waveslab
---

This study aims to develop explainable machine-learning and deep-learning models to identify ECG-derived signatures associated with cardiomyopathies... The study is carried out in collaboration with ASUGI–Cattinara.
```

> **Note:** `importance: 1` places the project at the top of the list. Higher numbers appear further down. To connect a publication, list its BibTeX key under `related_publications`.

---

## 5. GitHub & Software Repositories (`_data/repositories.yml`)

Displays open-source codebases, tools, and datasets created by WAVESLAB. Open `_data/repositories.yml` and update user/repo lists:

```yaml
github_users:
  - shayanever
  - CisottoGiulia
  - jesus-333

repo_description_lines_max: 2

github_repos:
  - name: EEG-EMG-analytics
    user: CisottoGiulia
    description: "Analytics pipeline and toolsets for synchronized EEG and EMG signal processing."
    related_publications:
      - sharifi2026waveslab

  - name: Variational-Autoencoder-for-EEG-analysis
    user: jesus-333
    description: "Deep learning architecture based on VAEs for feature extraction from EEG data."
    related_publications:
      - sharifi2026waveslab

  - name: ecg-Rpeak-validation-neurokit
    user: shayanever
    description: "Validation tools for ECG R-peak detection benchmarking against NeuroKit2."
    related_publications:
      - sharifi2026waveslab

  - name: Sleep-Apnea-and-Hypopnea-Detection
    user: shayanever
    description: "Machine learning framework for automated sleep apnea and hypopnea detection."
    related_publications:
      - sharifi2026waveslab
```

---

## 6. Collaborations (`_pages/collaborations.md`)

Manages partner institutions, clinical partners, and university lab networks categorized by group (e.g., Academia, Hospitals). Open `_pages/collaborations.md` and add collaborator blocks under the appropriate section header:

```yaml
- name: "Prof. Leonardo Badia"
  institution: "University of Padova"
  location: "Padova, Italy"
  address: "Via Gradenigo 6/b, 35131 Padova, Italy"
  image: "" # e.g., badia.jpg in assets/img/
  website: "https://www.dei.unipd.it/~badia/"
  linkedin: "leonardo-badia"
  github: ""
  scholar: ""
  email: "badia@dei.unipd.it"
  phone: ""
  description: "Collaborating on bio-signal processing algorithms and communication frameworks."
```

---

## 7. Join Us / Opportunities (`_data/positions.yml`)

Houses open calls for PhD candidates, postdocs, master's thesis projects, and visiting researchers. Open `_data/positions.yml` and add or edit position listings:

```yaml
- title: "PhD Position in Neural Signal Modeling"
  deadline: "October 15, 2026"
  location: "Trieste, Italy"
  description: "We are seeking a motivated PhD candidate with a strong background in biomedical engineering or machine learning..."
```

---

## 8. Contact Information (`_data/contact.yml`)

Contains lab location, directions, and official contact email addresses. Open `_data/contact.yml` and update the values:

```yaml
address: "Department of Engineering and Architecture, University of Trieste, Italy"
email: "info@waveslab.org"
```

---

## 9. Social Media & Videos (`_data/videos.yml` & `_pages/social.md`)

### Adding Featured YouTube Videos

Open `_data/videos.yml` and add a new video block:

```yaml
- title: "QUALI SONO I MISTERI DELL'EEG?"
  presenter: "Dr. Giulia Cisotto"
  youtube_id: "CGOohNAe868"

- title: "Comprendere o calcolare? Al confine tra intelligenza umana e artificiale"
  presenter: "Dr. Giulia Cisotto and Dr. F. Anselmi"
  youtube_id: "WEGKDRCsB6U"
```

- **`youtube_id`:** The unique string at the end of the YouTube URL (e.g., in `youtube.com/watch?v=CGOohNAe868`, the ID is `CGOohNAe868`).

### Updating Social Links

Open `_pages/social.md` to update official channel URLs or change status badges when accounts go live.

---

## 10. Events, Seminars & Courses (`_pages/events.md` & `_teachings/`)

### Calendar Integration (`_pages/events.md`)

To change the embedded Google Calendar, open `_pages/events.md` and swap the `src` attribute inside the `<iframe>` tag:

```html
<div class="calendar-container my-4">
  <iframe 
    src="https://calendar.google.com/calendar/embed?src=en.italian%23holiday%40group.v.calendar.google.com&amp;ctz=Europe%2FRome" 
    style="border: 0; width: 100%; height: 600px; border-radius: 8px;" 
    frameborder="0" 
    scrolling="no">
  </iframe>
</div>
```

### Course & Teaching Details (`_teachings/`)

To add detailed course syllabi, lecture notes, or workshop materials:

1. Navigate to `_teachings/`.
2. Create a new `.md` file (e.g., `biosignal-processing-2026.md`).
3. Fill in course metadata and content using standard Markdown like samples.

---

## Quick Markdown Formatting Cheat Sheet

| Style | Syntax Example | Output Result |
| :--- | :--- | :--- |
| **Bold Text** | `**sample text**` | **sample text** |
| *Italic Text* | `*sample text*` | *sample text* |
| **Header Level 2** | `## Section Title` | **Sub-section heading** |
| **Header Level 3** | `### Subsection Title` | **Minor section heading** |
| **Web Link** | `[WavesLab Website](https://shayansharifi.net/waveslab/)` | [WavesLab Website](https://shayansharifi.net/waveslab/) |
| **Bullet Points** | `- First item`<br>`- Second item` | • First item<br>• Second item |

---

## Summary Cheatsheet: File Locations & Formats

| Menu Item | File / Directory | Format | Key Function |
| :--- | :--- | :--- | :--- |
| **Home** | `index.html` / `_includes/` | HTML / JS | Banner text & main landing page cards |
| **News** | `_posts/` | Markdown (`.md`) | Posts announcements & talk details |
| **Team** | `_pages/_profile.md` & `_pages/_people/` | YAML / Markdown | Member roster & bio pages |
| **Publications** | `_bibliography/papers.bib` | BibTeX (`.bib`) | Dynamic publication library |
| **Projects** | `_projects/` | Markdown (`.md`) | Research track descriptions |
| **GitHub** | `_data/repositories.yml` | YAML (`.yml`) | Open-source GitHub repositories |
| **Collaborations** | `_pages/collaborations.md` | Markdown / YAML | Partner institutions & researchers |
| **Join us** | `_data/positions.yml` | YAML (`.yml`) | Open PhD & Postdoc vacancy calls |
| **Contact** | `_data/contact.yml` | YAML (`.yml`) | Lab address & email details |
| **Social Media** | `_data/videos.yml` & `_pages/social.md` | YAML / Markdown | Featured talks & official channel links |
| **Events** | `_pages/events.md` & `_teachings/` | HTML / Markdown | Google Calendar & course materials |

---

<p align="center">
  Prepared by <a href="http://shayansharifi.net" target="_blank">Shayan Sharifi</a>, WAVESLAB, 2026<br>
  <em>Last Updated: July 2026</em>
</p>
readme.md
Displaying readme.md.
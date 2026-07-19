---
layout: page
permalink: /events/
title: events
description: Course materials, schedules, and resources for classes taught.
nav: true
nav_order: 6
calendar: true
---

This page displays a collection of courses with detailed schedules, materials, and resources. You can organize your courses by years, terms, or topics.

{% include calendar.liquid calendar_id='test@gmail.com' timezone='Asia/Shanghai' %}

{% include courses.liquid %}
<link rel="stylesheet" href="{{ '/assets/css/theme-override.css' | relative_url }}">
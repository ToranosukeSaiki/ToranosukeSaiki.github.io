---
layout: default
title: "Works"
---

<div class="works-grid">
{% assign works = site.works %}
{% for work in works %}
  <a href="{{ work.url }}" class="work-item">
    <img src="{{ work.thumbnail }}" alt="{{ work.title }}">
  </a>
{% endfor %}
</div>
---
layout: page
title: Blog
permalink: /blog/
---

<style>
  .article-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); /* 3つ並び（画面幅に応じて自動調整） */
    gap: 20px;
    list-style: none;
    padding: 0;
  }
  .article-card {
    border: 1px solid #eee;
    border-radius: 12px;
    overflow: hidden;
    transition: transform 0.2s;
  }
  .article-link {
    text-decoration: none;
    color: inherit;
  }
  .article-link:hover, 
  .article-link:focus, 
  .article-link:active {
    text-decoration: none !important; /* ホバー・選択時も下線を絶対に出さない */
  }
  .thumbnail-wrapper {
    width: 100%;
    aspect-ratio: 16 / 9; /* 横長で統一 */
    overflow: hidden;
    background: #f0f0f0;
    border-radius: 12px;
  }
  .thumbnail-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .article-content {
    padding: 15px;
  }
  .article-title {
    font-size: 1.1em !important;
    color: #333333;
    margin: 0 0 10px 0;
    line-height: 1.2;
  }
  .article-date {
    font-size: 0.85em;
    color: #888;
  }
</style>

<ul class="article-grid">
  {% for post in site.posts %}
    <li class="article-card">
      <a href="{{ post.url | relative_url }}" class="article-link">
        <div class="thumbnail-wrapper">
          {% if post.thumbnail %}
            <img src="{{ post.thumbnail | relative_url }}" alt="{{ post.title }}">
          {% else %}
            <div style="display: flex; align-items: center; justify-content: center; height: 100%; color: #ccc;">No Image</div>
          {% endif %}
        </div>
        <div class="article-content">
          <h3 class="article-title">{{ post.title }}</h3>
          <p class="article-date">{{ post.date | date: "%Y/%m/%d" }}公開</p>
        </div>
      </a>
    </li>
  {% endfor %}
</ul>
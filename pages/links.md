---
layout: default
title: 友邻
description: 有趣的博客与站点收藏
keywords: 友情链接, 友邻, 博客
comments: false
menu: 友邻
permalink: /links/
---

<header class="page-hero">
  <h1>友邻</h1>
  <p class="page-hero__sub">有趣的博客与站点收藏</p>
</header>

<section class="section">
  <div class="container">
    <div class="friends-grid">
    {% for link in site.data.links %}
      <a href="{{ link.url }}" target="_blank" rel="noopener" class="friend-card">
        <span class="friend-name">{{ link.name }}</span>
        <span class="friend-url">{{ link.url | remove: 'http://' | remove: 'https://' }}</span>
      </a>
    {% endfor %}
    </div>
  </div>
</section>

<style>
.friends-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 1rem;
}
.friend-card {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  padding: 1.2rem 1.4rem;
  border: 1px solid var(--border);
  border-radius: 12px;
  text-decoration: none;
  transition: border-color 0.2s, transform 0.2s, box-shadow 0.2s;
}
.friend-card:hover {
  border-color: var(--accent);
  transform: translateY(-3px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.2);
}
.friend-name {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text);
}
.friend-url {
  font-size: 0.78rem;
  color: var(--text-muted);
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
</style>

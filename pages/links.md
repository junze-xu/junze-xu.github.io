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
      <a href="{{ link.url }}" target="_blank" rel="noopener" class="friend-card" style="--lc: {{ link.color | default: '#14b8a6' }};">
        <span class="friend-name">{{ link.name }}</span>
        <span class="friend-url">{{ link.url | remove: 'http://' | remove: 'https://' }}</span>
      </a>
    {% endfor %}
    </div>
  </div>
</section>

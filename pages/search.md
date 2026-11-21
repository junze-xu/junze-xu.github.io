---
layout: default
title: 搜索
description: 全站文章搜索
comments: false
permalink: /search/
---

<header class="page-hero">
  <h1>搜索</h1>
  <p class="page-hero__sub">在全站文章中检索</p>
</header>

<section class="section">
  <div class="container" style="max-width: 680px;">

    <div style="position: relative; margin-bottom: 2rem;">
      <input
        type="text"
        id="search-input"
        placeholder="输入关键词搜索..."
        autocomplete="off"
        style="
          width: 100%;
          padding: 0.9rem 1.2rem 0.9rem 2.8rem;
          background: var(--bg-card);
          border: 1px solid var(--border);
          border-radius: 50px;
          color: var(--text);
          font-size: 0.95rem;
          font-family: var(--font-sans);
          outline: none;
          transition: border-color 0.2s;
        "
        onfocus="this.style.borderColor='var(--accent)'"
        onblur="this.style.borderColor='var(--border)'"
      >
      <span style="position: absolute; left: 1rem; top: 50%; transform: translateY(-50%); color: var(--text-muted);">🔍</span>
    </div>

    <div id="search-results">
      <p style="color: var(--text-muted); text-align: center; padding: 2rem 0;">输入关键词开始搜索</p>
    </div>
  </div>
</section>

<script>window.searchJsonUrl = '{{ "/search.json" | relative_url }}';</script>
<script src="{{ 'assets/js/search.js' | relative_url }}" defer></script>

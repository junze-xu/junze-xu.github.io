---
layout: default
title: 归档
description: 按主题与时间线浏览全部文章
keywords: 归档, archives, 分类
comments: false
permalink: /archives/
---

<section class="section">
  <div class="container" style="max-width: 820px;">

    <!-- 头部：定位语 + 规模统计 + 搜索入口 -->
    <header class="archive-header">
      <p class="archive-kicker"><span class="gradient-text">深入 AI 的开发、研究与分析</span></p>
      <h1>归档</h1>
      <p class="archive-sub">按主题与时间线浏览全部文章</p>
      <div class="archive-stats">
        <span><strong>{{ site.posts.size }}</strong> 篇文章</span>
        <span class="divider">·</span>
        <span><strong>{{ site.wiki.size }}</strong> 篇速查手册</span>
      </div>
      <div class="archive-actions">
        <a href="{{ '/search/' | relative_url }}" class="cta-btn">🔍 全文搜索</a>
        <a href="{{ '/wiki/' | relative_url }}" class="cta-btn ghost">笔记速查 Wiki →</a>
      </div>
    </header>

    <!-- 文章分类 -->
    <h2 class="archive-section-title">文章分类</h2>
    {% assign sorted_categories = site.categories | sort %}
    <div class="cat-nav-grid">
      {% for category in sorted_categories %}
      <a href="#cat-{{ category[0] }}" class="cat-nav-card">{{ category[0] }}<span class="count">{{ category[1].size }}</span></a>
      {% endfor %}
    </div>
    <div class="cat-listing">
      {% for category in sorted_categories %}
      <div class="category-block" id="cat-{{ category[0] }}">
        <h3>{{ category[0] }} <span class="cat-count">{{ category[1].size }} 篇</span></h3>
        <ul class="category-list">
          {% for post in category.last %}
          <li>
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <span class="post-date">{{ post.date | date: '%Y-%m-%d' }}</span>
          </li>
          {% endfor %}
        </ul>
      </div>
      {% endfor %}
    </div>

    <!-- 时间线 -->
    <h2 class="archive-section-title">时间线</h2>
    {% assign thisyear = 0 %}
    {% for post in site.posts %}
      {% assign year = post.date | date: '%Y' %}
      {% if year != thisyear %}
        {% if thisyear != 0 %}</ul>{% endif %}
        <h3 class="tl-year">{{ year }}</h3>
        <ul class="tl-list">
        {% assign thisyear = year %}
      {% endif %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <span class="tl-date">{{ post.date | date: '%m-%d' }}</span>
      </li>
    {% endfor %}
    {% if thisyear != 0 %}</ul>{% endif %}
  </div>
</section>

<style>
.archive-header {
  text-align: center;
  padding: 1rem 0 3rem;
}
.archive-kicker {
  font-size: 0.95rem;
  letter-spacing: 0.02em;
  margin-bottom: 0.75rem;
}
.archive-header h1 {
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
}
.archive-sub {
  color: var(--text-secondary);
  font-size: 0.95rem;
}
.archive-stats {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  margin: 1.1rem 0 1.4rem;
  font-size: 0.9rem;
  color: var(--text-muted);
}
.archive-stats strong {
  color: var(--accent);
  font-size: 1rem;
}
.archive-stats .divider {
  color: var(--border);
}
.archive-actions {
  display: flex;
  gap: 0.9rem;
  justify-content: center;
  flex-wrap: wrap;
}
.archive-section-title {
  font-size: 1.3rem;
  font-weight: 700;
  margin: 3rem 0 1.5rem;
  padding-left: 0.7rem;
  border-left: 3px solid var(--accent);
}
@media (max-width: 768px) {
  .archive-header {
    padding-bottom: 2rem;
  }
  .archive-header h1 {
    font-size: 1.6rem;
  }
}
</style>

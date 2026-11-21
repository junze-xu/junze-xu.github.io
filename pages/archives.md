---
layout: default
title: 归档
description: 按主题与时间线浏览全部文章
keywords: 归档, archives, 分类
comments: false
permalink: /archives/
---

<header class="page-hero">
  <p class="page-hero__kicker"><span class="gradient-text">深入 AI 的开发、研究与分析</span></p>
  <h1>归档</h1>
  <p class="page-hero__sub">按主题与时间线浏览全部文章</p>
  <div class="page-hero__meta">
    <span><strong>{{ site.posts.size }}</strong> 篇文章</span>
    <span class="divider">·</span>
    <span><strong>{{ site.wiki.size }}</strong> 篇速查手册</span>
  </div>
  <div class="page-hero__actions">
    <a href="{{ '/search/' | relative_url }}" class="cta-btn">🔍 全文搜索</a>
  </div>
</header>

<section class="section">
  <div class="container" style="max-width: 820px;">

    <!-- 文章分类 -->
    <div class="section-header">
      <h2>分类</h2>
      <p>按主题浏览全部文章</p>
    </div>
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
    <div class="section-header">
      <h2>时间线</h2>
      <p>按年份浏览全部文章</p>
    </div>
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

---
layout: projects
title: 项目
subtitle: 以下项目均已部署到 GitHub Pages 并持续更新，涵盖个人博客、AI 认证备考、数据榜单与效率工具。
description: Junze Xu 的公开项目合集——个人博客、NVIDIA 认证笔记、GitHub Trending 周榜、Grok Bot 模板库
keywords: Junze Xu, 项目合集, GitHub Pages, NVIDIA 认证, GitHub Trending, Grok Bot
comments: false
menu: 项目
permalink: /projects/
css: [projects.css]
---

<div class="projects-hub">
{% for project in site.data.portfolio.projects %}
  <div class="hub-card">
    {% if project.link %}
    <a class="stretched-link" href="{{ project.link }}" target="_blank" rel="noopener" aria-label="访问 {{ project.title }}"></a>
    {% endif %}
    <div class="hub-cover" style="--pc: {{ project.color | default: '#2a2a3e' }};">
      <span class="emoji">{{ project.emoji }}</span>
    </div>
    <div class="hub-info">
      <span class="hub-tag">{{ project.tag }}</span>
      <h3>{{ project.title }}</h3>
      <p class="desc">{{ project.description }}</p>
      <div class="tech">{{ project.tech }}</div>
      <div class="hub-links">
        {% if project.link %}
        <a href="{{ project.link }}" target="_blank" rel="noopener" class="hub-primary">访问站点 →</a>
        {% endif %}
        {% if project.repo %}
        <a href="{{ project.repo }}" target="_blank" rel="noopener">GitHub 仓库</a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>

---
layout: page
title: 项目
description: Junze Xu 的公开项目合集——个人博客、NVIDIA 认证笔记、GitHub Trending 周榜、Grok Bot 模板库
keywords: Junze Xu, 项目合集, GitHub Pages, NVIDIA 认证, GitHub Trending, Grok Bot
comments: false
menu: 项目
permalink: /projects/
---

<p style="margin-top: 1rem; line-height: 1.9;">
  这里是我在 GitHub 上挑选的公开项目，均已部署到 GitHub Pages，后续会持续补充。
</p>

<div class="projects-hub">
{% for project in site.data.portfolio.projects %}
  <div class="hub-card">
    <div class="hub-cover">
      <span class="emoji">{{ project.emoji }}</span>
    </div>
    <div class="hub-info">
      <span class="hub-tag">{{ project.tag }}</span>
      <h3>{{ project.title }}</h3>
      <p class="desc">{{ project.description }}</p>
      <div class="tech">{{ project.tech }}</div>
      <div class="hub-links">
        {% if project.link %}
        <a href="{{ project.link }}" target="_blank" rel="noopener" class="stretched-link">访问站点 →</a>
        {% endif %}
        {% if project.repo %}
        <a href="{{ project.repo }}" target="_blank" rel="noopener">GitHub 仓库</a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>

<style>
.projects-hub {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}
.hub-card {
  position: relative; /* 供内部链接 ::after 撑满整卡 */
  cursor: pointer;
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: transform 0.3s, border-color 0.3s;
}
.hub-card:hover {
  transform: translateY(-4px);
  border-color: var(--border-hover);
}
.hub-cover {
  height: 130px;
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  display: flex;
  align-items: center;
  justify-content: center;
}
.hub-cover .emoji { font-size: 2.8rem; }
.hub-info { padding: 1.4rem; }
.hub-tag {
  display: inline-block;
  padding: 0.2rem 0.6rem;
  background: rgba(244, 63, 94, 0.1);
  color: var(--accent);
  border-radius: 4px;
  font-size: 0.68rem;
  font-weight: 600;
  letter-spacing: 0.05em;
  margin-bottom: 0.6rem;
}
.hub-info h3 {
  font-size: 1.08rem;
  font-weight: 700;
  margin-bottom: 0.45rem;
}
.hub-info .desc {
  color: var(--text-secondary);
  font-size: 0.85rem;
  line-height: 1.6;
  margin-bottom: 0.9rem;
}
.hub-info .tech {
  font-size: 0.72rem;
  color: var(--text-muted);
  font-family: var(--font-mono);
  padding-top: 0.7rem;
  border-top: 1px solid var(--border);
  margin-bottom: 0.9rem;
}
.hub-links {
  display: flex;
  gap: 0.8rem;
  flex-wrap: wrap;
}
.hub-links a {
  font-size: 0.8rem;
  color: var(--accent);
  text-decoration: none;
}
.hub-links a:hover { text-decoration: underline; }
.hub-links a:last-child {
  position: relative; /* 保持在整卡遮罩之上，仍可单独点 GitHub */
  z-index: 4;
}
</style>

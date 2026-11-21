---
layout: default
title: 关于
description: Junze Xu ——深入 AI 的开发、研究与分析，聚焦 AI Infra 与 LLM 应用
keywords: Junze Xu, 作品集, AI Infra, LLM, 技术博客
comments: false
menu: 关于
permalink: /about/
---

<div class="about-page">

<!-- 统一页头 -->
<header class="page-hero">
  <h1>你好，我是 <span class="gradient-text">Junze Xu</span></h1>
  <p class="page-hero__sub">深入 AI 的开发、研究与分析 · AI Infra 工程实践<br>记录技术思考与开发实践</p>
</header>

<!-- Skills -->
<section class="section" id="skills">
  <div class="container">
    <div class="section-header">
      <h2>Skills</h2>
      <p>我的技术栈</p>
    </div>
    <div class="skills-grid">
      {% for skill in site.data.skills %}
      <div class="skill-item">
        <div class="skill-header">
          <span class="skill-name">{{ skill.name }}</span>
          <span class="skill-level">{{ skill.level }}%</span>
        </div>
        <div class="skill-bar">
          <div class="skill-bar-fill" style="width: {{ skill.level }}%"></div>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</section>

<!-- Contact -->
<section class="contact" id="contact">
  <h2>让我们一起创造 ✨</h2>
  <p>如果你也有一个想法想做成，欢迎来找我聊聊</p>
  <div class="contact-links">
    <a href="mailto:{{ site.email }}">📧 Email</a>
    <a href="https://github.com/{{ site.github_username }}" target="_blank">🐙 GitHub</a>
    {% for social in site.data.social %}
    <a href="{{ social.url }}" target="_blank">{{ social.sitename }}</a>
    {% endfor %}
  </div>
</section>

</div>

<style>
/* ===== 关于页专属布局 ===== */
/* 模块间距收紧 */
.about-page .section { padding: 2.5rem 0; }
.about-page .section-header { margin-bottom: 1.75rem; }
.about-page .contact { padding: 3rem 2rem; }
@media (max-width: 768px) {
  .about-page .section { padding: 2rem 0; }
  .about-page .contact { padding: 2.5rem 1.25rem; }
}
</style>

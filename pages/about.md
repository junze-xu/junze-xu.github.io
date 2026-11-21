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

<!-- Hero -->
<section class="about-hero">
  <h1>你好，我是 <span class="gradient-text">Junze Xu</span></h1>
  <p>深入 AI 的开发、研究与分析 · AI Infra 工程实践<br>记录技术思考与开发实践</p>
</section>

<!-- Projects -->
<section class="section" id="projects">
  <div class="container">
    <div class="section-header">
      <h2>Projects</h2>
      <p>精选代表项目，完整卡片统一放在项目页</p>
    </div>
    <div class="about-projects-cta">
      <a class="cta-btn" href="{{ '/projects/' | relative_url }}">查看全部项目 →</a>
    </div>
  </div>
</section>

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
.about-hero {
  position: relative;
  text-align: center;
  padding: 3.5rem 2rem 2rem;
  overflow: hidden;
}
.about-hero::before {
  content: '';
  position: absolute;
  top: -30%;
  left: -20%;
  width: 140%;
  height: 160%;
  background: radial-gradient(circle at 30% 50%, rgba(244, 63, 94, 0.05) 0%, transparent 50%),
              radial-gradient(circle at 70% 50%, rgba(59, 130, 246, 0.05) 0%, transparent 50%);
  pointer-events: none;
}
.about-hero h1 {
  position: relative;
  font-size: clamp(1.9rem, 5vw, 2.6rem);
  font-weight: 800;
  letter-spacing: -0.02em;
  margin-bottom: 1rem;
}
.about-hero p {
  position: relative;
  color: var(--text-secondary);
  font-size: 1rem;
  line-height: 1.8;
}
/* 关于页项目区：只做入口 CTA，不与项目页重复 */
.about-projects-cta { text-align: center; margin-top: 1.5rem; }
/* 模块间距收紧 */
.about-page .section { padding: 2.5rem 0; }
.about-page .section-header { margin-bottom: 1.75rem; }
.about-page .contact { padding: 3rem 2rem; }
@media (max-width: 768px) {
  .about-hero { padding: 2.5rem 1.25rem 1.5rem; }
  .about-page .section { padding: 2rem 0; }
  .about-page .contact { padding: 2.5rem 1.25rem; }
}
</style>

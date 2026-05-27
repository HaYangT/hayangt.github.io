---
layout: page
title: "index"
permalink: /
---

{% assign profile = site.data.portfolio.profile %}
{% assign featured_project = site.data.portfolio.projects | where: "featured", true | first %}

<div class="portfolio-page landing">
  <section class="portfolio-hero">
    <p class="portfolio-kicker">Software Engineer</p>
    <h1>{{ profile.name }}</h1>
    <p class="portfolio-lead">{{ profile.headline }}</p>
    <p class="portfolio-summary">{{ profile.greeting }}</p>
    <blockquote class="portfolio-quote">{{ profile.summary }}</blockquote>
    <div class="portfolio-actions">
      <a class="portfolio-button primary" href="{{ '/portfolio/' | relative_url }}">Portfolio</a>
      <a class="portfolio-button" href="{{ '/posts/' | relative_url }}">Blog</a>
      <a class="portfolio-button" href="{{ profile.github }}" target="_blank" rel="noopener">GitHub</a>
    </div>
  </section>

  <section class="portfolio-section">
    <h2>What I do</h2>
    <div class="portfolio-skill-grid">
      {% for skill in site.data.portfolio.skills %}
        <article class="portfolio-card">
          <h3>{{ skill.name }}</h3>
          <ul class="portfolio-tag-list">
            {% for item in skill.items %}
              <li>{{ item }}</li>
            {% endfor %}
          </ul>
        </article>
      {% endfor %}
    </div>
  </section>

  {% if featured_project %}
    <section class="portfolio-section">
      <h2>Featured Project</h2>
      <article class="portfolio-project">
        <div class="portfolio-project-header">
          <div>
            <p class="portfolio-meta">{{ featured_project.period }}</p>
            <h3>{{ featured_project.title }}</h3>
            <p class="portfolio-project-tagline">{{ featured_project.tagline }}</p>
          </div>
          <p class="portfolio-role">{{ featured_project.role }}</p>
        </div>
        <p>{{ featured_project.description }}</p>
        <ul class="portfolio-highlight-list">
          {% for contribution in featured_project.contributions limit: 3 %}
            <li>{{ contribution.title }}</li>
          {% endfor %}
        </ul>
        <div class="portfolio-links">
          <a href="{{ '/portfolio/' | relative_url }}">프로젝트 자세히</a>
          {% for link in featured_project.links %}
            <a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>
          {% endfor %}
        </div>
      </article>
    </section>
  {% endif %}

  <section class="portfolio-section">
    <h2>Contact</h2>
    <div class="portfolio-contact">
      <a href="{{ profile.github }}" target="_blank" rel="noopener">GitHub</a>
      <a href="mailto:{{ profile.email }}">{{ profile.email }}</a>
      <a href="tel:{{ profile.mobile | remove: '-' }}">{{ profile.mobile }}</a>
    </div>
  </section>
</div>

---
title: Portfolio
icon: fas fa-diagram-project
order: 1
permalink: /portfolio/
layout: page
---

{% assign profile = site.data.portfolio.profile %}

<div class="portfolio-page">
  <section class="portfolio-hero">
    <p class="portfolio-kicker">Portfolio</p>
    <h1>{{ profile.name }} · {{ profile.role }}</h1>
    <p class="portfolio-lead">{{ profile.headline }}</p>
    <p class="portfolio-summary">{{ profile.summary }}</p>
    <div class="portfolio-actions">
      <a class="portfolio-button primary" href="{{ profile.github }}" target="_blank" rel="noopener">GitHub</a>
      <a class="portfolio-button" href="mailto:{{ profile.email }}">Email</a>
      <a class="portfolio-button" href="{{ '/posts/' | relative_url }}">Blog</a>
    </div>
  </section>

  <section class="portfolio-section">
    <h2>About</h2>
    <div class="portfolio-about">
      {% for item in site.data.portfolio.about %}
        <p>{{ item }}</p>
      {% endfor %}
    </div>
  </section>

  <section class="portfolio-section">
    <h2>Skills</h2>
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

  <section class="portfolio-section">
    <h2>Projects</h2>
    <div class="portfolio-project-list">
      {% for project in site.data.portfolio.projects %}
        <article class="portfolio-project">
          <div class="portfolio-project-header">
            <div>
              <p class="portfolio-meta">{{ project.period }} · {{ project.status }}</p>
              <h3>{{ project.title }}</h3>
              <p class="portfolio-project-tagline">{{ project.tagline }}</p>
            </div>
            <p class="portfolio-role">{{ project.role }}</p>
          </div>
          <p>{{ project.description }}</p>
          <ul class="portfolio-highlight-list">
            {% for highlight in project.highlights %}
              <li>{{ highlight }}</li>
            {% endfor %}
          </ul>
          <ul class="portfolio-tag-list">
            {% for item in project.stack %}
              <li>{{ item }}</li>
            {% endfor %}
          </ul>
          {% if project.links %}
            <div class="portfolio-links">
              {% for link in project.links %}
                <a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>
              {% endfor %}
            </div>
          {% endif %}
        </article>
      {% endfor %}
    </div>
  </section>

  <section class="portfolio-section">
    <h2>Next</h2>
    <ul class="portfolio-next-list">
      {% for item in site.data.portfolio.next_steps %}
        <li>{{ item }}</li>
      {% endfor %}
    </ul>
  </section>
</div>

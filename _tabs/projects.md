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
    <blockquote class="portfolio-quote">{{ profile.summary }}</blockquote>
    <div class="portfolio-actions">
      <a class="portfolio-button primary" href="{{ profile.github }}" target="_blank" rel="noopener">GitHub</a>
      <a class="portfolio-button" href="mailto:{{ profile.email }}">Email</a>
      <a class="portfolio-button" href="{{ '/posts/' | relative_url }}">Blog</a>
    </div>
    <dl class="portfolio-contact-list">
      <div>
        <dt>Email</dt>
        <dd><a href="mailto:{{ profile.email }}">{{ profile.email }}</a></dd>
      </div>
      <div>
        <dt>GitHub</dt>
        <dd><a href="{{ profile.github }}" target="_blank" rel="noopener">{{ profile.github }}</a></dd>
      </div>
    </dl>
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
              <p class="portfolio-meta">{{ project.period }}</p>
              <h3>{{ project.title }}</h3>
              <p class="portfolio-project-tagline">{{ project.tagline }}</p>
            </div>
            <p class="portfolio-role">{{ project.role }}</p>
          </div>
          <p class="portfolio-organization">{{ project.organization }}</p>
          <p>{{ project.description }}</p>
          <div class="portfolio-contribution-list">
            {% for contribution in project.contributions %}
              <div class="portfolio-contribution">
                <span>{{ forloop.index }}</span>
                <div>
                  <h4>{{ contribution.title }}</h4>
                  <p>{{ contribution.body }}</p>
                </div>
              </div>
            {% endfor %}
          </div>
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
    <h2>Research</h2>
    <article class="portfolio-project">
      <p class="portfolio-meta">{{ site.data.portfolio.research.period }}</p>
      <p>{{ site.data.portfolio.research.description }}</p>
      <div class="portfolio-contribution-list">
        {% for item in site.data.portfolio.research.items %}
          <div class="portfolio-contribution">
            <span>{{ forloop.index }}</span>
            <div>
              <h4>{{ item.title }}</h4>
              <p>{{ item.body }}</p>
            </div>
          </div>
        {% endfor %}
      </div>
    </article>
  </section>

  <section class="portfolio-section">
    <h2>Education</h2>
    <article class="portfolio-card portfolio-education">
      <h3>{{ site.data.portfolio.education.school }}</h3>
      <p>{{ site.data.portfolio.education.major }}</p>
      <p>{{ site.data.portfolio.education.period }} · {{ site.data.portfolio.education.status }} · GPA {{ site.data.portfolio.education.gpa }}</p>
    </article>
  </section>

  <section class="portfolio-section">
    <h2>Skills Detail</h2>
    <div class="portfolio-project-list">
      {% for skill in site.data.portfolio.skill_details %}
        <article class="portfolio-card">
          <h3>{{ skill.name }}</h3>
          <ul class="portfolio-detail-list">
            {% for detail in skill.details %}
              <li>{{ detail }}</li>
            {% endfor %}
          </ul>
        </article>
      {% endfor %}
    </div>
  </section>

  <section class="portfolio-section">
    <h2>Others</h2>
    <div class="portfolio-skill-grid">
      <article class="portfolio-card">
        <h3>{{ site.data.portfolio.extras.competitive_programming.title }}</h3>
        <ul class="portfolio-detail-list">
          {% for item in site.data.portfolio.extras.competitive_programming.items %}
            <li>{{ item }}</li>
          {% endfor %}
        </ul>
      </article>
      <article class="portfolio-card">
        <h3>{{ site.data.portfolio.extras.awards.title }}</h3>
        <ul class="portfolio-detail-list">
          {% for item in site.data.portfolio.extras.awards.items %}
            <li>{{ item }}</li>
          {% endfor %}
        </ul>
      </article>
    </div>
  </section>

  <p class="portfolio-closing">{{ site.data.portfolio.closing }}</p>
</div>

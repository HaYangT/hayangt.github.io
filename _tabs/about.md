---
title: About
icon: fas fa-user
order: 3
permalink: /about/
---

{% assign profile = site.data.portfolio.profile %}

## 반갑습니다.

SW 엔지니어 {{ profile.name }}입니다.

> {{ profile.summary }}

{% for item in site.data.portfolio.about %}
- {{ item }}
{% endfor %}

## Tech Stack

{% for skill in site.data.portfolio.skills %}
- **{{ skill.name }}**: {{ skill.items | join: ", " }}
{% endfor %}

## Education

- **{{ site.data.portfolio.education.school }} {{ site.data.portfolio.education.major }}**
- {{ site.data.portfolio.education.period }} · {{ site.data.portfolio.education.status }} · GPA {{ site.data.portfolio.education.gpa }}

## Awards

{% for item in site.data.portfolio.extras.awards.items %}
- {{ item }}
{% endfor %}

## Contact

- Mobile: {{ profile.mobile }}
- GitHub: [{{ profile.github }}]({{ profile.github }})
- Email: [{{ profile.email }}](mailto:{{ profile.email }})

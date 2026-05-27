---
title: About
icon: fas fa-user
order: 3
permalink: /about/
---

{% assign profile = site.data.portfolio.profile %}

## {{ profile.name }}

{{ profile.summary }}

{% for item in site.data.portfolio.about %}
- {{ item }}
{% endfor %}

## Tech Stack

{% for skill in site.data.portfolio.skills %}
- **{{ skill.name }}**: {{ skill.items | join: ", " }}
{% endfor %}

## Contact

- GitHub: [{{ profile.github }}]({{ profile.github }})
- Email: [{{ profile.email }}](mailto:{{ profile.email }})

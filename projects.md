---
layout: page
title: Projects
permalink: /projects/
---

# My Projects

Below is a collection of various electrical engineering and tech projects I've worked on.

{% for project in site.projects %}
## [{{ project.title }}]({{ project.url }})
{{ project.description }}

{% if project.image %}
![{{ project.title }}]({{ project.image }})
{% endif %}

---
{% endfor %}

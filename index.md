---
layout: home
title: Home
---

# Volodymyr

**Electrical Engineering Student | Tech Enthusiast**

## About Me

I'm a 3rd year EE student at University. I'm passionate about building circuits in my home lab, reading books on technology and science, listening to podcasts like Darknet Diaries, staying active at the gym, and capturing the world through photography.

## Featured Projects

{% for project in site.projects limit:3 %}
### [{{ project.title }}]({{ project.url }})
{{ project.description }}
{% if project.image %}
![{{ project.title }}]({{ project.image }})
{% endif %}
{% endfor %}

[See all projects](/projects/)

## Recent Blog Posts

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}

[See all posts](/blog/)

## Get in Touch

[Shchuryshyn@protonmail.com](mailto:Shchuryshyn@protonmail.com)

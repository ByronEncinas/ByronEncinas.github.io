---
layout: default
title: Home
---

# Welcome to My Blog

This is the home page of my personal blog built with Jekyll and GitHub Pages.

## Latest Posts

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
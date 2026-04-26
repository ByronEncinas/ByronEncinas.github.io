---
layout: default
title: Home
---

# I wanted a space to present my work, and so here it is!!!

## Latest Posts

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
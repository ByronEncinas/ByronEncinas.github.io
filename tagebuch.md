---
layout: default
title: Tagebuch
---

<h2>Tagebuch</h2>

<p>Kurze Einträge auf Deutsch.</p>

<ul>
{% assign entries = site.tagebuch | sort: "date" | reverse %}
{% for entry in entries %}
	<li>
		<a href="{{ entry.url }}">{{ entry.title }}</a>
		<time datetime="{{ entry.date | date: '%Y-%m-%d' }}">{{ entry.date | date: "%d.%m.%Y" }}</time>
	</li>
{% endfor %}
</ul>


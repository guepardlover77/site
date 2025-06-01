---
layout: default
title: "Tous mes articles"
---

# Tous mes articles

{% for folder in site.data.folders %}
## 📁 {{ folder.name | capitalize }}
{{ folder.description }}

{% assign folder_posts = site.pages | where_exp: "page", "page.path contains folder.path" %}
{% for post in folder_posts limit: 3 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d/%m/%Y" }}
{% endfor %}

[Voir tous les articles {{ folder.name }} →](./{{ folder.path }}/)
{% endfor %}

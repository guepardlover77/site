---
layout: default
title: "Articles Sciences"
category: sciences
---

# Articles de Sciences

{% assign posts = site.posts | where_exp: "post", "post.path contains 'sciences'" %}
{% for post in posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d/%m/%Y" }}
  {% if post.excerpt %}
    <br><em>{{ post.excerpt | strip_html | truncatewords: 20 }}</em>
  {% endif %}
{% endfor %}

{% if posts.size == 0 %}
Aucun article dans cette catégorie pour le moment.
{% endif %}

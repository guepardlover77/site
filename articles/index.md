---
layout: default
title: "Tous mes articles"
---

# 📝 Tous mes articles

{% assign all_articles = site.pages | where_exp: "page", "page.path contains 'articles/'" | where_exp: "page", "page.name != 'index.md'" | sort: "date" | reverse %}

{% if all_articles.size > 0 %}

*{{ all_articles.size }} article(s) au total*

{% for article in all_articles %}
{% if article.title %}

<div class="article-preview">
<h2><a href="{{ article.url | relative_url }}">{{ article.title }}</a></h2>

{% if article.date %}
<p class="article-meta">📅 {{ article.date | date: "%d %B %Y" }}</p>
{% endif %}

{% if article.description %}
<p>{{ article.description }}</p>
{% endif %}

{% if article.tags %}
<div class="tags">
🏷️ {% for tag in article.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
</div>
{% endif %}

<p class="article-meta">📁 Catégorie : 
{% if article.path contains '/technique/' %}💻 Technique
{% elsif article.path contains '/design/' %}🎨 Design  
{% elsif article.path contains '/personnel/' %}✨ Personnel
{% else %}📝 Général{% endif %}
</p>
</div>

{% endif %}
{% endfor %}

{% else %}
<p><em>Aucun article pour le moment.</em></p>
{% endif %}

---

## 🗂️ Parcourir par catégorie

- [💻 Articles techniques](./technique/) 
- [🎨 Articles design](./design/)
- [✨ Articles personnels](./personnel/)

---

[🏠 Retour à l'accueil](../)

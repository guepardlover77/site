---
layout: default
title: "Articles Techniques"
---

# Articles Scientifiques

{% assign technique_articles = site.pages | where_exp: "page", "page.path contains 'articles/technique/'" | where_exp: "page", "page.name != 'index.md'" | sort: "date" | reverse %}

{% if technique_articles.size > 0 %}

*{{ technique_articles.size }} article(s) dans cette catégorie*

{% for article in technique_articles %}
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
</div>

{% endif %}
{% endfor %}

{% else %}
<p><em>Aucun article technique pour le moment.</em></p>
{% endif %}

---

## 📱 Navigation

- [🏠 Accueil](../../)
- [📝 Tous les articles](../)
- [🎨 Articles design](../design/)
- [✨ Articles personnels](../personnel/)

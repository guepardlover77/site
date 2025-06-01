---
layout: default
title: "Accueil"
---

# Bienvenue sur mon blog !

## À propos

Salut ! Je suis [Votre Nom], développeur/designer passionné par la technologie et l'innovation. 

Sur ce blog, je partage :
- 💻 **Mes découvertes techniques** et tutoriels de développement
- 🎨 **Mes réflexions sur le design** et l'expérience utilisateur  
- ✨ **Mes expériences personnelles** et apprentissages

---

## 📝 Articles récents

{% assign recent_articles = site.pages | where_exp: "page", "page.path contains 'articles/'" | where_exp: "page", "page.name != 'index.md'" | sort: "date" | reverse | slice: 0, 5 %}

{% for article in recent_articles %}
{% if article.title %}
### [{{ article.title }}]({{ article.url | relative_url }})
{% if article.date %}*{{ article.date | date: "%d/%m/%Y" }}*{% endif %}

{{ article.description | default: "Nouvel article disponible..." }}

{% if article.tags %}
**Tags :** {% for tag in article.tags %}`{{ tag }}`{% unless forloop.last %} {% endunless %}{% endfor %}
{% endif %}

---
{% endif %}
{% endfor %}

## 🗂️ Catégories

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1rem; margin: 2rem 0;">

<div class="category-card">

### 💻 [Technique](./articles/sciences/)
Articles sur le développement, les outils et les bonnes pratiques.

</div>

<div class="category-card">

### 🎨 [Design](./articles/design/)
Réflexions sur l'UX/UI et le design d'interface.

</div>

<div class="category-card">

### ✨ [Personnel](./articles/personnel/)
Expériences personnelles et apprentissages de vie.

</div>

</div>

---

## 📬 Contact

- **Email** : [votre.email@exemple.com](mailto:votre.email@exemple.com)
- **GitHub** : [@votreusername](https://github.com/votreusername)
- **LinkedIn** : [Votre profil](https://linkedin.com/in/votre-profil)

---

*Dernière mise à jour : {{ site.time | date: "%d/%m/%Y" }}*

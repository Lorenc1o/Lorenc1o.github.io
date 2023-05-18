---
layout: default
title: Catégories
lang: fr
permalink: /categories_fr
en_link: /categories
es_link: /categories_es
---

Ici vous pouvez trouver toutes mes entrées de blog groupées par catégories[^1]:

{% for category in site.categories %}
  <h2>{{ category[0] }}</h2>
  <ul>
    {% for post in category[1] %}
      {% if post.lang == page.lang %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}

[^1]: Toutes les entrées ne sont pas traduites en français. Vous pouvez trouver les entrées en anglais [ici](/categories).
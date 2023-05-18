---
layout: default
title: Categorías
lang: es
permalink: /categories_es
en_link: /categories
fr_link: /categories_fr
---

Aquí puedes encontrar todas mis entradas del blog agrupadas por categorías[^1]:

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

[^1]: No todas las entradas están traducidas al español. Puedes encontrar las entradas en inglés [aquí](/categories).

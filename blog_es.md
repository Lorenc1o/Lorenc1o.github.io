---
layout: base
title: "Blog"
permalink: /blog_es
lang: es
en_link: /blog
fr_link: /blog_fr
---

Aquí están mis entradas del blog en español[^1]:

{% for post in site.posts %}
  {% if post.lang == page.lang %}
  - [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

[^1]: No todas las entradas están traducidas al español. Puedes encontrar las entradas en inglés [aquí](/blog).
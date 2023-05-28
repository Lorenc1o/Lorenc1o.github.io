---
layout: default
title: Categories
lang: en
permalink: /categories
es_link: /categories_es
fr_link: /categories_fr
---

Here you can find all my posts grouped by categories.

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
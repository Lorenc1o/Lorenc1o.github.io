---
layout: base
title: "Blog"
permalink: /blog_fr
lang: fr
es_link: /blog_es
en_link: /blog
---

Voici mes articles de blog en français[^1]:

{% for post in site.posts %}
  {% if post.lang == page.lang %}
  - [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

[^1]: Tous les articles ne sont pas traduits en français. Vous pouvez trouver les articles en anglais [ici](/blog).
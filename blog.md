---
layout: base
title: "Blog"
permalink: /blog/
lang: en
es_link: /blog_es
fr_link: /blog_fr
---

Here are my blog posts:

{% for post in site.posts %}
  {% if post.lang == page.lang %}
  - [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

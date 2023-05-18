---
layout: base
title: "Blog"
permalink: /blog/
lang: en
---

Here are my blog posts:

{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url }})
{% endfor %}

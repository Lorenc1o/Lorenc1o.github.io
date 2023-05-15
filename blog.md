---
layout: page
title: "Blog"
permalink: /blog/
---

Here are my blog posts:

{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url }})
{% endfor %}
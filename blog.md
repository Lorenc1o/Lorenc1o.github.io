---
layout: base
title: "Blog"
permalink: /blog/
lang: en
es_link: /blog_es
fr_link: /blog_fr
---

Here are my blog posts:

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% assign grouped_posts = sorted_posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}

{% for group in grouped_posts %}
## {{ group.name }}
{% for post in group.items %}
  {% if post.lang == page.lang %}
- [{{ post.title }}]({{ post.url | relative_url }})
  {% endif %}
{% endfor %}
{% endfor %}
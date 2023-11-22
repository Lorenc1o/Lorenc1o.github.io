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
<div class="posts-container">
  {% for post in group.items %}
    {% if post.lang == page.lang %}
      <a href="{{ post.url | relative_url }}" class="post-card">
        <div class="post-image">
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        </div>
        <div class="post-title">
          {{ post.title }}
        </div>
      </a>
    {% endif %}
  {% endfor %}
</div>
{% endfor %}
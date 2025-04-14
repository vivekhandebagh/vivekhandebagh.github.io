---
layout: default
title: Blog
permalink: /blog/
---

# Blog Posts

{% for post in site.posts reversed %}
  <article class="post-preview">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
    {% if post.description %}
      <p>{{ post.description }}</p>
    {% else %}
      <p>{{ post.excerpt | strip_html | truncatewords: 250 }}</p>
    {% endif %}
    <a href="{{ post.url | relative_url }}" class="read-more">Read more...</a>
  </article>
  <hr>
{% endfor %} 
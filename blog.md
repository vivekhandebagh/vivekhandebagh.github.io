---
layout: default
title: Blog
permalink: /blog/
---

# Blog Posts
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
  <hr>
{% endfor %}
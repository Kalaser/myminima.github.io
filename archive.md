---
layout: page
title: Archive
permalink: /archive/
---

<div class="archive-list">
  {% for post in site.posts %}
    <div class="archive-item">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-date">{{ post.date | date: "%Y-%m-%d" }}</p>
      <p class="post-excerpt">{{ post.excerpt }}</p>
    </div>
  {% endfor %}
</div>

<style>
.archive-list {
  display: flex;
  flex-direction: column;
}
.archive-item {
  margin-bottom: 20px;
}
.post-date {
  color: #888;
}
.post-excerpt {
  color: #555;
}
</style>
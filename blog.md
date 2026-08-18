---
layout: default
title: Posts
---

<div class="post-section">
  {% for post in site.posts %}
    <a href="{{ post.url }}" class="post-preview-link">
      {% if post.gif %}
        <img src="{{ post.gif }}" alt="{{ post.title }} preview">
      {% endif %}
      <div class="post-info">
        <h2>{{ post.title }}</h2>
        <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
        <p>{{ post.excerpt | strip_html | truncate: 150 }}</p>
      </div>
    </a>
  {% endfor %}
</div>
---
layout: default
title: Home
---

<div align="center">

Here you will find blogs and posts from the perspective of a junior dev. While most of my wisdom is likely questionable and ill advised, I hope my struggles, learning, and growth can provide clarity to those who read.  

The posts you will find will range from projects I create, opinion blogs, and even self reflection. Take what you find with a grain of salt and hint of humor.  

If you wish to reach out to me, please do so via email (amart89531@gmail.com) or via LinkedIn (see bottom of page). I am happy to help out anyone in anyway I can!

</div>

---

<div class="post-section">

  <h2 class="post-section-title">Latest Post</h2>
  {% assign latest_post = site.posts | first %}
  <div class="post-preview">
    {% if latest_post.gif %}
      <img src="/{{ latest_post.gif }}" alt="{{ latest_post.title }}">
    {% endif %}
    <div class="post-info">
      <h2><a href="{{ latest_post.url }}">{{ latest_post.title }}</a></h2>
      <p>{{ latest_post.excerpt | strip_html | truncate: 150 }}</p>
      <p class="post-date">{{ latest_post.date | date: "%B %d, %Y" }}</p>
    </div>
  </div>

  <h2 class="post-section-title">Featured Post</h2>
  {% assign featured_post = site.posts | where: "featured", true | first %}
  {% if featured_post %}
  <div class="post-preview">
    {% if featured_post.gif %}
      <img src="/{{ featured_post.gif }}" alt="{{ featured_post.title }}">
    {% endif %}
    <div class="post-info">
      <h2><a href="{{ featured_post.url }}">{{ featured_post.title }}</a></h2>
      <p>{{ featured_post.excerpt | strip_html | truncate: 150 }}</p>
      <p class="post-date">{{ featured_post.date | date: "%B %d, %Y" }}</p>
    </div>
  </div>
  {% endif %}

</div>
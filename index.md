---
layout: default
title: Home
---

# 👋 Welcome

Hi, I’m **Andrew Martinez** — a Data Scientist & Machine Learning Engineer.  
Here’s what I’ve been writing lately:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small>— {{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>

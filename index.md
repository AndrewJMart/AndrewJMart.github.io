---
layout: default
title: Home
---

<div class="post-section">

  <h2 class="post-section-title">Latest Posts</h2>
  {% for post in site.posts limit: 3 %}
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

  <h2 class="post-section-title">Featured Post</h2>
  {% assign featured_post = site.posts | where: "featured", true | first %}
  {% if featured_post %}
    <a href="{{ featured_post.url }}" class="post-preview-link">
      {% if featured_post.gif %}
        <img src="{{ featured_post.gif }}" alt="{{ featured_post.title }} preview">
      {% endif %}
      <div class="post-info">
        <h2>{{ featured_post.title }}</h2>
        <p class="post-date">{{ featured_post.date | date: "%B %d, %Y" }}</p>
        <p>{{ featured_post.excerpt | strip_html | truncate: 150 }}</p>
      </div>
    </a>
  {% endif %}

</div>

<div class="newsletter-box">
  <h2>Join The Newsletter</h2>
  <p>Get updates on new posts, projects, and behind-the-scenes content.</p>

  <form id="newsletter-form" class="newsletter-form">
    <input 
      type="email" 
      name="email" 
      placeholder="Enter your email..." 
      required 
    />
    <button type="submit">Subscribe</button>
  </form>
</div>

<script>
document.getElementById("newsletter-form").addEventListener("submit", async (e) => {
  e.preventDefault();

  const email = e.target.email.value;

  try {
    const res = await fetch("/newsletter", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ email })
    });

    if (res.ok) {
      alert("Subscribed successfully!");
      e.target.reset();
    } else {
      alert("Subscription failed.");
      console.error(await res.text());
    }
  } catch (err) {
    alert("Error submitting form.");
    console.error(err);
  }
});
</script>

---
layout: page
title: Posts by Tags
permalink: /posts/
---

<!-- Project Section -->
<div class="tag-section">
  <h2 class="tag-title">
    <span class="tag-icon">🚀</span> Project
  </h2>
  <ul class="post-list">
    {% for post in site.posts %}
      {% if post.tags contains "Project" %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
        </li>
      {% endif %}
    {% endfor %}
  </ul>
</div>

---

<!-- Study Section -->
<div class="tag-section">
  <h2 class="tag-title">
    <span class="tag-icon">📘</span> Study
  </h2>
  <ul class="post-list">
    {% for post in site.posts %}
      {% if post.tags contains "Study" %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
        </li>
      {% endif %}
    {% endfor %}
  </ul>
</div>



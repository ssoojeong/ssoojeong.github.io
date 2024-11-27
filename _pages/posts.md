---
layout: page
title: Posts
permalink: /posts/
---

<h1>Posts by Tags</h1>

{% assign tags = site.tags | sort %}
<div class="tags-container">
  {% for tag in tags %}
  <div class="tag-section">
    <h2 class="tag-title">{{ tag[0] }}</h2>
    <ul class="post-list">
      {% for post in tag[1] %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
      </li>
      {% endfor %}
    </ul>
  </div>
  {% endfor %}
</div>


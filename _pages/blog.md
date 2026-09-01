---
layout: default
permalink: /narratives/
title: My narratives
nav: true
nav_order: 5
description: Notes on design, technology, and the small details that shape how we live.
---

<div class="post">
  <div class="header-bar">
    <h1>My narratives</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>

  {% assign narratives = site.posts | where: "narrative", true %}
  {% if narratives.size > 0 %}
    <ul class="post-list">
      {% for post in narratives reversed %}
        <li>
          <h3><a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          {% if post.description %}<p>{{ post.description }}</p>{% endif %}
          <p class="post-meta">{{ post.date | date: '%B %d, %Y' }}</p>
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <div class="card hoverable mt-4">
      <div class="card-body">
        <h3 class="card-title">A space for thinking in public</h3>
        <p class="card-text">New narratives will appear here as I write about design practice, research, and the ideas behind my work.</p>
      </div>
    </div>
  {% endif %}
</div>

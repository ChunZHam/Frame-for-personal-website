---
layout: page
title: Portfolios
permalink: /portfolios/
description: Selected research, editorial, and visual projects.
nav: true
nav_order: 3
---

<style>
  .portfolio-grid { display: grid; grid-template-columns: repeat(6, minmax(0, 1fr)); gap: 1.5rem; }
  .portfolio-card { grid-column: span 2; margin: 0; }
  .portfolio-card:nth-child(4), .portfolio-card:nth-child(5) { grid-column: span 3; }
  .portfolio-frame { display: block; overflow: hidden; aspect-ratio: 4 / 3; border-radius: .75rem; background: #eef1f4; box-shadow: 0 8px 24px rgba(0,0,0,.08); }
  .portfolio-frame img { width: 100%; height: 100%; object-fit: cover; object-position: top center; transition: transform .35s ease; }
  .portfolio-frame:hover img { transform: scale(1.03); }
  @media (max-width: 767px) { .portfolio-grid { display: block; } .portfolio-card { margin-bottom: 1.5rem; } }
</style>

<p>Five selected pieces. Click any image to open the complete long-form artwork.</p>

<div class="portfolio-grid">
  {% assign portfolio_images = "show_717846839_1788345818355.jpg|show_719895557_1788345727940.jpg|show_719367793_1788345756426.jpg|show_719023674_1788345782760.jpg|show_718477953_1788345840963.jpg" | split: "|" %}
  {% for image in portfolio_images %}
    <article class="portfolio-card">
      <a class="portfolio-frame" href="{{ '/assets/img/portfolio/' | append: image | relative_url }}" target="_blank" rel="noopener" aria-label="Open full portfolio image {{ forloop.index }}">
        <img src="{{ '/assets/img/portfolio/' | append: image | relative_url }}" alt="Selected portfolio work {{ forloop.index }}" loading="lazy">
      </a>
      <p class="text-muted mt-2 mb-0">Selected work {{ forloop.index }}</p>
    </article>
  {% endfor %}
</div>

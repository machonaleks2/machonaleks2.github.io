---
layout: work
title: "My work"
permalink: /work/
---

<style>
  ul.posts {
    list-style: none;
    margin: 0; padding: 0;
  }
  ul.posts li {
    border: 1.5px dotted #aaa;
    border-left: none; border-right: none;
    padding: 20px; width: 100%;
    margin: 10px 0; box-sizing: border-box;
  }
  .post-thumb {
    display: block;
    width: clamp(240px, 85vw, 520px);
    max-width: 100%; height: auto;
    margin: 0 0 10px 0;
    border-bottom: 1px dotted #aaa;
  }
  .post-meta { color:#828282; font-size: 14px; }
</style>

<ul class="posts">
  {% assign works = site.categories.work | default: site.tags.work %}
  {% for post in works %}
    <li>
      {% if post.thumbnail %}
        <img
          class="post-thumb"
          src="{{ '/images/' | append: post.thumbnail | relative_url }}"
          alt="{{ post.title | escape }}"
          loading="lazy"
        >
      {% endif %}

      <a class="post-link" href="{{ post.url | relative_url }}"
         style="font-size: 22px; font-weight: 600;">
        {{ post.title }}
      </a>

      
    </li>
  {% endfor %}
</ul>

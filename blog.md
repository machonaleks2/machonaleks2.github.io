---
layout: work
title: "My work"
permalink: /work/
---

<style>
  ul.posts {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  ul.posts li {
    border: 1.5px;
    border-bottom-style: dotted;
    border-top-style: dotted;
    border-left-style: none;
    border-right-style: none;
    display: inline-block;
    padding: 20px;
    width: 100%;
    margin-top: 10px;
    margin-bottom: 10px;
    box-sizing: border-box;
  }
  ul.posts img.post-thumb {
    display: block;
    width: clamp(240px, 85vw, 520px); /* JESZCZE WIĘKSZE */
    max-width: 100%;                  /* nie wyjdzie poza <li> */
    height: auto;
    border-bottom-style: dotted;
    border-top-style: none;
    border-left-style: none;
    border-right-style: none;
    margin-bottom: 10px;
  }
  @media (min-width: 900px) {
    ul.posts img.post-thumb {
      width: clamp(300px, 40vw, 640px); /* większy limit na desktopie */
    }
  }
</style>

<ul class="posts">
  {% for post in site.categories.work %}
    <li>
      <img
        class="post-thumb"
        src="{{ site.baseurl }}images/{{ post.thumbnail }}"
        alt="{{ post.title | escape }}"
        loading="lazy"
      />
      <br/> ::
      <a class="post-link" href="{{ site.baseurl }}{{ post.url }}" style="font-size:25px; margin-bottom:5px;">
        {{ post.title }}
      </a>
      <br/>
      <span style="font-size:15px; margin-bottom:5px;">@ {</span>
      {% assign tag = post.tags | sort %}
      {% for category in tag %}
        <span style="font-size:15px; margin-bottom:5px;">
          <a href="{{ site.baseurl }}category/#{{ category }}" class="reserved">{{ category }}</a>{% if forloop.last != true %},{% endif %}
        </span>
      {% endfor %}
      {% assign tag = nil %}
      <span style="font-size:15px; margin-bottom:5px;">}</span>
    </li>
  {% endfor %}
</ul>
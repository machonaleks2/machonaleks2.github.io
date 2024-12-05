---
layout: work
title: "My work"
permalink: /work/
---

<ul class="posts">
    {% for post in site.categories.work %}
        <li style="border: 1.5px; border-bottom-style: dotted; border-top-style: dotted; border-left-style: none; border-right-style: none; display: inline-block; padding: 20px; width: 80%;   margin-top: 10px;   margin-bottom: 10px;">
            ::
            <a class="post-link" href="{{ site.baseurl }}{{ post.url }}" style="font-size: 20px; margin-bottom: 5px;" >{{ post.title }}</a>
            <br/>@ {
            {% assign tag = post.tags | sort %}
            {% for category in tag %}<span><a href="{{ site.baseurl }}category/#{{ category }}" class="reserved">{{ category }}</a>{% if forloop.last != true %},{% endif %}</span>{% endfor %}
            {% assign tag = nil %}
            }
        </li>
    {% endfor %}
</ul>
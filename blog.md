---
layout: work
title: "My work"
permalink: /work/
---

<ul class="posts">
    {% for post in site.categories.work %}
        <li style="border: 1.5px; border-bottom-style: dotted; border-top-style: dotted; border-left-style: none; border-right-style: none; display: inline-block; padding: 20px; width: 80%;   margin-top: 10px;   margin-bottom: 10px;">
            <img src="{{ site.baseurl }}images/{{ post.thumbnail }}" width="200" style="border-bottom-style: dotted; border-top-style: none; border-left-style: none; border-right-style: none; margin-bottom: 5px;"> <br/>
            ::
            <a class="post-link" href="{{ site.baseurl }}{{ post.url }}" style="font-size: 25px; margin-bottom: 5px;" >{{ post.title }}</a>
            <br/><span style="font-size: 15px; margin-bottom: 5px;">@ {</span>
            {% assign tag = post.tags | sort %}
            {% for category in tag %}
            <span style="font-size: 15px; margin-bottom: 5px;">
            <a href="{{ site.baseurl }}category/#{{ category }}" class="reserved" >{{ category }}</a>{% if forloop.last != true %},{% endif %}
            </span>
            {% endfor %}
            {% assign tag = nil %}
            <span style="font-size: 15px; margin-bottom: 5px;">
            }
            </span>
        </li>
    {% endfor %}
</ul>
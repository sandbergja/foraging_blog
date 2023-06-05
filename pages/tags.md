---
layout: page
title: Tags
---

{% assign tags_sorted = site.tags | sort %}
{% assign posts_sorted = site.posts | sort: 'title' %}
{% for tagitem in tags_sorted %}
<div id="{{ tagitem[0] }}">
  <h2> {{ tagitem[0] }} </h2>

  <ul>
    {% for post in posts_sorted %}
      {% if post.tags contains tagitem[0] %}
          <li>
            <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
          </li>
      {% endif %}
    {% endfor %}
  </ul>
</div>
{% endfor %}
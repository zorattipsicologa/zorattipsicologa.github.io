---
layout: default
permalink: /de/blog/
title: blog
lang: de
translations:
  it: /blog/
  en: /en/blog/
---

<div class="post">
  <ul class="post-list">
    {% assign postlist = site.de_posts | sort: 'date' | reverse %}
    {% for post in postlist %}
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
      <li>
        <h3>
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
        <p>{{ post.description }}</p>
        <p class="post-meta">{{ read_time }} min read &nbsp; &middot; &nbsp; {{ post.date | date: '%B %d, %Y' }}</p>
      </li>
    {% endfor %}
  </ul>
</div>

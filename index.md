---
layout: page
title: 首页
permalink: /index.html
---

需想象西西弗斯是幸福的。

## 最近文章

<div class="posts compact">
{% for post in site.posts limit:5 %}
  <article class="post-list-item">
    <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
    <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}{% if post.tags %} · {{ post.tags | join: " / " }}{% endif %}</p>
    <div class="entry">{{ post.excerpt }}</div>
  </article>
{% endfor %}
</div>

[查看全部文章]({{ site.baseurl }}/blog/)

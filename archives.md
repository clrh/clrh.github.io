---
layout: page
title: Archives
---

<section class="archive">
{% for post in site.posts %}
{% unless post.next %}

{% unless forloop.first %}</div></div>{% endunless %}

  <div">
    <h2 class="post-year">{{ post.date | date: '%Y' }}</h2>
    <div class="posts-by-year">

{% else %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}

{% unless forloop.first %}</div></div>{% endunless %}

  <div>
    <h2 class="post-year">{{ post.date | date: '%Y' }}</h2>
    <div class="posts-by-year">
{% endif %}
{% endunless %}

  <article>
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    <div class="post-date">
      <time datetime="{{ post.date | date: '%Y-%m-%d' }}">{{ post.date | date: "%-d %B" }}</time>
    </div>
  </article>

{% if forloop.last %}</div></div>{% endif %}

{% endfor %}
</section>

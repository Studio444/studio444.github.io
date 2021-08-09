---
layout: page
title: Update Note
subtitle: Tiny Jump
---

<div>
{% assign postsCategory = site.posts | group_by_exp:"post", "post.categories"  %}
{% for category in postsCategory %}
        {% if category.path contains 'tinyjump' %}
<h4 class="post-teaser__month">
<strong>
{% if category.name %} 
- - - - -  {{ category.name }} - - - - - 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</h4>
<ul class="list-posts">
{% for post in category.items %}
    {% if post.path contains 'tinyjump' %}
<li class="post-teaser">
<a href="{{ post.url | prepend: site.baseurl }}">
<span class="post-teaser__title">{{ post.title }}</span>
<span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span>
</a>
</li>
    {% endif %}
{% endfor %}
</ul>
        {% endif %}
{% endfor %}
</div>

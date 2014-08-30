---
layout: page
title: Bear defeat without losing heart.
tagline:  Arya Rush
---
{% include JB/setup %}



## My resume

Read [wangtengteng_FE](http://wangtengteng.qiniudn.com/Wangtengteng_FEResume.pdf)

    
##  Posts


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>





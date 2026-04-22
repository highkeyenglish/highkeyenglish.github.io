---
layout: page
title: A Christmas Carol
description: 
img: assets/img/acc-cover.png
permalink: /a-christmas-carol/
nav: true
importance: 1
category: tutors
related_publications: false
---

## Teaching materials
See below all teaching materials I have for <i>Macbeth</i>.

{% for post in site.posts %}
  {% if post.categories contains 'a-christmas-carol' %}

    
### [{{post.title}}]({{post.url}})<br/><small>{{ post.date | date_to_long_string }}</small>
    
  {% endif %}
{% endfor %}

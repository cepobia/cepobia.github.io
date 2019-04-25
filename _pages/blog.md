---
title: Blog
layout: post
permalink: /blog/
author_profile: 
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/wbook.jpg
excerpt: "Este espacio es acerca del maravilloso mundo del business Intelligence y la ciencia de datos. En este compartiremos tips, conocimientos, tutoriales etc.. que seran utiles en tu desarrollo profesional"
---

<div class="grid__wrapper">
  {% assign posts = site.posts %}
  {% for post in posts %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>

---
title: Blog
layout: splash
#classes: wide
#type: grid
permalink: /blog/
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/wbook.jpg
excerpt: "Este espacio es acerca del maravilloso mundo del business Intelligence y la ciencia de datos. En este compartiremos tips, conocimientos, tutoriales etc.. que seran utiles en tu desarrollo profesional"
---

- ¿Tiene dificultades para proporcionar informes y análisis más precisos?
- ¿No puede identificar las últimas tendencias, las condiciones del mercado y responder rápidamente a los cambios?
- ¿Tiene problemas para optimizar el proceso interno de negocios y tomar decisiones?
- ¿Qué hay de obtener importantes informes de negocios?
- ¿Es un desafío convertir los datos en bruto en información procesable?

***Si es así, entonces este blog es definitivamente para ti!***

{{ content }}

{% assign categories_max = 0 %}
{% for category in site.categories %}
  {% if category[1].size > categories_max %}
    {% assign categories_max = category[1].size %}
  {% endif %}
{% endfor %}

<ul class="taxonomy__index">
  {% for i in (1..categories_max) reversed %}
    {% for category in site.categories %}
      {% if category[1].size == i %}
        <li>
          <a href="#{{ category[0] | slugify }}">
            <strong>{{ category[0] }}</strong> <span class="taxonomy__count">{{ i }}</span>
          </a>
        </li>
      {% endif %}
    {% endfor %}
  {% endfor %}
</ul>

{% for i in (1..categories_max) reversed %}
  {% for category in site.categories %}
    {% if category[1].size == i %}
      <section id="{{ category[0] | slugify | downcase }}" class="taxonomy__section">
        <h2 class="archive__subtitle">{{ category[0] }}</h2>
        <div class="entries-{{ page.entries_layout | default: 'list' }}">
          {% for post in category.last %}
            {% include archive-single.html type=page.entries_layout %}
          {% endfor %}
        </div>
        <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Regresar' }} &uarr;</a>
      </section>
    {% endif %}
  {% endfor %}
{% endfor %}


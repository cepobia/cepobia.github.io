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

¿Tiene dificultades para proporcionar informes y análisis más precisos?
¿No puede identificar las últimas tendencias, las condiciones del mercado y responder rápidamente a los cambios?
¿Tiene problemas para optimizar el proceso interno de negocios y tomar decisiones?
¿Qué hay de obtener importantes informes de negocios?
¿Es un desafío convertir los datos en bruto en información procesable?

### Si es así, entonces este blog es definitivamente para ti!

Bueno, en tal escenario, el poderoso sistema de Business Intelligence puede venir a rescatar.

Gartner ha reconocido a Microsoft como líder en plataformas de análisis y BI durante 11 años consecutivos.

Antes de profundizar, comencemos con lo básico.

<div class="grid__wrapper">
  {% assign posts = site.posts %}
  {% for post in posts %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>


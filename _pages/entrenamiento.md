---
title: "Entrenamiento"
layout: splash
permalink: /entrenamiento/
collections: cursos
author_profile: false
header:
  overlay_color: "#777779"
  overlay_filter: "0.5"
  overlay_image: /assets/images/wide/training.jpg
excerpt: "Empoderate con informacion"
---

Diseñamos experiencias de aprendizaje tanto en modalidad eLearning como presencial, con el objetivo de cubrir las principales necesidades de capacitación de nuestros clientes, facilitando así su viaje a través del mundo analítico

Nuestros servicios de entrenamiento al igual que nuestras consultorias estan enfocados para que su equipo se empodere de los datos y disminuyan la dependencia del equipo de TI y tenga la capacidad de generar nuevos informes y reportes que soporten la toma de decisiones.

En el entrenamiento del Campo de BI nos especializamos en el stack de Microsoft porque son las herramientas más familares para los usuarios finales, En el campo de la analitica tenemos hibrido entre herramientas Microsfot y OpenSource porque el crecimiento de este campo se ha desarrollado en este tipo de herramientas.

<div class="grid__wrapper">
  {% assign posts = site.cursos %}
  {% for post in posts %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>

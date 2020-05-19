---
layout: single
classes: wide
author_profile: true
author: Juan David
title: "APLICACIÓN AUTOMATIZADA DE MACHINE LEARNING (ML) EN POWER BI"
excerpt: "En los últimos años, la inteligencia artificial y el aprendizaje automático han visto un aumento sin procedentes en popularidad en todas las industrias y áreas de la investigación científica. Las empresas están buscando formas de integrar estas nuevas tecnologías en sus operaciones."
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/AI.jpg
  teaser: assets/images/cuadrado/ML_ indicador.jpg
categories:
  - Machine Learning
---


Power BI es una de las herramientas más populares de Microsoft que han adaptado científicos de datos, analistas y desarrolladores de Bussines Intelligence para la ejecución de sus roles en función del ML, como se muestra en el siguiente el cuadro: 

![Cuadro Comparativo](/assets/images/post/ML_en_PowerBI/cuadro_comparativo.png)

La mayoría de estas propiedades se pueden ejecutar en la modalidad de Power BI Desktop y el resto adquiriendo licencia en premium con Power BI Service.
En este artículo, se pretende mostrar una novedosa característica del IA en Power BI Desktop denominado AutoML. Con unos simples clics, el AutoML permite a los usuarios crear visualizaciones basados en modelos de Machine Learning para la generación informes ad-hoc o en análisis de causa raíz, que se mejora mediante la funcionabilidad integrada de IA integration. 	

## Árbol de Descomposición

Una de las novedosas visualizaciones en términos de ML que ha introducido Power BI es el árbol de descomposición. Una Visualización altamente interactiva que le permite descomponer (desglosar) una métrica o variable respuesta varios atributos a través de diferentes dimensiones.
Para demostrar cómo funciona el árbol de descomposición, se modela a partir del conjunto de datos sobre seguros de vida, donde se tiene información sobre el valor del seguro en dólares de cada persona con respecto a su sexo, la edad, si fuma o no tabaco y la cantidad de hijos que tiene.
El problema de análisis consiste en descomponer la métrica valor del seguro en dólares en las variables explicativas denominadas sexo, la edad, si fuma o no tabaco y la cantidad de hijos.
Una vez el set de datos esté conectado a Power BI, se agrega una nueva visualización “Descomposition Tree” donde se requiere dos tipos de entrada:
Analize: La métrica que le gustaría analizar
Explain by: Una o más dimensiones en las que te gustaría profundizar

![PB_Analize](/assets/images/post/ML_en_PowerBI/PB_Analize.png)

Se obtiene el siguiente resultado:

![Arbol](/assets/images/post/ML_en_PowerBI/arbol_1.png)

El árbol de descomposición te permite desglosar la variable respuesta en el orden de variables explicativas que desees solamente haciendo clic en cualquiera de los nodos, además, tendrás un signo (+) para saber el nivel alto de cada variable y un signo (-) si quieres observar el nivel más bajo. En contexto del ejemplo tenemos que, si una persona es de sexo masculino, fuma tabaco, no tiene hijos y su edad esta en los 19 años tendrá el valor del seguro más alto dentro de todos los posibles resultados del análisis, el cual se estima de $245.500 dólares. Los $17.755.825 dólares hacen referencia al valor total de los seguros de todas las personas del conjunto de datos. 
Así sucesivamente se pueden analizar las posibles descomposiciones de interés según la idea de negocio o la problemática de análisis a trabajar.

Dado el caso que se tenga otra variable de interés en el estudio se pueden crear otro tipo de visualización para poder interactuar con el árbol de descomposición, siguiendo el ejemplo, se tiene la región de procedencia de cada persona como se expone los siguientes resultados:

![Arbol_2](/assets/images/post/ML_en_PowerBI/arbol_2.jpg)

![Arbol_3](/assets/images/post/ML_en_PowerBI/arbol_3.png)

Dependiendo de la región de procedencia cambian las distintas descomposiciones del árbol, lo cual lo hace una herramienta del AutoML interesante de aplicar dentro de Power BI.

## key Influencers

Otras de las visualizaciones destacas son los Key influencers . Power BI utiliza el AutoML para ejecutar una regresión logística como modelo base de ML dentro de esta visualización, teniendo como principal objetivo el poder clasificar los factores que están más asociados con la métrica en términos de probabilidad.
Para la ejecución del ejemplo, se tomó el archivo de datos sobre comentarios de cliente basados en [Moro et al., 2014] S.Moro,P. Cortez y P.Rita. “Un enfoque basado en datos para predecir el éxito de telemarketing bancario”. Decision Support Systems, Elsevier, 62:22-31, junio de 2014.
Como problemática de negocio, el gerente de producto quiere que se descubra la cantidad factores que llevan a los clientes en determinar una calificación negativa con respecto a su servicio en la nube.
Los campos que influyen en la calificación (rating) de los clientes son:

•	País-Región
•	Rol del cliente en la organización
•	Tipo de suscripción 
•	Tamaño de la empresa 
•	Tema

Cuando no se tenga una determinación clara de las variables explicativas más influyentes en una métrica, se recomienda emplear un preanálisis estadístico correlacional en sus set de datos para poderlas identificar. 
Al igual que en el árbol de descomposición, los dos tipos de entradas son los siguientes:

![PB_Analize](/assets/images/post/ML_en_PowerBI/PB_Analize_2.png)

El cual genera las siguientes salidas:

![PB_Analize](/assets/images/post/ML_en_PowerBI/top_segments1.jpg)

Como primer paso se señala que el tipo de rating sea bajó en la visualización, después se representan los factores más influyentes, el factor número 1 o más influyente, es el rol del cliente en la organización, donde si es de tipo consumidor tiene 2.57 más probabilidades de dar una puntación baja en comparación con los demás roles como administrador y editor.
El segundo factor más influyente es el tema de la revisión del cliente. Los clientes que comentaron sobre la usabilidad del producto tenían 2.55 veces más probabilidades de dar una calificación baja en comparación con los clientes que comentaron sobre otros temas, como la fiabilidad, el diseño o la velocidad. De manera semejante  se interpretaría los demás resultados según el contexto de cada variable.

Como un resultado de apoyo en la visualización Key influencers, hay un gráfico de columnas que muestra la distribución del factor seleccionado. Al seleccionar la casilla de verificación en la parte inferior, muestra solo lo más influyentes

![barras](/assets/images/post/ML_en_PowerBI/Barras.png)

En el caso del rol del cliente en la organización, se tiene que el 14.93% de la categoría consumidores dan un puntaje bajo. Adicionalmente, en promedio todos los demás roles excluyendo el de consumidores estiman un puntaje bajo de calificación del 5.78%.

La pestaña top segments muestra los diferentes clústeres identificados por Power BI dentro de la población, para el valor métrico seleccionado que en este caso son las calificaciones bajas de los clientes.
El segmento 1, por ejemplo, tiene 30.8% de calificaciones de bajas calificaciones de los clientes. El tamaño de la burbuja representa cuantos clientes hay dentro de cada clúster

![segments_1](/assets/images/post/ML_en_PowerBI/top_segments1.jpg)

Al seleccionar una burbuja, se profundiza en detalle cada segmento. Si seleccionamos la burbuja número uno, encontrará que en este clúster pertenecen clientes que no son editores, es decir, son consumidores o administradores con más de 29 años accediendo a los servicios de la empresa y que tienen más de 4 tickets de soporte.
En este grupo, el 30.8% de los clientes dieron una calificación baja. El cliente promedio obtuvo calificación baja del 11.7%, además, que el segmento uno contiene aproximadamente 3.5% del set de datos.

![segments_2](/assets/images/post/ML_en_PowerBI/top_segments2.png)

La intención con lo que se escribió este articulo fue mencionar algunas técnicas de las cuales Power BI está adaptando en todo lo relacionado con IA. De aquí adelante se vendrán muchas cosas muy interesantes para abordar y sacarle más potencial a esta buena herramienta que nos brinda Microsoft.
Nos encontramos al borde de la cuarta revolución industrial, donde las empresas de tecnologías de la información esta llamadas a dominar la industria por su papel fundamental de darle valor a los datos para la toma de decisiones. A medida que avanza esta cuarta revolución industrial, los científicos de datos y profesionales en IA tendremos la fortuna de seguir aprendiendo de nuevas temáticas que nos sorprenden cada día.

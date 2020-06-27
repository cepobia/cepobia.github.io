---
layout: single
classes: wide
author_profile: true
author: Juan David
title: "Aplicación de una Artificial Neural Network (ANN) en Power BI adaptando el lenguaje de programación R"
excerpt: "Muchos de los que somos usuarios de herramientas fuertes en la ciencia de datos como R y/o Python...."
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/Banner_ANN.jpg
  teaser: assets/images/cuadrado/Redes_N.jpg
categories:
  - Artificial Neural Network (ANN)
---


Muchos de los que somos usuarios de herramientas fuertes en la ciencia de datos como R y/o Python estamos en la constante búsqueda de estrategias para adaptar estos programas de desarrollo de analítica a otros entornos.

Considerando el anterior argumento, desde el equipo de CepoBIA surgió la idea de redactar un artículo en el cual se exponga de manera secuencial como incluir las salidas de una Artificial Neural Network (ANN) con la ayuda de la script de R instalada en Microsoft Power BI.

Pero a todas estas, ¿Qué es una ANN?. Una red neuronal artificial, como se conoce en español, modela la relación entre un conjunto de señales de entrada y salida utilizando un modelo derivado de comprender cómo el cerebro responde a los estímulos sensoriales. Así como un cerebro humano usa una red de células interconectadas llamadas neuronas para crear un proceso masivo paralelo, una ANN utiliza una red neuronal o nodos artificiales para resolver problemas de aprendizaje automático.

En la actualidad, el uso de masivo de computadoras potencialmente eficientes ha impulsado a la aplicación de las ANN en problemas de gran calibre como:

*	Programas de reconocimiento de imágenes y voz utilizados en algún servicio tecnológico.  
*	La mecanización de dispositivos inteligentes como autos sin conductor y drones con piloto automático
*	Modelos sofisticados de patrones climáticos, clasificaciones de enfermedades y muchos otros fenómenos científicos, sociales o económicos.

 
Bueno, ahora que se hizo una breve definición de lo que es ANN y en donde se puede emplear, vamos directo al ejemplo.

Estimar la resistencia del concreto es un desafío de particular interés. Aunque es utilizado en casi todos los proyectos de construcción, el rendimiento de su estructura varía mucho debido a una amplia variedad de características que interactúan de forma compleja, por lo tanto, es difícil predecir con precisión la resistencia de este material. Como desafío se implementa una ANN, para predecir la resistencia del concreto dada una lista de insumos que ayudan a la composición de prácticas en la construcción de edificaciones.

Utilizaremos el set de datos  sobre la resistencia a la compresión de concreto donado en la plataforma de machine learning Kaggle    [enlace](https://www.kaggle.com/pavanraj159/concrete-compressive-strength-data-set). 

Según el sitio web, el conjunto de datos contiene 1.030 mediciones de la resistencia de concreto con ocho sus insumos que describen los componentes utilizados en el material. Como insumos se incluyen la cantidad en kilogramos por metro cúbico de cemento (cement), mezcla de escoria (slag), mezcla de cenizas (Ash), agua (water), mezcla de superplastificante (superplasticizer), mezcla de agregado grueso (CoarseAgg) y  mezcla agregado fino (Fine Agg) utilizado en el material además del tiempo de envejecimiento (Age) medido en días, estos ingredientes se creen que están relacionados con la resistencia (strength).

Al subir el dataset a Microsoft Power BI tenemos la siguiente estructura:

![Cuadro principal](/assets/images/post/ANN/Principal.PNG)

## Paso 1- Crear la visualización de R

Al darle clic en la visualización correspondiente al script de R, seleccionamos todas las variables en estudio como se muestra a continuación:

 
![Imagen Opciones](/assets/images/post/ANN/imagen1.PNG)	

## Paso 2- Formación de un dataframe

De manera automática en él script de R de Power BI formará un dataframe con las variables seleccionadas para posteriormente ejecutar los códigos de análisis.


![Imagen Scrip](/assets/images/post/ANN/imagen2.PNG)	

## Paso 3- Estandarización, reparto de dataset de entrenamiento y prueba

Antes de ejecutar cualquier algoritmo de Machine Learning, es aconsejable reescalar las variables con el objetivo de que todas estén medidas en un mismo rango de unidades, en este ejercicio se decidió estandarizar a partir de los valores máximos y mínimos dado que en un previo análisis descriptivo se evidenció que la distribución de casi todas  las variables era sesgada. Posteriormente, se escoge el 75% de los datos para el dataset de entrenamiento y el 25% restante como dateset prueba.
Los datos ya estaban ordenados en orden aleatorio por tal motivo no hubo necesidad de realizar un muestreo aleatorio con la función sample en R.

  
![Imagen Scrip](/assets/images/post/ANN/imagen3.PNG)	

## Paso 4- Entrenar la ANN

Al tener con anterioridad instalada y cargada la librería neuralnet  en R, procedemos a  llamar el paquete con el comando library y  entrenar la ANN usando la siguiente sintaxis: 


![Imagen Scrip](/assets/images/post/ANN/imagen4.PNG)	

Al final al “plotear” el modelo, se obtiene la visualización en Power BI de la red neural que se están entrenando, el algoritmo de entrenamiento utilizado es el de backpropagation, la función de activación ejercida en cada neurona es la sigmoide y la cantidad de nodos ocultos recomendados en la modelación son de 5.


![Imagen Scrip](/assets/images/post/ANN/imagen5.PNG)	

En la parte inferior de la visualización, R informa el número de pasos de entrenamiento y un error aprendizaje donde por fortuna nos da bajó, es decir, la función de coste encontró después de una gran cantidad de pasos, los pesos que minimizan el error del modelo de entrenamiento dadas las condiciones de análisis.


## Evaluación de la ANN

Ahora evaluemos el rendimiento de la ANN a partir del conjunto de datos de prueba, en este caso se utiliza el Query Editor de Power BI.

## Paso 1- Obtener la resistencia predicha 
En la pestaña de transformaciones del Query Editor, le damos clic al botón descrito como Run R script, luego copiamos y pegamos todo el código mostrado anteriormente con la única excepción de quitar el comando plot que nos ayuda a visualizar la red neuronal artificial, añadimos compute el cual almacena las predicciones respecto a los datos de prueba.

Seguidamente, determinamos las salidas de interés en un dataframe denominado output donde se introduce el conjunto de datos de prueba y las predicciones desestandarizadas.


![Imagen Scrip](/assets/images/post/ANN/imagen5.PNG)	

Al darle clic en OK y posteriormente en el output creado en el Query Editor, obtenemos las predicciones de la resistencia del concreto tabuladas y listas para crear las visualizaciones que desees con la meta de evaluar el rendimiento del modelo de aprendizaje automático.

![Imagen Scrip](/assets/images/post/ANN/imagen6.PNG)

## Paso 2- Correlación entre la resistencia predicha y real

Debido a que este es un problema de predicción en lugar de uno de clasificación, no se puede usar la matriz de confusión para examinar la precisión del modelo. En cambio, se propone medir el grado de asociación lineal a partir de la correlación entre resistencia de concreto predicha y el valor real.

Al cerrar y aplicar las transformaciones del Query Editor, en el Power BI Desktop procedemos a abrir una nueva visualización del script R y seleccionamos las variables de interés, como se presenta a continuación:

![Imagen Scrip](/assets/images/post/ANN/imagen7.PNG)

Con la ayuda de la librería “GGally” previamente instalada en R, obtenemos el cálculo de la correlación entre las dos variables:

![Imagen Scrip](/assets/images/post/ANN/imagen8.PNG)

La correlación indica una fuerte relación lineal entre dos variables. Esto implica que nuestra ANN está haciendo un trabajo bastante bueno para predecir la resistencia del concreto.

Si es de gusto puedes acompañar el cálculo de la correlación ejecutando una gráfica de dispersión entre valores predichos y reales, como se expone a continuación.

![Imagen Scrip](/assets/images/post/ANN/imagen9.PNG)

Finalmente, vimos paso a paso como se pueden mostrar los resultados de uno de los modelos de aprendizaje automático a partir de Microsoft Power BI, ahora anímate y empieza a hacer tus dashboard no solo empleando una ANN, inténtalo con una máquina de soporte vectorial, un ACP, arboles de decisión y demás modelos ML pertenecientes mundo de la inteligencia artificial.

En cepoBIA seguiremos avanzado en la aplicación de nuestro conocimiento de analytics en las novedosas tecnologías que nos ofrece Microsoft.




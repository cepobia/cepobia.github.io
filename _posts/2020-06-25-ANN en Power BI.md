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

Considerando el anterior argumento, desde el equipo de CepoBIA surgió la idea de exponer de manera resumida como incluir las salidas de una Artificial Neural Network (ANN) con la ayuda de la script de R instalada en Microsoft Power BI.
Pero a todas estas, ¿Qué es una ANN?. Una red neuronal artificial, como se conoce en lenguaje español, modela la relación entre un conjunto de señales de entrada y salida utilizando un modelo derivado de comprender cómo el cerebro responde a los estímulos sensoriales. Al igual que el cerebro humano usa una red de células interconectadas llamadas neuronas para crear un proceso masivo paralelo, una ANN utiliza una red neuronal o nodos artificiales para resolver problemas de aprendizaje automático.
En la actualidad, el uso masivo de computadoras potencialmente eficientes ha impulsado a la aplicación de las ANN en problemas de gran calibre como:

*	Programas de reconocimiento de imágenes y voz utilizados en algún servicio tecnológico. 
*	La mecanización de dispositivos inteligentes como autos sin conductor y drones con piloto automático
*	Modelos sofisticados de patrones climáticos, clasificaciones de enfermedades y muchos otros fenómenos científicos, sociales o económicos.

 
Ahora que hicimos una breve definición de lo que es ANN y en donde se puede emplear, vamos directo al ejemplo. 

En el campo de la ingeniería, es crucial contar con estimaciones precisas del rendimiento de los materiales de construcción. Estas estimaciones son necesarias para desarrollar directrices que rigen los materiales utilizados en la construcción de edificios, puentes y carreteras.
Estimar la resistencia del concreto es un desafío de particular interés. Aunque es utilizado en casi todos los proyectos de construcción, el rendimiento de su estructura varía mucho debido a una amplia variedad de características que interactúan de forma compleja, por lo tanto, es difícil predecir con precisión la resistencia de este material. Como desafío se implementa una ANN, para predecir la resistencia del concreto dada una lista de insumos que ayudan a la composición de prácticas en la construcción de edificaciones.
Utilizaremos el set de datos  sobre la resistencia a la compresión de concreto donado en la plataforma de machine learning Kaggle  (https://www.kaggle.com/pavanraj159/concrete-compressive-strength-data-set). 

Según el sitio web, el conjunto de datos contiene 1.030 mediciones de la resistencia de concreto con ocho de sus insumos que describen los componentes utilizados en el material. Como insumos se incluyen la cantidad en kilogramos por metro cúbico de cemento (cement), mezcla de escoria (slag), mezcla de cenizas (Ash), agua (water), mezcla de superplastificante (superplasticizer), mezcla de agregado grueso (CoarseAgg) y  mezcla agregado fino (Fine Agg) utilizado en el material además del tiempo de envejecimiento (Age) medido en días, estos ingredientes se creen que están relacionados con la resistencia (strength).

Al subir el dataset a Microsoft Power BI tenemos la siguiente estructura:

![Cuadro principal](/assets/images/post/ANN/Principal.PNG)

Al darle clic en la visualización correspondiente al script de R, seleccionamos todas las variables en estudio como se muestra a continuación:

 
![Imagen Opciones](/assets/images/post/ANN/imagen1.PNG)	

De manera automática en el script de R se formará un dataframe con las variables seleccionadas para posteriormente ejecutar los códigos de análisis.

![Imagen Scrip](/assets/images/post/ANN/imagen2.PNG)	

Antes de ejecutar cualquier algoritmo de Machine Learning, es aconsejable reescalar las variables en estudio, con el objetivo de que todas estén medidas en un mismo rango de unidades, en este ejercicio se decidió estandarizar a partir de los valores máximos y mínimos dado que en un previo análisis descriptivo se evidenció que la distribución de la mayoría de variables era sesgada. Posteriormente, se escoge el 75% de los datos para el dataset de entrenamiento y el 25% restante como dateset de prueba.
Los datos ya estaban ordenados en orden aleatorio, por tal motivo no hubo necesidad de realizar un muestreo aleatorio con la implementación de la función sample en R.
  
![Imagen Scrip](/assets/images/post/ANN/imagen3.PNG)	

Instalando y cargando la librería neuralnet en la base de R, procedemos a entrenar la ANN usando la siguiente sintaxis: 

![Imagen Scrip](/assets/images/post/ANN/imagen4.PNG)	

Al final al “plotear” el modelo, se obtiene la visualización de la red neural que se están entrenando, el algoritmo de entrenamiento utilizado es el de backpropagation, la función de activación ejercida en cada neurona es la sigmoide y la cantidad de nodos ocultos recomendados en la modelación son de 5.

El algoritmo de iteración hacia atrás backpropagation utiliza la derivada de la función de activación insertada en cada neurona artificial para identificar la dirección del gradiente en los pesos entrantes, de ahí la importancia de tener una función de activación diferenciable como la sigmoide.

![Imagen Scrip](/assets/images/post/ANN/imagen5.PNG)	

En la parte inferior de la imagen, R informa el número de iteraciones de entrenamiento y un error aprendizaje donde por fortuna es bajo, es decir, la función de coste encontró después de una gran cantidad de pasos los pesos que minimizan el error del modelo dadas las condiciones de análisis.

Ahora evaluemos el rendimiento de la NNA a partir del conjunto de datos de prueba, en este caso se utiliza el Query Editor de Power BI para hacer las transformaciones con la ayuda del script R.

Copiamos y pegamos el código mostrado anteriormente con la única excepción de quitar el comando plot que nos ayuda a visualizar la red neuronal, añadimos el comando compute que almacena las predicciones respecto a los datos de prueba.

Seguidamente, determinamos las salidas de interés en un output que en este caso son el conjunto de datos de prueba y las predicciones desestandarizadas.

![Imagen Scrip](/assets/images/post/ANN/imagen5.PNG)	

Al hacer las transformaciones en el Query Editor, obtenemos las predicciones de la resistencia del concreto tabuladas y listas para crear las visualizaciones que desees con la meta de evaluar el rendimiento del modelo de aprendizaje automático.

![Imagen Scrip](/assets/images/post/ANN/imagen6.PNG)


Debido a que este es un problema de predicción en lugar de uno de clasificación, no se puede usar la matriz de confusión para examinar la precisión del modelo. En cambio, se propone medir el grado de asociación lineal a partir de la correlación entre resistencia de concreto predicha y el valor real.

Al cerrar y aplicar las transformaciones del Query Editor, en el Power BI Desktop procedemos a abrir una nueva visualización del script R y seleccionamos las variables de interés, como se presenta a continuación:

![Imagen Scrip](/assets/images/post/ANN/imagen7.PNG)

Con la ayuda de la librería “GGally” previamente instalada en R, obtenemos el cálculo de la correlación entre las dos variables:

![Imagen Scrip](/assets/images/post/ANN/imagen8.PNG)

La correlación indica una fuerte relación lineal entre dos variables. Esto implica que nuestra ANN está haciendo un trabajo bastante bueno para predecir la resistencia del concreto.

Al final si es de gusto puedes acompañar el cálculo de la correlación ejecutando una gráfica de dispersión entre valores predichos y reales, como se expone a continuación.

![Imagen Scrip](/assets/images/post/ANN/imagen9.PNG)

Vimos paso a paso como se pueden mostrar los resultados de uno de los modelos de aprendizaje automático a partir de Microsoft Power BI, ahora anímate y empieza a hacer tus dashboard no solo empleando una ANN, inténtalo con una máquina de soporte vectorial, un ACP, arboles de decisión y demás modelos ML pertenecientes al mundo de la inteligencia artificial.
En cepoBIA seguiremos avanzado en la aplicación de nuestro conocimiento de analytics en las novedosas tecnologías que nos ofrece Microsoft.

## Árbol de Descomposición

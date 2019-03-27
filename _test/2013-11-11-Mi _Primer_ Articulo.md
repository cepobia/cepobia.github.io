---
title: "Mi Primer Articulo Académico"
date: 2013-11-16
tags: [Time Series, Forescast, Español]
header:
  teaser: assets/images/teaser/time_series.png
toc: true
toc_label: "Tabla de Contenido"
toc_icon: "cog"
categories:
  - Time Series
---
# Sistema de Pronósticos para los Minoristas de Productos de Moda

## Universidad del Valle, Sede Palmira, Colombia

### RESUMEN

En la actualidad el tema de los pronósticos ha sido un punto crítico a manejar en el sector de los minoristas de productos de moda.  Para el desarrollo de este artículo  primero se seleccionaron  los productos objetos en base a la cantidad de venta,  estos productos se  analizaron en una serie de tiempos con las ventas ocurridas durante cinco (5) años en el punto de venta  de productos de moda teniendo en cuenta el comportamiento de las demandas y por último se  pronosticaron  manejando tres (3) combinaciones de métodos pronósticos enmarcadas en el metodología de descomposición. 
El criterio de selección de la combinación de Pronósticos  fue el de menor ECM se determinó cuál era el mejor modelo para los distintos productos. No se pudo obtener una única combinación de  métodos de pronóstico. 

Palabras claves: Demanda, Pronósticos, Serie de tiempos, Estacionalidad

### ABSTRACT

At present the issue of forecasting has been a critical issue to handle in the field of retail fashion products. For the development of this article first objects were selected products based on the amount of sale, these products were analyzed in a time series with sales that occurred for five (5) years at the point of sale of fashion products taking into account the behavior of the demands and finally driving predicted three (3) combinations of forecasting methods framed in the decomposition methodology.
The selection criterion was the combination of the lowest Forecasts ECM was determined which was the best model for different products. Could not get a single combination forecasting methods.

Keywords: Demand Forecasting, Time series, Seasonality

### INTRODUCCIÓN 
Pronosticar consiste en la estimación y el análisis de la demanda futura para un producto en particular, un componente o un servicio, a través de diferentes técnicas de previsión. El pronóstico de la demanda futura es central en cualquier actividad de planificación y de operaciones, en particular en actividades relacionadas a la logística y a la cadena de suministro.
Esto ha sido en gran parte reconocido por diversos autores (Chu & Zhang, 2003). El pronóstico es una herramienta básica en la toma de decisiones de la administración y, en particular, es un componente esencial para que cualquier sistema de inventarios tenga éxito, (Hillier & Lieberman 1997). En la actualidad, la disposición de pronósticos constituye una parte fundamental de la logística, por las implicaciones que una variación en ésta supone en los principales procesos de la cadena de suministro (gestión de stocks, aprovisionamientos, transporte, fabricación, nivel de servicio, etc.), y por los beneficios que proporciona su correcta estimación y control. 
El objetivo de este trabajo es hallar un buen método de pronóstico para las ventas y para la programación de inventarios y producción para los minoristas de productos de moda.

1. ***Selección de Datos***

El inicio de la investigación de la problemática de los minoristas de productos de moda empieza con la recopilación de los datos durante 5 años consecutivos y teniendo las ventas correspondientes a cada una de las prendas de vestir de modo, el primer supuesto para poder desarrollar fue la agrupación de estas por categoría y dentro de estas se plantea que la prenda de vestir es igual a la otra en cuanto a su comportamiento de la demanda, sin diferencia alguna en cuanto a diseño y talla. 

2. ***Análisis de Serie tiempo***

Una serie tiempo es una secuencia de datos, observaciones o valores, medidos en determinados momentos del tiempo, ordenados cronológicamente y, normalmente, espaciados entre sí de manera uniforme. El análisis de series tiempo comprende métodos que ayudan a interpretar este tipo de datos, extrayendo información representativa, tanto referente a los orígenes o relaciones subyacentes como a la posibilidad de extrapolar y predecir su comportamiento futuro.
Se realizó un análisis del gráfico 2 que permitió la visualización del comportamiento de la demanda, para evaluar componentes En este análisis se toma como una estación el lapso de tiempo de un año y los períodos estacionales de longitud un mes, aquí se encontró que el patrón de la demanda es perpetuo y que se presentan estacionalidades en el último período estacional del año (mes de diciembre) y que se presentan también picos de demanda definidos como datos atípicos, que es un registro mayor o menor de lo esperado, los cuales se muestran por tener un residuo que es un valor inusual, muy grande o muy pequeño, en relación a la distribución normal de los datos recopilados de la demanda. Para el analisis de los datos atipicos se utilizan los diagramas de cajas basado en los cuartiles, una vez comprobado que los datos son atípicos no se eliminan automáticamente, debido a que, pueden representar un cambio real en el nivel de la cantidad de la demanda agregada. Lo conveniente es tomar en cuenta otras variables a la situación específica. El dato atípico se reemplaza por el promedio. 

3. ***Pronosticos***

Considerando que el comportamiento de la demanda encontrado corresponde a un patrón estacional se propone aplicar para pronosticar la demanda métodos de descomposición, los cuales se basan en la suposición de que se pueden separar los componentes como tendencia, ciclo, estacionalidad e irregularidad (Nahmias 2007)
El modelo de descomposición puede adoptar una variedad en el caso puntual del desarrollo de esta investigación se realizó con un modelo mixto de descomposición de formas como se muestra a continuación (Chopra y Meindl 2004):

```math
Modelo Mixto = (nivel + tendencia) x factor estacional

Se tiene en cuenta la siguiente nomenclatura para el desarrollo de los pronósticos.

Yt = Serie
Tt = componente tendencia
St = componente estacional
Ft = componente Aleatorio o Nivel (serie desestacionalizada)
It= componente irregular (error)
La descomposición de la serie de tiempo es la siguiente: 
Y_t=(T_t+F_t ) S_t+I_t
```

El método de pronóstico depende de si los patrones son estáticos o dinámicos, métodos estáticos para patrones que no cambian con el tiempo es el método del porcentaje medio y métodos dinámicos para patrones que cambian en el tiempo y sus estimados son determinados por los valores más cercanos.
En esta investigación se usan tres (3) combinaciones, es decir se utiliza un método estático para modelar un componente y otro dinámico para modelar otro componente.

* Combinación 1
Nivel (Ft)  estático-anual lineal
Estacionalidad (St) estático Método del porcentaje medio
Tendencia (Tt) despreciable
* Combinación 2
Nivel (Ft) estático-anual suavizado
Estacionalidad (St) estático Método del porcentaje medio
Tendencia (Tt) despreciable
* Combinación 3
Nivel (Ft) Dinámico suavizado
Estacionalidad (St) dinámica Método del porcentaje medio  suavizado
Tendencia (Tt) dinámica suavizada

### Resultados Pronósticos.
Como criterio decisión para determinar la mejor combinación se escoge el ECM (error cuadrático medio), porque el ECM es mejor indicador según Chan et al. (1999), debido a que a partir de suponer que los errores muy grandes en el pronóstico tienen un impacto más negativo que el efecto positivo generado por un error pequeño y considerando que por el cálculo que se realiza, asigna más ponderación a los errores grandes, es que se lo considera mejor criterio al momento de seleccionar el método más adecuado de pronóstico. Berenson  (2001). La tabla 1 recopila la información de los errores de cada combinación, se grafican la demanda con la combinación seleccionada por el ECM para cada categoría. Es importante tener en cuenta que para el desarrollo de la combinación 2 y 3 de pronósticos se optimizaron las constantes de suavización a través del solver  (∞, β, γ). 

### Conclusiones
Como se muestra en la Tabla 1  no se encontró un única combinación que sea la mejor para todas las categorías, se  puede observar que para 3 de las 6 categorías analizadas, la que menor ECM obtuvo fue la combinación 3, ya que calcula los componentes de manera dinámica, es decir se adapta mejor a los cambios en la cantidad demanda. El ECM determino que la combinación 2 fuera la escogida para 2 de las 6 categorías analizadas, esta combinación calcula de manera dinámica el nivel anual,  de manera estática el factor estacional y desprecia la tendencia. Por último el ECM mostro la combinación  1 para una sola de las categorías, esta combinación plantea el cálculo del nivel estático lineal anual, la estacionalidad estática y desprecia la tendencia.
Para el cálculo de inicial del factor estacional de las 3 combinación se utilizó el método de los porcentajes medios, aunque en la combinación 3 este se suaviza es decir se vuelve dinámico.
A partir de los resultados arrojados se puede ratificar lo plantean por varios autores en cuanto a que la teoría nos da un acercamiento de cuál puede ser el mejor método de pronóstico a partir de un análisis gráfico de los componentes de la demanda,  pero se debe de hacer una análisis más profundo planteado varias opciones y evaluándolas con los criterios de errores.

### REFERENCIAS
* Ballou, R. (2004). Logística de los negocios y la cadena de sumnistros: un tema vital. En Logística, Administración de la Cadena de Suministro.. Cap. 1. 5ta. ed. Editorial Prentice Hall. pp 32
* Bayraktar, E., Lenny K, S.C., Gunasekaran, A., Sari, K., Tatoglu, E. (2008). The role of forecasting on bullwhip effect for E-SCM application. International Journal of Production Economics, 113, 193-204
* Berenson, M., Levine, D., Krehbiel, T. (2001). Análisis de Series de Tiempo. En Estadística para la administración. Cap. 11. 2a. ed., Editorial Prentice Hall. pp 66
* Chan, C.K., Kingsman, B.G., Wong, H. (1999). The value of combinig forecast in inventory management - a case study in banking. European Journal of Operational Research,117, 199-
210.
* Chu, CH. & Zhang, G. (2003). A comparative study of linear and nonlinear models for aggregate retail sales forecasting. International Journal of Production Economics, 86, 217-231
* Corres, G., Esteban, A., García, J., Zárate, C. (2007). Análisis de stocks de seguridad en un ambiente de fabricación para inventario, 1° Congreso de Ingeniería Industrial COINI 2007,
UNLAM. Argentina.
* Fogarty, D., Blackstone, J., Hoffmann, T. (1999). Pronósticos. En Administración de la producción e inventarios”. Cap. 3. 2a. ed, Editorial CECSA. pp 43

### Figuras, Tablas y Ecuaciones

Gráfico 1. Gráfico de Demanda.

![](/assets/images/post/Grafico_1.png)

Fuente: Datos Puntos de venta
- Grupo de ecuaciones combinación  1
F_t=(Regresion lineal del año i correspondiente a periodo t)/(Numero de periodos (t) del ciclo estacional (año i))
S_t=(El promedio de Yt  en la estacion correspondiente (j))/(El promedio globla de Yt)
T_t=despreciable
- Grupo de ecuaciones combinación 2
Ft=(Suavizacion exponencial del año i correspondiente a periodo t)/(Numero de periodos (t) del ciclo estacional (año i))
S_t=(El promedio de Yt  en la estacion correspondiente (j))/(El promedio globla de Yt)
T_t=despreciable

- Grupo de ecuaciones combinación 3
'''
Ft=∝Y_t/S_(t-P) +(1-∝)(F_(t-1)+T_(t-1))
T_t=γ(F_t-F_(t-1))+(1-γ) T_(t-1)
S_t=β Y_t/F_t +(1-β) S_(t-P)

'''
TABLA 1.

|ERROR CUADRÁTICO MEDIO (ECM) |	COMBINACIÓN 1 |	COMBINACIÓN 2 | COMBINACIÓN 3 |
|-----------------------------|---------------|---------------|---------------|
|CATEGORÍA 4	              |         120,08|         109,59|         154,85|
|CATEGORÍA 6                  |	        507,38|	        625,07|	        451,47|
|CATEGORÍA 7                  |	      4.798,56|	      6.342,19|	      3.424,45|
|CATEGORÍA 10                 |         395,94|	        984,74|	        277,98|
|CATEGORÍA 14	              |       2.902,48|	      3.826,84|       3.524,25|
|CATEGORÍA 15	              |         293,96|	        288,29|	        330,54|
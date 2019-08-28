---
layout: single
classes: wide
author_profile: true
author: Esteban Londono
title: "El ETL de Power BI - Power Query y El leguaje M"
excerpt: "Power Query el Poderoso ETL oculto detrás de la Sección de Obtener Datos de Power BI "
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/wtablet.jpg
  teaser: assets/images/cuadrado/ETL.png
categories:
  - Introduccion
---

Si bien a veces se considera que Power BI es una herramienta de visualización de front-end, Microsoft creó un sistema de Business Intelligence que incluye todas las partes estándar de una solución tradicional. Aquí hay una vista de alto nivel de Power BI y una mirada a la parte "ETL" que está oculta detrás de la Sección de Datos Externos. (Por cierto, esa parte es el mismo subsistema que en Power Query en Excel; se ha trasplantado a SSAS 2017 y modelos tabulares más nuevos, así como a flujos de datos en Azure Data Lake).
 
Power BI se puede descomponer en las áreas funcionales estándar de Business Intelligence, tiene: 
- Una herramienta ETL (Extraer, Transformar, Cargar) en la sección Consulta de datos externos, 
- Modelado en el área de Relaciones, lenguaje de acceso a datos con DAX y su creación de medidas 
- Visualizaciones.

De hecho, hemos visto el uso exactamente de esta manera a medida que se extiende el uso de Power BI. Muchas personas están usando Power BI como una versión de alta potencia de lo que muchas pequeñas empresas hicieron con Excel.
 
Es bueno que Power BI pueda ser visto en el marco general de Business Intelligence porque puede usar estos informes como base para crear una solución más tradicional: un sistema de BI grande, más escalable y compatible que se pueda expandir y administrar de manera eficiente.
 
Pero también hay algo malo en que es fácil de usar para tareas funcionales individuales de diferentes personas porque fomenta la fragmentación. Cuando muchas personas en un negocio utilizan Power BI de forma independiente, los modelos no se acoplarán, y habrá problemas con los datos y el soporte a medida que el uso crezca. Estos son problemas normales cuando una herramienta como Power BI es adoptada por más y más personas en un negocio.
 
Al ver Power BI de esta manera, el profesional de BI se da cuenta de que todo lo que aprendió a lo largo de los años se puede aplicar a Power BI, para componer y descomponer  la estructura de Power BI  cuando necesita ser rediseñada para un entorno más grande ( ej. - SSAS realiza un back-end sobre un Datamart en SQL Server). ¡Las mejores prácticas desarrolladas en los últimos 20 años se pueden usar para expandir los sistemas Power BI para manejar más tareas empresariales

### Power Query M
Datos externos y el lenguaje mashup "M"
Con ese fondo en mente, concentrémonos en la parte ETL de Power BI: el Administrador de consultas y el lenguaje subyacente de Power Query M. ¿Cómo se debe utilizar? ¿Qué puede hacer para limpiar los datos? ¿Cuáles son los signos que apuntan a una solución más diseñada?
 
Al igual que muchas herramientas ETL populares, el lenguaje Power Query está envuelto en una interfaz para que (en muchos casos) el usuario no sepa que hay un lenguaje subyacente. El lenguaje debajo de la parte de "Datos externos" de Power BI es mucho más fácil de entender que, por ejemplo, el formato del paquete SSIS. M es un tipo de lenguaje funcional que al principio parece algo exótico pero es relativamente fácil trabajar con él en función del código que se genera. Hay varias introducciones decentes a M y cómo usarlas. El uso de Power Query Editor y M se considera que es lo mismo.
 
Cargando (la L en E-T-L)
M tiene una capacidad de carga muy simple. Para Excel, Power BI y SSAS, se carga en una estructura tabular. Esto limita la usabilidad de esta herramienta en esos contextos. Hay métodos para extraer los datos, pero no en una solución robusta. Si uno usa Azure Data Lake, entonces puede usar Power Query para crear salidas que pueden ser utilizadas por otras herramientas de flujo de datos. Esto es nuevo pero muestra dos cosas: que Microsoft está comprometido con el uso de Power Query en más lugares, y que existe una ruta para Power Query como una herramienta ETL de propósito más general.
 
Dado que Analysis Services también tiene esta herramienta desde SQL Server 2017, se puede diseñar un modelo tabular en SSAS utilizando las capacidades de M y luego conectarse a ese servicio en vivo o con una consulta de varios documentos de Power BI. Este diseño es más escalable. Es un paso más en el camino hacia un backend de estilo completo de data mart y es una adición bienvenida por parte de Microsoft.
 
Una limitación en el pasado para Power BI era que (excepto para las conexiones en vivo a SSAS) todos los datos debían ser cargados cada vez que se actualizaban. Hay una nueva función en Premium Power BI (mayo de 2018) que permite la carga incremental de, digamos, solo los últimos 5 días, pero solo está disponible en el servicio premium de Power BI. Cada vez que vuelva a publicar (por ejemplo, después de haber cambiado una visualización), tendrá que volver a cargar todo. Si bien eso abre algunas posibilidades, todavía está limitado en términos de diseño. Las cargas largas, o con frecuencia rotas, son un ejemplo.
 
Extracción (la E en E-T-L)
Aquí es donde m brilla. Es la herramienta de extracción más poderosa que Microsoft pone a disposición en términos de combinación de facilidad de uso y tipos de datos accesibles. El lanzamiento en los data flows del data lake de Azure da la esperanza de que una versión independiente general puede ser posible.
 
La lista de fuentes para Power BI está en constante crecimiento y tiene más de 60 a mediados de 2019.
 
Algunas categorías incluidas son:
 
Raspado web (Web Scraping)
API como Google Analytics, Salesforce y muchos más
Bases de datos SQL
Aplicaciones como Exchange, VSTS y Active Directory
Listas de SharePoint
Web feeds como OData
Saprk y Hadoop HDFS
R Scripts
Python Scripts
Datos autogenerados (por ejemplo, una dimensión de fecha)
… Y muchos otros tipos
 
En última instancia, lo que cada una de las fuentes proporciona es un conjunto de datos de columnas y filas. El proceso de carga les asignará tipos que pueden cambiarse más adelante. Una vez que tengamos uno o más de estos conjuntos de datos, podemos transformarlos.
 
Transformaciones (la T en E-T-L)
Este es un poderoso conjunto de capacidades. M puede hacer lo siguiente:
 
Datos limpios
Eliminar columnas y filas
Remodelar por pivotar o pivotar
Cambiar tipos de datos
Datos del cubo
Datos imputados
Unir consultas con uniones externas o naturales.
Llama modelos de aprendizaje para clasificar.
…y más
 
Cuando lee las recomendaciones para no crear columnas calculadas en Power BI, están diciendo eso en términos de DAX. Sin embargo, debe crear columnas usando M según sea necesario para limpiar los datos, transformarlos en valores útiles, restringirlos y más.
 
Como guía, cualquier cosa que no dependa del contexto no debe estar en DAX.
 
M es muy orientado al flujo de trabajo. Puede ver los "pasos" en los "Pasos aplicados" cuando trabaje en el Power Query Editor. Estos corresponden directamente con las llamadas de la función M. Son visibles en la “barra de fórmulas”. La secuencia de comandos de M completa para una consulta se puede ver haciendo clic derecho en la consulta y seleccionando el "Editor avanzado". En otro post, tomaremos un ejemplo y veremos lo que podemos hacer usando M.
 
Power Query y M son muy poderosos juntos
Cuanto más poder use, más debería considerar si la lógica debería estar centralizada en Analysis Services o SQL. Si muchas personas copian datos en los libros de Power BI por separado, tarde o temprano no coincidirán cuando se utilicen en visualizaciones. Esto es cuando es hora de hablar con profesionales!
 
Si su equipo de BI no tiene habilidades de modelado de datos, los consultores pueden ayudarlo a modelar sus datos de manera adecuada. También pueden crear procesos confiables en torno al rendimiento de la carga, el gobierno de los datos y el archivo. Luego, los usuarios pueden discutir qué significa un número para un proceso de negocio en lugar de cómo se define.
 
Afortunadamente, Power BI permite que el diseño se realice a un nivel más alto y con menos cambios en el front-end.
 
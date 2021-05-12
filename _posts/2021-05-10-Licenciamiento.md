---
layout: single
classes: wide
author_profile: true
author: Esteban Londono
title: "¿Como empezar a usar Power BI en tu Organización?"
excerpt: "Guía de Licenciamiento y Precios de Power BI. Hemos notado que esta confusión en torno a los precios y licenciamiento de Power BI, se genera porque a Microsoft le encanta hacer que las licencias sean flexibles, pero termina con demasiadas opciones que son francamente confusas.Este articulo puede servir como una guía interna de referencia rápida. "
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/wide/dataanalyst.png
  teaser: assets/images/cuadrado/marketing-analyst.png
categories:
  - Introduccion
---
Últimamente hemos recibido muchas preguntas sobre la estrategia de licencias en Power BI. Usualmente estas preguntas nacen durante las primeras sesiones que tenemos con nuestros clientes que buscan ser organizaciones “Impulsadas por datos” (Data Driven) a través de una plataforma de análisis de datos como Power BI.  Algunas de las preguntas que hemos recibido son:
- ¿Cuánto cuesta Power BI?
- ¿Qué licencia debería comprar?
- ¿Power BI es Gratis?
- ¿Qué se requiere para empezar con Power BI?

Hemos notado que esta confusión en torno a los precios y licenciamiento de Power BI, se genera porque a Microsoft le encanta hacer que las licencias sean flexibles, pero termina con demasiadas opciones que son francamente confusas.
**Este articulo puede servir como una guía interna de referencia rápida.** 

Introducción
A la fecha de la escritura de este artículo (10-05-2021) existen al menos cinco [tipos de licencias](https://powerbi.microsoft.com/es-es/pricing/) que Microsoft ofrece para satisfacer las necesidades de sus clientes.

![Comparación Licencias Power BI](/assets/images/post/licenciamiento/ComparacionLicenciasPowerBI.PNG)

## Power BI Free (gratis)
Totalmente gratis obtienes acceso completo a Power BI Desktop [Descarga]( https://powerbi.microsoft.com/es-es/desktop/) la herramienta de diseño y creación de reportes dinámicos. Power BI gratis es la experiencia completa del diseñador de Power BI . Puede crear informes completos para su organización sin gastar un centavo.
También tienes acceso al servicio de Power BI (el término para PowerBI.com) aunque con una gran excepción evidente: compartir .  Para acceder al servicios de Power BI debes tener un [correo electrónico del trabajo, la escuela o el gobierno.](https://docs.microsoft.com/es-es/power-bi/fundamentals/service-self-service-signup-for-power-bi)

Esta es una manera realmente excelente para que su organización ahorre costos en la fase exploratoria al elegir un software de BI. Sin embargo, cuando llegue el momento de implementar su solución, necesitará las capacidades de uso compartido que se otorgan al actualizar su licencia a Pro o Premium .
Debido a que los usuarios de Free no pueden compartir contenido con otros usuarios, solo tienen acceso a su 'Mi espacio de trabajo' personal. Este 'Mi espacio de trabajo' es un área de almacenamiento personalizada para su cuenta y no facilita una distribución o colaboración aceptable. 

Sin compartir capacidades es muy difícil de usar para cualquier empresa. Puede crear informes con todas las funciones, sin embargo, existen capacidades para compartir increíblemente limitadas. Aunque nada le impide enviar un correo electrónico o compartir su archivo .PBIX. Pero **NO recomendamos** usar esto como método de distribución porque existen serias preocupaciones de seguridad y control de versiones. 
Ha habido algunos casos de equipos muy pequeños que comparten una cuenta ADMIN centralizada, sin embargo, **no recomendamos usar PBI gratis como su implementación de producción** de PBI para cualquier equipo de más de dos personas.
 

## Power BI Pro
Pro es la estrategia de licencias más común para Power BI. A $ 10 USD por usuario al mes, Power BI Pro es muy asequible. El precio hace que sea fácil para los primeros usuarios aterrizar y expandirse a otros departamentos por la integración perfecta entre otros usuarios Pro. Cuando un usuario Pro publica su informe en el servicio Power BI, puede compartir inmediatamente ese informe o conjunto de datos con otros usuarios Pro.  Es importante tener en cuenta que, si bien los usuarios Free y Pro pueden existir en la misma organización, los usuarios Free NO PUEDEN interactuar con el contenido creado por los usuarios Pro.

### Espacios de trabajo: 
los espacios de trabajo son generalmente una colección de elementos similares; es posible que tenga un espacio de trabajo de finanzas y un espacio de trabajo de operaciones. Puede agregar colaboradores al espacio de trabajo como visores, colaboradores, miembros y administradores. Los roles son los siguientes:
- Los espectadores tienen derechos de solo lectura en el espacio de trabajo.
- Los colaboradores pueden crear / modificar algunos contenidos y configurar los ajustes de actualización en los conjuntos de datos. También tienen todos los permisos del rol anterior.
- Los miembros pueden publicar / actualizar aplicaciones, compartir elementos distintos con otros usuarios profesionales y crear otros miembros en un espacio de trabajo. También tienen todos los permisos del rol anterior.
- Los administradores tienen el control total del espacio de trabajo y pueden agregar / eliminar cualquier tipo de usuario. También tienen todos los permisos del rol anterior.

### Aplicaciones: 
las aplicaciones son contenido empaquetado y publicado desde un espacio de trabajo; son el mecanismo de control de versiones de Power BI. Una vez que su contenido esté listo para el consumo general, publicará ese contenido como una 'Aplicación' desde el espacio de trabajo. Una vez publicada, el contenido y la estructura de la aplicación permanecerán intactos sin importar lo que suceda con el espacio de trabajo relacionado. Los nuevos cambios en el espacio de trabajo solo entrarán en vigor después de que se hayan publicado. Las aplicaciones pueden tener una audiencia separada de la audiencia del espacio de trabajo relacionada. Una estrategia común es tener usuarios de desarrollo, colaboración y beta en el espacio de trabajo mientras se les brinda a los consumidores acceso a la aplicación. Esto evita que los consumidores estropeen los informes de producción y permite probar los informes en el espacio de trabajo.
Debido a que las aplicaciones pueden tener audiencias divididas y control de versiones, esto hace que las aplicaciones de PowerBI sean un método de distribución ordenado.

## Power BI Premium por Usuario

Es la adición más reciente a la familia Power BI y este nuevo modelo de licencia  llena la brecha entre Power BI Pro y Power BI Premium. Está especialmente creado para empresas que tienen los requisitos analíticos más exigentes pero que no tienen el tamaño empresarial para proporcionar una licencia Premium por capacidad.
Las licencias Premium por usuario no solo ofrecen un mejor rendimiento, sino que también comparten algunas características adicionales importantes. Los usuarios que tienen una licencia Premium (por usuario) obtienen muchos beneficios:
- Mejores flujos de datos;
-	Acceso a informes paginados;
-	Arandes conjuntos de datos con múltiples (hasta 48) refresca por día;
-	Implementación automatizada con canalizaciones de implementación;
-	Extremos de lectura / escritura XMLA;
Los escenarios en los que Power BI Premium por usuario pueden ser interesantes:
-	Un departamento (que es parte de una organización grande) o una organización de tamaño pequeño a mediano, que quiere ser autosuficiente en Analytics y requiere las características más avanzadas de Power BI puede comenzar a un costo razonable con Power BI Premium por usuario.
-	Si desea desarrollar informes paginados imprimibles y con píxeles perfectos, como parte de una Prueba de concepto, puede comenzar poco a poco asignando licencias Premium por usuario a los usuarios. Cuando la Prueba de concepto es exitosa, puede continuar asignando más licencias Premium por usuario a los usuarios con los que desea compartir informes, o puede elegir Power BI Premium.
Tenga en cuenta que los artefactos de Power BI creados dentro de un área de trabajo de Power BI Premium por usuario solo pueden ser consumidos por usuarios con licencia Premium por usuario. Por ejemplo: si un conjunto de datos se crea y se aloja en un espacio de trabajo Premium por usuario, cualquier usuario debe tener una licencia Premium por usuario para ver / acceder al contenido en un espacio de trabajo Premium por usuario.

## Capacidad Premium:
Power BI Premium es el 'nivel' más alto disponible; Premium desbloquea actualizaciones adicionales, límites de almacenamiento de datos más altos, capacidad informática dedicada, capacidades de inteligencia artificial y licencias efectivas ilimitadas y no administradas . Los diversos 'nodos' de Premium solo se relacionan con la potencia informática con licencia. Puede comprar más o menos capacidad en función del nodo que elija. La prima comienza en ~  $ 5,000,  USD esto significa que no es rentable trasladar su organización a PBI-P mientras tenga menos de 500 usuarios.

## Power BI Embedded:

Embedded es una implementación de PowerBI Premium de nicho destinada a aplicaciones y flujos de trabajo personalizados. Embedded resuelve problemas de licencias masivas a consumidores en aplicaciones de terceros. A menudo, Power BI integrado se usa junto con una o dos licencias de Power BI Pro, esos usuarios Pro son responsables de crear contenido que se distribuye a través de la aplicación personalizada. Embedded le permite consultar, invocar RLS y mostrar informes a través de la API de PowerBI. Debido a que Embedded es un servicio, [el precio es por uso](https://azure.microsoft.com/es-es/pricing/details/power-bi-embedded/) comienza desde $ USD 1 la hora aprox $740 USD Mes
Microsoft Power BI Embedded permite a los desarrolladores de aplicaciones insertar en las aplicaciones informes y paneles espectaculares y completamente interactivos, sin tener que dedicar tiempo ni dinero a crear sus propios controles de la nada.

## Conclusiones
La flexibilidad con muchas opciones es un arma de doble filo. Por un lado, puede mezclar y combinar para satisfacer sus necesidades exactas, pero hay muchas consideraciones incluso para lo que parecen ser las decisiones más pequeñas y fáciles.
No esta seguro de cual es la estrategia de licencias adecuada para su organización [contactenos](https://cepobia.com/contacto/)




---
classes: wide
title: "Análisis de hábitos de Lectura en Pocket"
date: 2019-01-15
header:
  teaser: assets/images/teaser/pocket.png
categories:
  - Text Analytics
  - Notebooks
---

# Analisis de los Habitos de Lectura en  [Pocket](https://getpocket.com/)

Cómo he quedado en el 1% de lectores en @Pocket para 2018! he decidido analizar mis datos para tratar de entender mis hábitos de lectura en esta app. Si desean ver el notebook que he utilizado para este análisis lo pueden encontrar en mi github.

La primera pregunta que nos surge al realizar un análisis es ¿qué estamos buscando? ¿O qué queremos encontrar en el análisis?. Casualmente para responder estas preguntas iniciales debemos hacer más preguntas preliminares que creemos que los datos nos pueden ayudar a responder, como:
- ¿Cuántos artículos he agregado a la app en 2018?
- ¿Que % de los artículos agregados son revisados/leídos?
- ¿Cuantas paginas he leído en el 2018?
- ¿Cuantas horas he dedicado a leer en esta app?
- ¿Sobre qué temas tratan los artículos leídos?

Para intentar responder a estas preguntas, seguiremos el flujo normal de un análisis de datos.
Extraer
Limpiar y Trasformar
Analizar y Visualizar.

Extraer los datos.
Aunque la app de pocket permite exportar los datos a un archivo html este es muy limitado, básicamente son los links marcados como leídos y no leídos, por esta razón y por que las APIs son la principal forma de compartir datos entre aplicaciones, y si estamos en el mundo de la ciencia de datos vamos trabajar regularmente con ellas vamos a utilizar la API de pocket para acceder a nuestros datos, en este link puedes encontrar toda la documentación. Normalmente para poder acceder a una API requerimos de credenciales, y esta no es la excepción, para conseguir nuestra consumer_key debemos de crear una app en pocket (https://getpocket.com/developer/apps/new) que va acceder a nuestros datos y para configurar la API debemos seguir los siguientes pasos
Conseguir el token_request. con nuestra consumer_key hacemos una solicitud a la API obtenemos nuestro request_token
Autenticar. Debemos realizar una manualidad para darle permisos a la app de acceder a nuestros datos, en el navegador vamos pegar la URL que esta debajo donde remplazaremos el texto después de ?request_token por el request_token obtenido en el paso anterior. https://getpocket.com/auth/authorize?request_token=PEGA_AQUI_TU REQUEST_TOKEN&amp;amp;amp;amp;amp;amp;amp;amp;amp;redirect_uri=https://getpocket.com/connected_applications
Conseguir el token_access Realizamos una nueva petición con nuestro consumer_key y nuestro token_request para obtener nuestro access_token
Extraer los datos. Obtenemos nuestros datos con la consumer_key y el access_token. En este link podremos profundizar más sobre que datos podemos obtener de la API.

Los pasos del 1–3 solo se realizan una única vez. con las credenciales obtenidas, si los permisos otorgados no se han revocado, podemos seguir llamando nuestros datos las veces que deseemos.

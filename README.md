# Proyecto-CTF
#### Gómez Aldrete Luis Ignacio
#### 216588253
#

Para el proyecto final decidí hacer una aplicación web con microservicios en la que se realiza una encuesta y dependiendo de la versión se tendrá la opción de poder jugar un minijuego en lugar de votar. Además, permitirá de obtener los resultados de la encuesta en tiempo real.

Esta aplicación desplegada en [Developer Sandbox for Red Hat OpenShift](https://developers.redhat.com/developer-sandbox/get-started). Como es una versión de prueba, la aplicación tiende a ponerse en reposo, además de que el servicio de bases de datos no conserva su volumen de almacenamiento y cada cierto tiempo se vacia la base de datos que almacena los votos. 

La aplicación funciona de la siguiente manera, en el enlace para la [App de votacion](https://voting-app-nachogmz-dev.apps.sandbox-m2.ll9k.p1.openshiftapps.com/) se abre la página de votación y puede salir tanto la versión 1 como la versión 2 con un 50% de probabilidad cada una. La versión 2 presenta la elección entre votar y jugar un minijuego, el minijuego es accesible desde la aplicación de votación o también mediante el enlace del [Juego](http://game-app-nachogmz-dev.apps.sandbox-m2.ll9k.p1.openshiftapps.com/). Por útlimo, es posible visualizar en tiempo real la votación entrando al enlace de [Resultados](https://result-app-nachogmz-dev.apps.sandbox-m2.ll9k.p1.openshiftapps.com/).

## Openshift

En la Developex Sandbox de RedHat, se configuraron y desplegaron los servicios necesarios para el funcionamiento de la aplicación.

![Topología del proyecto](https://github.com/Nacho-Gmz/Proyecto-CTF/assets/80866790/9aa5bdf2-44b3-4539-961f-7b53025bbae7)

Se puede observar como es que el servicio de *voting-app* cuenta con dos revisiones: **v1** y **v2**. Cada revisión está configurada para recibir el 50% del tráfico de la ruta para la app de votación.

![Loadbalancer](https://github.com/Nacho-Gmz/Proyecto-CTF/assets/80866790/38b7450a-9f61-400f-9fbf-751959abfcc1)

## Arquitectura del proyecto

![Modelo del proyecto](https://github.com/Nacho-Gmz/Proyecto-CTF/assets/80866790/49861721-265c-448f-b03d-8769c7eaac1c)


# Angular en Docker con Nginx

Este proyecto muestra como desplegar para producción una aplicación Angular en un contenedor Docker sobre el que tenemos Nginx configurado.

La app utlizada no es otra que el Tour of Heroes de Angular: https://angular.io/tutorial

# Como correr el proyecto usando NG:

1. Correr en desarrollo simulando entorno de desarrollo:

$ ng serve 

2. Correr en desarrollo simulando entorno de producción

$ ng serve --prod 

# Como correr el proyecto usando Docker

1. Build de la imagen

$ docker build -t angular-docker-nginx:prod

2. Run de la app

$ docker run -p 80:80 angular-docker-nginx:prod

Ya podemos abrir el navegador y acceder a http://localhost, http://localhost/dashboard o http://localhost/detail/14

# Configuración importantísima para evitar error 404

Toda la base de esta lab ha sido el siguiente artículo: https://medium.com/@tiangolo/angular-in-docker-with-nginx-supporting-environments-built-with-multi-stage-docker-builds-bb9f1724e984

En el se muestra como hacer correr una aplicación Angular creada desde cero en un Nginx ubicado en un contenedor Docker. Mi pequeño cambio ha sido utilizar le Tutorial Tour of Heroes de Google para verificar el acceso directo a rutas de la propia app como puedan ser la ficha de un heroe: /detail/14

Adicionalmente me ha sido de mucha ayuda el siguiente enlace https://angular.io/guide/deployment#server-configuration de la documentación de Angular.

Quiero agradecer a Sebastián Ramírez (@tiangolo) el magnífico trabajo de su artículo.
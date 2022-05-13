# Docker - Reto final

Proceso detallado del uso de Docker Compose y el levantamiento de un conjunto de 5 microservicios de Spring

## Proceso

Primero debemos organizar por carpetas los distintos microservicios, y en el directorio raíz creamos el docker-compose.yml donde editamos y añadimos todas las imágenes que vamos a levantar, las cuales están en cada directorio de sus respectivos servicios que previamente hemos buildeado en Docker (es decir, cada carpeta contiene el .jar y el `Dockerfile` también adjunto en este repositorio)

Luego en cada servicio, al buildearlo, le indicamos en su Dockerfile las instrucciones (puertos, rutas...) para que el compose nos levante cada servicio y establezca sus reglas, como por ejemplo los puertos de cada uno. Tras esto, y una vez terminemos de configurar el `docker-compose.yml`, lanzamos `docker-compose up` y se nos levantan todos los servicios. Cada uno con su puerto mapeado

Para comprobar el funcionamiento de las funciones he usado `Postman`. He probado `localhost:8082/get-all-prices` como ejemplo donde se ven todos los productos
![image](https://user-images.githubusercontent.com/32489904/168285710-e764e1d5-96a0-4960-bfad-267b8180b8f3.png)


Por último y para aclararlo, los `Dockerfile` de cada servicio son exactamente los mismos, por lo que aunque he subido las 5 carpetas, el archivo es común para todos y el puerto a mapear es común

### Comandos

Los comandos han sido los de docker compose a la hora de levantar y matar los servicios

* Iniciar sesión: `docker login -u {usuario}`
* Subir dockerfile con la imagen: `docker build .`
* Levantar docker-compose tras su configuraci-on: `docker-compose up`
* Comprobamos los contenedores activos: `docker ps`
* Apagamos los servicios, para probar, con: `docker-compose down`
* Para comprobar las respuestas: `curl localhost:{puerto_service}`

## ¿Qué he aprendido?

He aprendido a levantar un conjunto de microservicios con Docker Compose con sus dependencias el uno del otro y a configurar las bases de datos de h2 a MySQL. También me he orientado mucho respecto al funcionamiento de Docker en general y sus estructuras, como los archivos, carpetas y directorios

### Comandos aprendidos

En el otro proyecto usé la gran mayo

* `docker-compose up`
* `docker-compose down`
* `docker-compose logs`
* `docker-restart`

## Herramientas

* Docker hub
* Docker compose
* VS Code
* MobaXterm
* Hyper-V
* Postman

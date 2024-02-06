# PruebaDocker
1.- Explica en tus propias palabras qué es Docker y cuál es su propósito principal
R = Es un plataforma que encapsula toda tu aplicación con todas sus dependecias en contenedores

2.- ¿Cuál es la diferencia entre una imagen y un contenedor en Docker?
R = La imagen contiene todas las instrucciones para poder ejecutar nuestra aplicación y un contenedor es una instancia de una imagen, es portable

3.- Proporciona los pasos básicos para instalar Docker en un sistema operativo WINDOWS/LINUX/MAC (ELIGE UNO).
R = WINDOWS:
Tener actualizado el WSL y descargar Docker Desktop

4.- Describe brevemente qué es Docker Hub y cómo se puede utilizar en el contexto de Docker.
R = Es una plataforma la cual contiene un conjunto de imagenes las cuales puedes descargar para utilizar en tus proyectos

5.- Crea un archivo Dockerfile simple que utilice una imagen base de Ubuntu y ejecute el comando "Hello, Docker!" al iniciar el contenedor.  (PARA ESTE CASO PUEDES USAR CHATGPT O BLACKBOX IA)
R =
    # Dentro del archivo index.js hay un console.log("Hola Mundo")
    FROM Ubuntu
    WORKDIR /app
    COPY ..
    CMD["node" "index.js"]

6.- Explica la diferencia entre los comandos docker ps y docker ps -a. ¿Qué información proporciona cada uno?
R = Docker ps enlista los contenedores corriendo y docker ps -a enlista todos, hasta los que no estan corriendo

7.- ¿Cómo se pueden listar las redes disponibles en Docker?
R = docker networks ls

8.- Crea una red en Docker llamada "mi_red" y explica cómo asignar un contenedor a esta red al momento de iniciarlo
R = docker network create mi_red    docker run -d --name container --network mi_red image

9.- Explica la diferencia entre montar un volumen y copiar archivos directamente dentro de un contenedor
R = Una de las principales ventajas de los volumenes es que si se elimina el contenedor, los datos se mantienen en el volumen. También los datos pueden ser compartidos entre varios contenedores. Al copiar los archivos directamente los datos no persisten es decir que solo viven mientras el contenedor este "vivo" 

10.- ¿Qué es Docker Compose y para qué se utiliza?
R = Docker compose facilita la implementación y la administración de aplicación en las cuales se tiene multiples contenedores. Nos permite denifir las configuraciones y los servicios en un archivo llamado docker-compose.yml

11.- Crea un archivo docker-compose.yml para definir dos servicios: uno que utilice la imagen de Mongo y otro que utilice la imagen de Node Version 14. Asegúrate de especificar la red a la que pertenecerán ambos servicios.
R = version: '3'
services:
  mongodb:
    image: mongo
    container_name: mongodb_container
    networks:
      - mi_red

  nodejs:
    image: node:14
    container_name: nodejs_container
    networks:
      - mi_red

networks:
  mi_red:
    driver: bridge
    
12.- Imagina que un contenedor no se inicia correctamente. Proporciona algunos pasos que seguirías para identificar y solucionar el problema. 
R = como primer paso reviso que el contenedor exista y en caso de existir reviso su status actual para esto uso: docerk ps -a
También reviso que la imagen que este utilizando en el contenedor exista o este disponible para esto uso: docker image ls
También reviso el log del contenedor con el comando: docker logs container_id
en caso de que no exista el contenedor hay que volver a crearlo, en caso de que no este corriendo el contenedor se vuelve a correr y haria lo mismo con la imagen en caso de que tuviera algun error por status o de que no existiera

13.- ¿Cómo puedes acceder a la shell de un contenedor en ejecución?
R = docker exec -it container_id /bash

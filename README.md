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

5.- 
    # Dentro del archivo index.js hay un console.log("Hola Mundo")
    FROM Ubuntu
    WORKDIR /app
    COPY ..
    CMD["node" "index.js"]

6.- Explica la diferencia entre los comandos docker ps y docker ps -a. ¿Qué información proporciona cada uno?
R = Docker ps enlista los contenedores corriendo y docker ps -a enlista todos, hasta los que no estan corriendo

7.- ¿Cómo se pueden listar las redes disponibles en Docker?
R = docker networks ls

8.- 

# Volumen

### Crear los volúmenes: Usa el siguiente comando para crear los volúmenes

docker volume create volumen_datos
docker volume create volumen_web


### Arrancar el contenedor c1 sobre la imagen php:7.4-apache:

docker run -d --name c1 -v volumen_web:/var/www/html php:7.4-apache


### Arrancar el contenedor c2 sobre la imagen mariadb:

docker run -d --name c2 -v volumen_datos:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=admin mariadb


### Parar y borrar el contenedor c2

docker stop c2
docker rm c2

### Borrar Volumen_datos

docker volume rm volumen_datos


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Docker/EjerciciosDocker/Tarea07/volumenesCreados.jpg)

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Docker/EjerciciosDocker/Tarea07/arranca%20contenedores.jpg)

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Docker/EjerciciosDocker/Tarea07/eliminamos%20volumen.jpg)
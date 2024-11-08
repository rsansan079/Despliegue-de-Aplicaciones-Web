## Asegúrate de tener Docker instalado

sudo usermod -aG docker $USER

## Ejecuta el contenedor web con la imagen php:7.3-apache

docker run -d --name web -p 8181:80 php:7.3-apache


##  Copiar el archivo index.html al directorio raíz del servicio web en el contenedor. 

echo "<h1>HOLA SOY [Tu Nombre y Apellido]</h1>" > index.html

docker cp index.html web:/var/www/html/

## Copiar el archivo index.php. 

echo "<?php phpinfo(); ?>" > index.php
docker cp index.php web:/var/www/html/

## Verifica que el contenedor web esté en funcionamiento:

docker ps

## Ejecuta el contenedor bbdd con la imagen mariadb

docker run -d --name bbdd -p 3336:3306 \
    -e MYSQL_ROOT_PASSWORD=root \
    -e MYSQL_DATABASE=prueba \
    -e MYSQL_USER=invitado \
    -e MYSQL_PASSWORD=invitado \
    mariadb
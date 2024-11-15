# GESTIÓN DE IMÁGENES

### 1. Descargar la imagen Ubuntu:20.04 desde Docker Hub

docker pull ubuntu:20.04


### 2. Obtener toda la información de la imagen y volcarla a un fichero

docker image inspect ubuntu:20.04 > info.txt


### 3. Instanciar un contenedor basado en la imagen creando uno llamado modulo3

docker run --name modulo3 -d ubuntu:20.04


### 4. Comprobar que el contenedor se ha creado (en ejecución o no)

docker ps -a


### 5. Intentar borrar la imagen Ubuntu:20.04

docker rmi ubuntu:20.04

No se puede borrar la imagen porque está siendo usada por el contenedor modulo3



### 6. Realizar las operaciones necesarias para borrar la imagen

docker rm modulo3

docker rmi ubuntu:20.04


### Explicacion:

Docker no permite eliminar una imagen si hay contenedores (en ejecución o detenidos) que la usan. 



![](




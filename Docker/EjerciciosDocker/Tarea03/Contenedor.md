docker run --name ubuntu -d ubuntu:18.04

### Salir del contenedor y comprobar que se ha parado

docker stop ubuntu

### Para comprobar que el contenedor se ha detenido, ejecuta:
docker ps -a

### Rearrancar el contenedor y comprobar que está funcionando

docker start ubuntu

### Para comprobar que está funcionando, ejecuta nuevamente:
docker ps

### Mostrar el fichero /etc/os-release sin entrar en el contenedor

docker exec ubuntu cat /etc/os-release

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Docker/EjerciciosDocker/Tarea03/ubuntu.jpg)
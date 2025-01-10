# Laboratorio 3

## Ejercicio 1

### Creo Script

#!/bin/bash
clear
echo "Hola Mundo"

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20EJ1.1.jpg)

### Cambiamos permisos y lo hacemos ejecutable

chmod +x test.sh
./test.sh

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej1.2.jpg)
![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej1.3.jpg)


### No usar chmod 777
Dar permisos 777 a un archivo implica que cualquier usuario en el sistema puede leer, escribir y ejecutar


## Ejercicio 2

### Crear los usuarios bob y smith con contraseñas

useradd -d /home/bob bob
mkdir /home/bob
chown bob:bob /home/bob

useradd -d /home/smith smith
mkdir /home/smith
chown smith:smith /home/smith

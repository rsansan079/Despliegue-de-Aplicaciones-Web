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

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej2.1.jpg)
![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej2.2.jpg)

useradd -d /home/smith smith
mkdir /home/smith
chown smith:smith /home/smith

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej2.3.jpg)


## Ejercicio 3

### Crear un directorio público:

mkdir /home/ncs
chmod 777 /home/ncs

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej3.1.jpg)

### Crear un script hello.sh que imprima "Hello World"
sudo nano hello.sh

chmod +x /home/ncs/hello.sh

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej3.2.jpg)
![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej3.3.jpg)
### Ejecutarlo:

./hello.sh

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej3.4.jpg)

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab3/Cap%20Ej3.5.jpg)


## Ejercicio 4

### Iniciar sesión como bob y verificar contenido:

 Presionar Ctrl+Alt+F2 y loguearse como bob
cd /home/ncs
ls

### Ejecutar hello.sh:

./hello.sh


### Crear bob.sh:

echo -e "#!/bin/bash\necho 'Hello this is Bob'" > /home/ncs/bob.sh
chmod +x /home/ncs/bob.sh


![]()



### Iniciar sesión como smith y verificar contenido:

 Presionar Ctrl+Alt+F2 y loguearse como smith
cd /home/ncs
ls


### Ejecutar hello.sh:

./hello.sh

### Crear smith.sh:

echo -e "#!/bin/bash\necho 'Hello this is Smith'" > /home/ncs/smith.sh
chmod +x /home/ncs/smith.sh


![]()

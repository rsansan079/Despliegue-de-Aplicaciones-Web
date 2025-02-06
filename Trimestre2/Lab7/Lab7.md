# PHP Debian

## Ejercicio 7.1: Configuración de Apache

### Propósito de los comentarios (#) en httpd.conf

Los comentarios explican las configuraciones sin afectar el funcionamiento
 del servidor. También se utilizan para desactivar líneas de 
 configuración sin eliminarlas.

 ### Valores por defecto de ServerName y DocumentRoot

ServerName define el nombre del servidor (ejemplo: localhost).
DocumentRoot es la ruta donde se almacenan los archivos web,
 generalmente /var/www/html.

### Efecto de Include /etc/httpd/mod_php.conf

Permite la carga del módulo PHP en Apache, permitiendo
 la ejecución de scripts PHP.



## Ejercicio 7.2: Ejecutando Apache

### Por qué reiniciar httpd tras cambios en la configuración

Apache debe recargar los archivos de configuración para aplicar cambios.

### Análisis del comando ps aux | grep httpd

ps aux muestra procesos en ejecución.
grep httpd filtra los procesos relacionados con Apache.
| es un operador de pipe que pasa la salida de un comando como entrada 
de otro.

### Salida esperada de ps aux | grep httpd

Si httpd está corriendo, se listarán varios procesos de Apache.

Si no está corriendo, solo se mostrará la línea de grep httpd.


## Ejercicio 7.3: Creando archivos HTML

### ¿Qué tiene de especial index.html?

Es la página por defecto que carga Apache si no se especifica otra.

### Permisos y propietario del archivo index.html

ls -l /var/www/html/index.html

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap3.1.jpg)

### Creando test.html

sudo nano /var/www/html/test.html

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap3.2.jpg)


## Ejercicio 7.4: Viendo archivos HTML en terminal

### Diferencia entre CLI y GUI

CLI usa comandos en texto, GUI tiene una interfaz gráfica.

### ¿Qué tiene de especial 127.0.0.1?

Es la dirección local del sistema (localhost).

### Ver test.html en lynx

sudo apt install lynx
lynx 127.0.0.1/test.html

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap4.1.jpg)



## Ejercicio 7.5: Creando y viendo archivos PHP

### Función de phpinfo();

Muestra información de PHP, módulos instalados y configuración.


### Ver nse.php en lynx

sudo nano /var/www/html/nse.php

lynx 127.0.0.1/nse.php

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap5.1.jpg)



## Ejercicio 7.6: Modificando el archivo hosts

### Abrir /etc/hosts y agregar ServerName

sudo nano /etc/hosts

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap6.1.jpg)



### Agrega 127.0.0.1 www.ejemplo.com

lynx www.ejemplo.com


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab7/Cap6.2.jpg)









# Laboratorio 4 : Demonios y Procesos

## Ejercicio 4.1: Explorando procesos en ejecución

### 1. Mostar numeros de procesos

ps aux | wc -l

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej1.1.jpg)

### 2. Los 10 procesos que más CPU consumen:

ps aux --sort=-%cpu | head -n 11

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej1.2.jpg)


## Ejercicio 4.2: Explorando procesos de red

### 1.Listar procesos de red en localhost

nmap localhost

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej2.1.jpg)

### 2.Explicación de los procesos retornados: Para cada proceso listado por nmap, busca su descripción utilizando:

ps aux | grep nombre_del_proceso
man nombre_del_proceso

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej2.2.jpg)

## Ejercicio 4.3: Explorando señales de UNIX

### Listar señales disponibles:

kill -l 

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej3.1.jpg)


## Ejercicio 4.4:  Procesos y redes

### 1.Editar /etc/inetd.conf para habilitar FTP y Telnet:

sudo nano /etc/inetd.conf

![]()

### 2.Reiniciar inetd:

sudo systemctl restart inetd

![]()

### 3.Probar FTP y Telnet:

ftp localhost
telnet localhost

![]()

### 4.Deshabilitar FTP y reiniciar: 

Edita /etc/inetd.conf nuevamente y comenta las líneas de FTP, luego reinicia el servicio.

### Pregunta:

SFTP es una versión segura de FTP que usa el protocolo SSH para la transferencia de archivos.
Telnet no es seguro porque transmite datos en texto plano, lo que permite interceptar contraseñas y datos sensibles.


## Ejercicio 4.5:

### 1.Combinar pidof y kill -HUP:

kill -HUP $(pidof inetd)

### Preguntas:

FTP como root: En sistemas seguros, FTP como root está deshabilitado por defecto para evitar vulnerabilidades. Es mejor crear un usuario dedicado con permisos específicos.

Conexión desde Windows: Desde una máquina Windows, usa un cliente como PuTTY para Telnet o FileZilla para FTP.


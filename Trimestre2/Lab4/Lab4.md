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

![]()

### 2.Explicación de los procesos retornados: Para cada proceso listado por nmap, busca su descripción utilizando:

ps aux | grep nombre_del_proceso
man nombre_del_proceso

![]()

## Ejercicio 4.3: Explorando señales de UNIX

### Listar señales disponibles:

kill -l 

![]()


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


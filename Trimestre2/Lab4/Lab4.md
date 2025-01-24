# Laboratorio 4 : Demonios y Procesos

## Ejercicio 4.1: Explorando procesos en ejecución

### 1. Mostar numeros de procesos

ps aux | wc -l

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej1.1.jpg)

### 2. Los 10 procesos que más CPU consumen:

ps aux --sort=-%cpu | head -n 11

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab4/Ej1.2.jpg)

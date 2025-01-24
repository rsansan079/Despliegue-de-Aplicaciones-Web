# Laboratorio 4 : Demonios y Procesos

## Ejercicio 4.1: Explorando procesos en ejecución

### 1. Mostar numeros de procesos

ps aux | wc -l

![]()

### 2. Los 10 procesos que más CPU consumen:

ps aux --sort=-%cpu | head -n 11

![]()

# Lab09: Network traffic analysis

## Ejercicio 9.1 - Listar máquinas activas en la red

### Crea el archivo y edítalo:

nano ping.sh

#!/bin/bash
Cambia la base de dirección según tu red local (por ejemplo, 192.168.1)
for ip in 192.168.1.{1..255}; do
    ping -c 2 $ip &> /dev/null
    if [ $? -eq 0 ]; then
        echo "$ip está activo"
    fi
done

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap9.1.jpg)

### Otorga permisos de ejecución:

chmod +x ping.sh

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap9.2.jpg)


### Ejecuta el script:

./ping.sh

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap9.3.jpg)


## Ejercicio 10.1 - Información de usuarios y sistema

### Número de intentos de inicio de sesión (éxito y fallidos):

last -F | grep "$(date --date='2 days ago' '+%Y-%m-%d')" | wc -l

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.1.1.jpg)


### Número de reinicios del sistema en las últimas 48 horas:

last reboot -F | grep "$(date --date='2 days ago' '+%Y-%m-%d')" | wc -l

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.1.2.jpg)


## Ejercicio 10.2 - Enlaces simbólicos y duros

### Crea un archivo y un enlace simbólico:

mkdir -p ~/unixstuff/links
touch ~/unixstuff/extra_file
ln -s ~/unixstuff/extra_file ~/unixstuff/links/extra_file_link
ls -l ~/unixstuff/links/

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.1.jpg)

###  Modifica extra_file y verifica el enlace:

echo "Hola, soy un archivo" >> ~/unixstuff/extra_file
cat ~/unixstuff/links/extra_file_link

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.2.jpg)

### Mueve extra_file a backups/ y verifica el estado del enlace:

mkdir -p ~/unixstuff/backups
mv ~/unixstuff/extra_file ~/unixstuff/backups/
cat ~/unixstuff/links/extra_file_link

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.3.jpg)


### Vuelve a mover el archivo y verifica:

mv ~/unixstuff/backups/extra_file ~/unixstuff/
cat ~/unixstuff/links/extra_file_link

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.4.jpg)


### Borra extra_file_link y revisa extra_file:

rm ~/unixstuff/links/extra_file_link
cat ~/unixstuff/extra_file

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.5.jpg)


### Crea un nuevo enlace, elimina extra_file y revisa extra_file_link:

ln -s ~/unixstuff/extra_file ~/unixstuff/links/extra_file_link
rm ~/unixstuff/extra_file
cat ~/unixstuff/links/extra_file_link

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.6.jpg)


### Repite todo el proceso con un enlace duro:

ln ~/unixstuff/extra_file ~/unixstuff/links/extra_file_hard

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.7.jpg)


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.8.jpg)


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.9.jpg)


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.10.jpg)


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab9/Cap10.2.11.jpg)


### Diferencias:

Enlace simbólico: Si el archivo original se mueve o borra, el enlace se rompe.
Enlace duro: Mantiene acceso a los datos incluso si el archivo original se borra.


# Email for Linux

## Ejercicio 6.1: Enviar un correo usando mail

### Crea un archivo llamado message.txt:

echo "Hola Bob, este es un mensaje de prueba." > message.txt

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap1.1.jpg)

### Enviar:

mail -s "Prueba de correo" bob@localhost < message.txt

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap1.3.jpg)

### Explicación del comando:

echo "Welcome to Network Computer Systems" | mail -s "Hello world" bob@anglia.bryant -c smith@anglia.bryant -b root@anglia.bryant

Envía el mensaje "Welcome to Network Computer Systems" como cuerpo.
Usa "Hello world" como asunto.
Lo envía a bob@anglia.bryant.
Envía una copia al destinatario smith@anglia.bryant y una copia oculta a root@anglia.bryant.

##  Ejercicio 6.2: Verificar correos 

### Inicia sesión como bob:

### Lee los correos usando mail:

mail

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap2.1.jpg)

## Ejercicio 6.3: Explorar comando mail

### Acciones comunes en mail:

Leer: Escribe el número del mensaje.
Responder: Escribe r <número_del_mensaje>.
Enviar nuevo mensaje: Escribe m usuario.
Eliminar: Escribe d <número_del_mensaje>.
Listar mensajes: Escribe h.
Guardar: Escribe s <número_del_mensaje> <archivo>.

### Contenido de /var/spool/mail/:

ls -l /var/spool/mail/

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap3.1.jpg)

### Sesión SMTP: Desde la máquina Windows:

telnet <ip_debian> 25

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap3.2.jpg)

### Habilitar POP3: Edita /etc/inetd.conf para descomentar la línea de POP3:

pop3 stream tcp nowait root /usr/sbin/tcpd /usr/sbin/pop3d

Reinicia el servicio inetd

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap3.3.jpg)

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab6/Cap3.4.jpg)
## Ejercicio 6.4 OPcional

### IMAP:

Protocolo más avanzado que POP3.
Permite sincronización en múltiples dispositivos.
Usa el puerto 143 o 993 (seguro).

### PGP (Pretty Good Privacy):

Sistema de encriptación para correos.
Usa clave pública y privada para garantizar confidencialidad e integridad.



# DNS Rafael Sanchez 2DAW

## Instalar bind9

sudo apt update

sudo apt install bind9 bind9utils bind9-doc dnsutils

## Configurar IP estática

Edita el archivo /etc/network/interfaces

sudo nano /etc/network/interfaces

### Ejemplo:

auto eth0
iface eth0 inet static
    address 10.0.2.15
    netmask 255.255.255.0
    gateway 10.0.2.1

### Reiniciamos el servicio de red
sudo systemctl restart networking


## Configurar named.conf.options

sudo nano /etc/bind/named.conf.options

### Dentro del bloque options, agrega los forwarders (por ejemplo, los DNS de Google):

options {
    directory "/var/cache/bind";
    forwarders {
        8.8.8.8;
        8.8.4.4;
    };
    dnssec-validation auto;
    auth-nxdomain no;    # conform to RFC1035
    listen-on-v6 { any; };
};

### Guarda el archivo y reinicia el servicio bind9:

sudo systemctl restart bind9

## Configurar las zonas de búsqueda directa e inversa
sudo nano /etc/bind/named.conf.local

### Agregamos

zone "ejemplo.com" {
    type master;
    file "/etc/bind/db.ejemplo.com";
};

zone "2.0.10.in-addr.arpa" {
    type master;
    file "/etc/bind/db.10.0.2";
};



## Configurar los archivos de zona

### Directa:
sudo cp /etc/bind/db.local /etc/bind/db.ejemplo.com

sudo nano /etc/bind/db.ejemplo.com

### Contenido: 

$TTL 604800
@   IN  SOA ns.ejemplo.com. admin.ejemplo.com. (
         2     ; Serial
    604800     ; Refresh
     86400     ; Retry
   2419200     ; Expire
    604800 )   ; Negative Cache TTL
;
@   IN  NS  ns.ejemplo.com.
ns  IN  A   10.0.2.15
www IN  A   10.0.2.15



### Inversa

sudo cp /etc/bind/db.127 /etc/bind/db.10.0.2
sudo nano /etc/bind/db.10.0.2

### Contenido

$TTL 604800
@   IN  SOA ns.ejemplo.com. admin.ejemplo.com. (
         1     ; Serial
    604800     ; Refresh
     86400     ; Retry
   2419200     ; Expire
    604800 )   ; Negative Cache TTL
;
@   IN  NS  ns.ejemplo.com.
15  IN  PTR ejemplo.com.



## Configurar resolv.conf

sudo nano /etc/resolv.conf

Agregamos:

domain ejemplo.com

search ejemplo.com

nameserver 10.0.2.15


## Verificamos configuracion

sudo named-checkconf

sudo named-checkzone ejemplo.com /etc/bind/db.ejemplo.com

sudo named-checkzone 2.0.10.in-addr.arpa /etc/bind/db.10.0.2

## Reiniciamos bind9

sudo systemctl restart bind9


## Comprobamos DNS

nslookup ejemplo.com

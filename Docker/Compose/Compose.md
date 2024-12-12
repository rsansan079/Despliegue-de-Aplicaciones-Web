# Configuración inicial de Debian y Docker Compose


### 1.Instalar Docker:

sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER

### Reiniciamos la sesion(IMPORTANTE)

### Crea un directorio para el proyecto MediaWiki:

mkdir /mediawiki 
cd /mediawiki

### Creamos el archivo docker-compose.yml(Estos parametros)

version: '3.3'
services:
  mediawiki:
    image: mediawiki:latest
    container_name: mediawiki
    ports:
      - "8080:80" # Cambia el puerto 8080 si está ocupado
    volumes:
      - mediawiki-data:/var/www/html
    environment:
      - MEDIAWIKI_SITE_NAME=MiWiki
      - MEDIAWIKI_SITE_LANG=es
      - MEDIAWIKI_ADMIN_USER=admin
      - MEDIAWIKI_ADMIN_PASS=admin123
      - MEDIAWIKI_DB_TYPE=mysql
      - MEDIAWIKI_DB_HOST=db
      - MEDIAWIKI_DB_NAME=mediawiki
      - MEDIAWIKI_DB_USER=mediawikiuser
      - MEDIAWIKI_DB_PASS=mediawikipass
    depends_on:
      - db

  db:
    image: mariadb:10.5
    container_name: mariadb
    environment:
      - MYSQL_ROOT_PASSWORD=rootpassword
      - MYSQL_DATABASE=mediawiki
      - MYSQL_USER=mediawikiuser
      - MYSQL_PASSWORD=mediawikipass
    volumes:
      - db-data:/var/lib/mysql

volumes:
  mediawiki-data:
  db-data:

### Levantamos contenedores

docker-compose up -d


![]()

![]()



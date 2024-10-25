# Instalar Docker
### Actualiza el índice de paquetes:
sudo apt update


###  Instala los paquetes necesarios para permitir apt usar paquetes a través de HTTPS:
sudo apt install apt-transport-https ca-certificates curl software-properties-common

### Añade la clave GPG oficial de Docker:
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -


### Añade el repositorio de Docker:
echo "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list

### Actualiza el índice de paquetes de nuevo:
sudo apt update

### Instala Docker:
sudo apt install docker-ce

### Configurar Docker para ejecutar sin permisos de administrador
Agrega tu usuario al grupo docker:

sudo usermod -aG docker sansanra


### Cierra la sesión y vuelve a iniciarla para que los cambios tengan efecto.
### Verificar la versión de Docker
Ejecuta el siguiente comando para obtener la versión instalada de Docker:

docker --version

### Ejecutar "Hola Mundo"
Para ejecutar el contenedor que muestra "Hola Mundo", utiliza el siguiente comando:
docker run hello-world
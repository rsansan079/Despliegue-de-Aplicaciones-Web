# Ejercicio 8.1

## Para obtener el número de entradas en la tabla de usuarios de la base de datos mysql:

SELECT User, Host FROM mysql.user;

## Comandos SQL básicos para trabajar con tablas:

### Crear una tabla:

CREATE TABLE nombre_tabla (
    id INT PRIMARY KEY,
    columna1 VARCHAR(50),
    columna2 INT
);

### Eliminar tabla

DROP TABLE nombre_tabla;

### Seleccionar datos de una tabla

SELECT * FROM nombre_tabla;

### Insertar datos en una tabla

INSERT INTO nombre_tabla (id, columna1, columna2) VALUES (1, 'Ejemplo', 100);


## Crear la base de datos nselab y la tabla users:

CREATE DATABASE nselab;
USE nselab;

CREATE TABLE users (
    studentid INT AUTO_INCREMENT PRIMARY KEY,
    firstname VARCHAR(25) NOT NULL,
    lastname VARCHAR(25) NOT NULL
);


### Insertar los estudiantes Joe Bloggs y Ashley Smith:

INSERT INTO users (firstname, lastname) VALUES ('Joe', 'Bloggs');
INSERT INTO users (firstname, lastname) VALUES ('Ashley', 'Smith');



# Ejercicio 8.2

### Crear un usuario MySQL adminsec con privilegios solo en nselab:

CREATE USER 'adminsec'@'localhost' IDENTIFIED BY 'password123';
GRANT ALL PRIVILEGES ON nselab.* TO 'adminsec'@'localhost';
FLUSH PRIVILEGES;


### Crear una página PHP para mostrar los usuarios en la base de datos:

!()[]

### Explicación:

Se conecta a MySQL usando mysqli.
Se ejecuta un SELECT para obtener los datos de la tabla users.
Se imprimen los resultados en una tabla HTML.

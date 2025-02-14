# Ejercicio 8.1

## Para obtener el número de entradas en la tabla de usuarios de la base de datos mysql:

SELECT User, Host FROM mysql.user;

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.1.jpg)

## Comandos SQL básicos para trabajar con tablas:

### Crear una tabla:

CREATE TABLE nombre_tabla (
    id INT PRIMARY KEY,
    columna1 VARCHAR(50),
    columna2 INT
);

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.2.jpg)

### Eliminar tabla

DROP TABLE nombre_tabla;


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.3.jpg)

### Seleccionar datos de una tabla

SELECT * FROM nombre_tabla;


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.4.jpg)

### Insertar datos en una tabla

INSERT INTO nombre_tabla (id, columna1, columna2) VALUES (1, 'Ejemplo', 100);


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.5.jpg)


## Crear la base de datos nselab y la tabla users:

CREATE DATABASE nselab;
USE nselab;

CREATE TABLE users (
    studentid INT AUTO_INCREMENT PRIMARY KEY,
    firstname VARCHAR(25) NOT NULL,
    lastname VARCHAR(25) NOT NULL
);


![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.6.jpg)


### Insertar los estudiantes Joe Bloggs y Ashley Smith:

INSERT INTO users (firstname, lastname) VALUES ('Joe', 'Bloggs');
INSERT INTO users (firstname, lastname) VALUES ('Ashley', 'Smith');

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap1.7.jpg)


# Ejercicio 8.2

### Crear un usuario MySQL adminsec con privilegios solo en nselab:

CREATE USER 'adminsec'@'localhost' IDENTIFIED BY 'password123';
GRANT ALL PRIVILEGES ON nselab.* TO 'adminsec'@'localhost';
FLUSH PRIVILEGES;

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap2.1.jpg)



### Crear una página PHP para mostrar los usuarios en la base de datos:

![](https://github.com/rsansan079/Despliegue-de-Aplicaciones-Web/blob/master/Trimestre2/Lab8/Cap2.2.jpg)

### Explicación:

Se conecta a MySQL usando mysqli.
Se ejecuta un SELECT para obtener los datos de la tabla users.
Se imprimen los resultados en una tabla HTML.

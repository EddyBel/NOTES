---
Completado: Yes
Dificultad: ⭐
Etiquetas: Bases, Bases de datos, Conceptos, SQL
Fecha: March 1, 2023
---

# Bases de SQL

SQL (Structured Query Language) es un lenguaje de programación utilizado para administrar bases de datos relacionales entre otras funciones como:

- Gestión de bases de datos: SQL se utiliza para crear y gestionar bases de datos. Permite crear tablas, definir relaciones entre ellas y modificar su estructura.
- Consultas de datos: SQL se utiliza para consultar datos almacenados en una base de datos. Permite buscar, ordenar y filtrar información específica de una base de datos.
- Actualización de datos: SQL se utiliza para actualizar datos existentes en una base de datos. Permite modificar registros, agregar nuevos registros y eliminar registros existentes.
- Generación de informes: SQL se utiliza para generar informes basados en los datos almacenados en una base de datos. Permite seleccionar y organizar los datos para crear informes personalizados.
- Integración de datos: SQL se utiliza para integrar datos de varias fuentes en una sola base de datos. Permite unificar datos de diferentes fuentes para su análisis y uso en informes.

En este documento, se explicarán las bases de SQL para comenzar a trabajar con este lenguaje.

## Creación de una tabla

La creación de una tabla es una de las primeras cosas que se debe hacer al trabajar con SQL. La sintaxis para crear una tabla es la siguiente:

```sql
CREATE TABLE nombre_de_la_tabla (
  columna1 tipo_de_dato,
  columna2 tipo_de_dato,
  columna3 tipo_de_dato,
  ...
);

```

Por ejemplo, para crear una tabla llamada "clientes" con las columnas "id", "nombre" y "edad", se puede utilizar la siguiente sintaxis:

```sql
CREATE TABLE clientes (
  id INT,
  nombre VARCHAR(50),
  edad INT
);

```

## Inserción de datos

Una vez que se ha creado una tabla, se puede insertar datos en ella. La sintaxis para insertar datos en una tabla es la siguiente:

```sql
INSERT INTO nombre_de_la_tabla (columna1, columna2, columna3, ...)
VALUES (valor1, valor2, valor3, ...);
```

Por ejemplo, para insertar un nuevo cliente en la tabla "clientes", se puede utilizar la siguiente sintaxis:

```sql
INSERT INTO clientes (id, nombre, edad)
VALUES (1, 'Juan', 25);
```

## Selección de datos

Para seleccionar datos de una tabla, se utiliza la siguiente sintaxis:

```sql
SELECT columna1, columna2, columna3, ...
FROM nombre_de_la_tabla;
```

Por ejemplo, para seleccionar todos los clientes de la tabla "clientes", se puede utilizar la siguiente sintaxis:

```sql
SELECT id, nombre, edad
FROM clientes;
```

## Actualización de datos

Para actualizar datos en una tabla, se utiliza la siguiente sintaxis:

```sql
UPDATE nombre_de_la_tabla
SET columna1 = valor1, columna2 = valor2, ...
WHERE condicion;
```

Por ejemplo, para actualizar la edad del cliente con id 1 en la tabla "clientes", se puede utilizar la siguiente sintaxis:

```sql
UPDATE clientes
SET edad = 26
WHERE id = 1;
```

## Eliminación de datos

Para eliminar datos de una tabla, se utiliza la siguiente sintaxis:

```sql
DELETE FROM nombre_de_la_tabla
WHERE condicion;
```

Por ejemplo, para eliminar el cliente con id 1 de la tabla "clientes", se puede utilizar la siguiente sintaxis:

```sql
DELETE FROM clientes
WHERE id = 1;
```

# Práctica Northwind SQL - Isaac sanchez garcia

## Descripción
Esta práctica consiste en la creación, carga y explotación de la base de datos Northwind en PostgreSQL, utilizando pgAdmin como herramienta de administración y consulta. El trabajo incluye la creación de la estructura de la base de datos, la carga del script SQL y la elaboración del diagrama entidad-relación (ER) correspondiente.

## Versiones utilizadas
- PostgreSQL
- pgAdmin

## Requisitos
Antes de comenzar, asegúrate de tener instalado lo siguiente:
- PostgreSQL
- pgAdmin
- El script SQL de la base de datos Northwind

## Cómo reproducir el trabajo

### 1. Crear la base de datos
Desde pgAdmin:
1. Abre pgAdmin.
2. Conéctate al servidor PostgreSQL.
3. Haz clic derecho en "Databases".
4. Selecciona "Create" > "Database".
5. Asigna el nombre `northwind`.

También puedes crearlo desde línea de comandos:

```sql
CREATE DATABASE northwind;
```
### 2. Cargar el script SQL
Una vez creada la base de datos, carga el script que contiene la estructura y los datos de Northwind.

Desde pgAdmin:

1. Selecciona la base de datos northwind.
2. Abre el "Query Tool".
3. Cargue el archivo .sqlde la práctica.
4. Ejecuta el script para crear las tablas e insertar los datos.

## Diagrama ER
A continuación se muestra el diagrama ER generado en la Parte 1 de la práctica:

![Diagrama ER de Northwind](./images/diagrapgerd.png)


Índice
![Readme](./respuestas.md)


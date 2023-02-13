

# Crear Base de Datos 


```sql
DROP TABLE IF EXISTS world;

CREATE TABLE world (
name varchar(35),
continent varchar(20),
area decimal,
population integer,
gdp double precision,
capital varchar(30),
tld varchar(5),
flag varchar(100)
);

COPY world
FROM '/private/tmp/Tabla_World2.csv'
WITH (FORMAT CSV, HEADER TRUE, DELIMITER ';');
````



# Crear Base de Datos 

> Nota: Revisar que los carácteres de la tabla coincidan con la variables descrita, por ejemplo nnúmeros muy grandes con notación científica, en este caso si esta en excel, simplemente se ajusta el formato de la columna a número sin decimales; también puede que una palabra exceda el número de carácteres dados para varchar.
> Importante tener en cuenta el DELIMITER, en este caso como la tabla tenía antes decimales, al convertir de excel a CSV los espacios se reemplazaron con (;) y no con (,) entonces debe escribirse así. 
> Cuando los títulos de las columnas hacen parte de la base de datos, se debe incluir el operador HEADER **TRUE**, sino las tuviera, seria HEADER **FALSE**


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

SELECT *
FROM world
````

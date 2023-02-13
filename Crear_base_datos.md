

# Crear Base de Datos 

> Notas
>*1. Revisar que los carácteres de la tabla coincidan con la variables descrita, por ejemplo números muy grandes con notación científica, en este caso si esta en excel, simplemente se ajusta el formato de la columna a número sin decimales; también puede que una palabra exceda el número de carácteres dados para varchar.
>*2. Importante tener en cuenta el DELIMITER, en este caso como la tabla tenía antes decimales, al convertir de excel a CSV los espacios se reemplazaron con (;) y no con (,) entonces debe escribirse así. 
>*3. Cuando los títulos de las columnas hacen parte de la base de datos, se debe incluir el operador HEADER **TRUE**, sino las tuviera, seria HEADER **FALSE**
>*4. Para insertar la ubicación del archivo, en este caso: /private/tmp, se debe copiar del archivo de CSV de la Mac: click derecho, obtener información, copiar ubicación. Este archivo siempre debe estar en los temporales de la Mac.


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

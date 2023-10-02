```sql
-- Lista el nombre de todos los productos que hay en la tabla producto.
SELECT nombre FROM producto;

-- Lista los nombres y los precios de todos los productos de la tabla producto.
SELECT nombre, precio FROM producto;

-- Lista todas las columnas de la tabla producto.
SHOW COLUMNS FROM producto;

-- Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).
SELECT nombre, 'euros', 'dólares' FROM producto;

-- Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD) con alias para las columnas.
SELECT nombre AS 'nombre de producto', precio AS 'euros', precio AS 'dólares' FROM producto;

-- Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.
SELECT UPPER(nombre) AS 'nombre', precio FROM producto;

-- Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.
SELECT LOWER(nombre) AS 'nombre', precio FROM producto;

-- Lista el nombre de todos los fabricantes en una columna y los dos primeros caracteres en mayúsculas en otra columna.
SELECT nombre, UPPER(SUBSTRING(nombre, 1, 2)) FROM fabricante;

-- Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.
SELECT nombre, ROUND(precio) FROM producto;

-- Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio sin cifras decimales.
SELECT nombre, CAST(precio AS SIGNED) FROM producto;

-- Lista el código de los fabricantes que tienen productos en la tabla producto.
SELECT codigo_fabricante FROM producto WHERE codigo_fabricante IS NOT NULL;

-- Lista el código de los fabricantes que tienen productos en la tabla producto, eliminando los códigos que aparecen repetidos.
SELECT DISTINCT codigo_fabricante FROM producto;

-- Lista los nombres de los fabricantes ordenados de forma ascendente.
SELECT nombre_fabricante FROM fabricante ORDER BY nombre_fabricante ASC;

-- Lista los nombres de los fabricantes ordenados de forma descendente.
SELECT nombre_fabricante FROM fabricante ORDER BY nombre_fabricante DESC;

-- Lista los nombres de los productos ordenados por nombre ascendente y precio descendente.
SELECT nombre_producto, precio_producto FROM producto ORDER BY nombre_producto ASC, precio_producto DESC;

-- Devuelve una lista con las 5 primeras filas de la tabla fabricante.
SELECT * FROM fabricante LIMIT 5;

-- Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante, incluyendo la cuarta fila.
SELECT * FROM fabricante LIMIT 2 OFFSET 3;

-- Lista el nombre y el precio del producto más barato.
SELECT nombre, precio FROM producto ORDER BY precio ASC LIMIT 1;

-- Lista el nombre y el precio del producto más caro.
SELECT nombre, precio FROM producto ORDER BY precio DESC LIMIT 1;

-- Lista el nombre de todos los productos del fabricante cuyo código de fabricante es igual a 2.
SELECT nombre FROM producto WHERE codigo_fabricante = 2;

-- Lista el nombre de los productos que tienen un precio menor o igual a 120€.
SELECT nombre FROM producto WHERE precio <= 120;

-- Lista el nombre de los productos que tienen un precio mayor o igual a 400€.
SELECT nombre FROM producto WHERE precio >= 400;

-- Lista el nombre de los productos que no tienen un precio mayor o igual a 400€.
SELECT nombre FROM producto WHERE precio < 400;

-- Lista todos los productos que tengan un precio entre 80€ y 300€ sin utilizar el operador BETWEEN.
SELECT nombre FROM productos WHERE precio >= 80 AND precio <= 300;

-- Lista todos los productos que tengan un precio entre 60€ y 200€ utilizando el operador BETWEEN.
SELECT nombre FROM productos WHERE precio BETWEEN 60 AND 200;

-- Lista todos los productos que tengan un precio mayor que 200€ y el código de fabricante sea igual a 6.
SELECT nombre FROM producto WHERE precio > 200 AND codigo_fabricante = 6;

-- Lista todos los productos donde el código de fabricante sea 1, 3 o 5 sin utilizar el operador IN.
SELECT nombre FROM producto WHERE codigo_fabricante = 1 OR codigo_fabricante = 3 OR codigo_fabricante = 5;

-- Lista todos los productos donde el código de fabricante sea 1, 3 o 5 utilizando el operador IN.
SELECT nombre FROM producto WHERE codigo_fabricante IN (1, 3, 5);

-- Lista el nombre y el precio de los productos en céntimos (multiplicados por 100) con alias para la columna que contiene el precio en céntimos.
SELECT nombre, precio * 100 AS 'céntimos' FROM producto;

-- Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.
SELECT nombre_fabricante FROM fabricante WHERE nombre_fabricante LIKE 'S%';

-- Lista los nombres de los fabricantes cuyo nombre termine por la vocal "e".
SELECT nombre_fabricante FROM fabricante WHERE nombre_fabricante LIKE '%e';

-- Lista los nombres de los fabricantes cuyo nombre contenga el carácter "w".
SELECT nombre_fabricante FROM fabricante WHERE nombre_fabricante LIKE '%w%';

-- Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.
SELECT nombre_fabricante FROM fabricante WHERE LENGTH(nombre_fabricante) = 4;

-- Devuelve una lista con el nombre de todos los productos que contienen la cadena "Portátil" en el nombre.
SELECT nombre FROM producto WHERE nombre LIKE '%Portátil%';

-- Devuelve una lista con el nombre de todos los productos que contienen la cadena "Monitor" en el nombre y tienen un precio inferior a 215 €.
SELECT nombre FROM producto WHERE nombre LIKE '%Monitor%' AND precio < 215;

-- Lista el nombre y el precio de todos los productos que tienen un precio mayor o igual a 180€, ordenando por precio (descendente) y nombre (ascendente).
SELECT nombre, precio FROM producto WHERE precio >= 180 ORDER BY precio DESC, nombre ASC;
```
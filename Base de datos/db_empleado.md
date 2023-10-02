```sql
USE empleados;

-- Lista el primer apellido de todos los empleados.
SELECT apellido1 FROM empleado;

-- Lista el primer apellido de los empleados eliminando los apellidos que estén repetidos.
SELECT DISTINCT apellido1 FROM empleado;

-- Lista todas las columnas de la tabla empleado.
SELECT * FROM empleado;

-- Lista el nombre y los apellidos de todos los empleados.
SELECT nombre, apellido1, apellido2 FROM empleado;

-- Lista el código de los departamentos de los empleados que aparecen en la tabla empleado.
SELECT codigo_departamento FROM empleado;

-- Lista el código de los departamentos de los empleados que aparecen en la tabla empleado, eliminando los códigos que aparecen repetidos.
SELECT DISTINCT codigo_departamento FROM empleado;

-- Lista el nombre y apellidos de los empleados en una única columna.
SELECT CONCAT_WS(' ', nombre, apellido1, apellido2) AS nombre_completo FROM empleado;

-- Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en mayúscula.
SELECT UPPER(CONCAT_WS(' ', nombre, apellido1, apellido2)) AS nombre_completo FROM empleado;

-- Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en minúscula.
SELECT LOWER(CONCAT_WS(' ', nombre, apellido1, apellido2)) AS nombre_completo FROM empleado;

-- Lista el código de los empleados junto al NIF, separando los dígitos del NIF y la letra en columnas distintas.
SELECT codigo_departamento, LEFT(nif, LENGTH(nif) - 1) AS digitos_nif, RIGHT(nif, 1) AS letra_nif FROM empleado;

-- Lista el nombre de cada departamento y el valor del presupuesto actual (restando gastos del presupuesto inicial).
SELECT nombre, presupuesto - gastos AS Presupuesto_Actual FROM departamento;

-- Lista el nombre de los departamentos y el valor del presupuesto actual ordenado de forma ascendente.
SELECT nombre, presupuesto - gastos AS Presupuesto_Actual FROM departamento ORDER BY Presupuesto_Actual ASC;

-- Lista el nombre de todos los departamentos ordenados de forma ascendente.
SELECT nombre FROM departamento ORDER BY nombre ASC;

-- Lista el nombre de todos los departamentos ordenados de forma descendente.
SELECT nombre FROM departamento ORDER BY nombre DESC;

-- Lista los apellidos y el nombre de todos los empleados, ordenados alfabéticamente por apellidos y luego por nombre.
SELECT nombre, apellido1, apellido2 FROM empleado ORDER BY apellido1 ASC, apellido2 ASC, nombre ASC;

-- Devuelve una lista con el nombre y el presupuesto de los 3 departamentos que tienen mayor presupuesto.
SELECT nombre, presupuesto FROM departamento ORDER BY presupuesto DESC LIMIT 3;

-- Devuelve una lista con el nombre y el presupuesto de los 3 departamentos que tienen menor presupuesto.
SELECT nombre, presupuesto FROM departamento ORDER BY presupuesto ASC LIMIT 3;

-- Devuelve una lista con el nombre y el gasto de los 2 departamentos que tienen mayor gasto.
SELECT nombre, gastos FROM departamento ORDER BY gastos DESC LIMIT 2;

-- Devuelve una lista con el nombre y el gasto de los 2 departamentos que tienen menor gasto.
SELECT nombre, gastos FROM departamento ORDER BY gastos ASC LIMIT 2;

-- Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado, incluyendo la tercera fila.
SELECT * FROM empleado LIMIT 5 OFFSET 2;

-- Devuelve una lista con el nombre de los departamentos y el presupuesto de aquellos con presupuesto mayor o igual a 150,000 euros.
SELECT nombre, presupuesto FROM departamento WHERE presupuesto >= 150000;

-- Devuelve una lista con el nombre de los departamentos y el gasto de aquellos con gasto menor de 5000 euros.
SELECT nombre, gastos FROM departamento WHERE gastos < 5000;

-- Devuelve una lista con el nombre de los departamentos y el presupuesto de aquellos con presupuesto entre 100,000 y 200,000 euros.
SELECT nombre, presupuesto FROM departamento WHERE presupuesto >= 100000 AND presupuesto <= 200000;

-- Devuelve una lista con el nombre de los departamentos que no tienen presupuesto entre 100,000 y 200,000 euros.
SELECT nombre FROM departamento WHERE presupuesto < 100000 OR presupuesto > 200000;

-- Devuelve una lista con el nombre de los departamentos que tienen presupuesto entre 100,000 y 200,000 euros utilizando el operador BETWEEN.
SELECT nombre FROM departamento WHERE presupuesto BETWEEN 100000 AND 200000;

-- Devuelve una lista con el nombre de los departamentos que no tienen presupuesto entre 100,000 y 200,000 euros utilizando el operador BETWEEN.
SELECT nombre FROM departamento WHERE NOT (presupuesto BETWEEN 100000 AND 200000);

-- Devuelve una lista con el nombre de los departamentos, gastos y presupuesto de aquellos departamentos donde los gastos son mayores que el presupuesto.
SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos > presupuesto;

-- Devuelve una lista con el nombre de los departamentos, gastos y presupuesto de aquellos departamentos donde los gastos son menores que el presupuesto.
SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos < presupuesto;

-- Devuelve una lista con el nombre de los departamentos, gastos y presupuesto de aquellos departamentos donde los gastos son iguales al presupuesto.
SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos = presupuesto;

-- Lista todos los datos de los empleados cuyo segundo apellido es NULL.
SELECT * FROM empleado WHERE apellido2 IS NULL;

-- Lista todos los datos de los empleados cuyo segundo apellido no es NULL.
SELECT * FROM empleado WHERE apellido2 IS NOT NULL;

-- Lista todos los datos de los empleados cuyo segundo apellido es "López".
SELECT * FROM empleado WHERE apellido2 = 'López';

-- Lista todos los datos de los empleados cuyo segundo apellido es "Díaz" o "Moreno" sin utilizar el operador IN.
SELECT * FROM empleado WHERE apellido2 = 'Díaz' OR apellido2 = 'Moreno';

-- Lista todos los datos de los empleados cuyo segundo apellido es "Díaz" o "Moreno" utilizando el operador IN.
SELECT * FROM empleado WHERE apellido2 IN ('Díaz', 'Moreno');

-- Lista los nombres, apellidos y NIF de los empleados que trabajan en el departamento 3.
SELECT nombre, apellido1, apellido2, nif FROM empleado WHERE codigo_departamento = 3;

-- Lista los nombres, apellidos y NIF de los empleados que trabajan en los departamentos 2, 4 o 5.
SELECT nombre, apellido1, apellido2, nif FROM empleado WHERE codigo_departamento IN (2, 4, 5);
```
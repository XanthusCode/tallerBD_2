# ***Taller Nro 2 Bases de Datos***

#### *Consultas sobre una tabla*

1. Lista el primer apellido de todos los empleados.

   ```sql
   SELECT apellido1 FROM empleado;
   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Salas     |
   | Sáez      |
   +-----------+
   ```

   

2. Lista el primer apellido de los empleados eliminando los apellidos que estén

repetidos.

```sql
SELECT DISTINCT apellido1 FROM empleado;
+-----------+
| apellido1 |
+-----------+
| Rivero    |
| Salas     |
| Rubio     |
| Suárez    |
| Loyola    |
| Santana   |
| Ruiz      |
| Gómez     |
| Flores    |
| Herrera   |
| Sáez      |
+-----------+
```



3. Lista todas las columnas de la tabla empleado .

   ```mysql
   SELECT codigo, nit, nombre, apellido1, apellido2, codigo_departamento FROM empleado;
   +--------+-----------+--------------+-----------+-----------+---------------------+
   | codigo | nif       | nombre       | apellido1 | apellido2 | codigo_departamento |
   +--------+-----------+--------------+-----------+-----------+---------------------+
   |      1 | 32481596F | Aarón        | Rivero    | Gómez     |                   1 |
   |      2 | Y5575632D | Adela        | Salas     | Díaz      |                   2 |
   |      3 | R6970642B | Adolfo       | Rubio     | Flores    |                   3 |
   |      4 | 77705545E | Adrián       | Suárez    | NULL      |                   4 |
   |      5 | 17087203C | Marcos       | Loyola    | Méndez    |                   5 |
   |      6 | 38382980M | María        | Santana   | Moreno    |                   1 |
   |      7 | 80576669X | Pilar        | Ruiz      | NULL      |                   2 |
   |      8 | 71651431Z | Pepe         | Ruiz      | Santana   |                   3 |
   |      9 | 56399183D | Juan         | Gómez     | López     |                   2 |
   |     10 | 46384486H | Diego        | Flores    | Salas     |                   5 |
   |     11 | 67389283A | Marta        | Herrera   | Gil       |                   1 |
   |     12 | 41234836R | Irene        | Salas     | Flores    |                NULL |
   |     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |                NULL |
   +--------+-----------+--------------+-----------+-----------+---------------------+
   ```

   

4. Lista el nombre y los apellidos de todos los empleados.

   ```sql
   SELECT nombre, apellido1, apellido2 FROM empleado;
   +--------------+-----------+-----------+
   | nombre       | apellido1 | apellido2 |
   +--------------+-----------+-----------+
   | Aarón        | Rivero    | Gómez     |
   | Adela        | Salas     | Díaz      |
   | Adolfo       | Rubio     | Flores    |
   | Adrián       | Suárez    | NULL      |
   | Marcos       | Loyola    | Méndez    |
   | María        | Santana   | Moreno    |
   | Pilar        | Ruiz      | NULL      |
   | Pepe         | Ruiz      | Santana   |
   | Juan         | Gómez     | López     |
   | Diego        | Flores    | Salas     |
   | Marta        | Herrera   | Gil       |
   | Irene        | Salas     | Flores    |
   | Juan Antonio | Sáez      | Guerrero  |
   +--------------+-----------+-----------+
   ```

   

5. Lista el identificador de los departamentos de los empleados que aparecen

en la tabla empleado .

```mysql
SELECT codigo_departamento  FROM empleado;
+---------------------+
| codigo_departamento |
+---------------------+
|                   1 |
|                   2 |
|                   3 |
|                   4 |
|                   5 |
|                   1 |
|                   2 |
|                   3 |
|                   2 |
|                   5 |
|                   1 |
|                NULL |
|                NULL |
+---------------------+
```



6. Lista el identificador de los departamentos de los empleados que aparecen

en la tabla empleado , eliminando los identificadores que aparecen repetidos.

```sql
SELECT DISTINCT codigo_departamento  FROM empleado;
+---------------------+
| codigo_departamento |
+---------------------+
|                   1 |
|                   2 |
|                   3 |
|                   4 |
|                   5 |
|                NULL |
+---------------------+
```



7. Lista el nombre y apellidos de los empleados en una única columna.

   ```mysql
   SELECT CONCAT(nombre, ' ', apellido1, ' ', apellido2) AS nombre_completo FROM empleado;
   +-----------------------------+
   | nombre_completo             |
   +-----------------------------+
   | Aarón Rivero Gómez          |
   | Adela Salas Díaz            |
   | Adolfo Rubio Flores         |
   | NULL                        |
   | Marcos Loyola Méndez        |
   | María Santana Moreno        |
   | NULL                        |
   | Pepe Ruiz Santana           |
   | Juan Gómez López            |
   | Diego Flores Salas          |
   | Marta Herrera Gil           |
   | Irene Salas Flores          |
   | Juan Antonio Sáez Guerrero  |
   +-----------------------------+
   ```

   

8. Lista el nombre y apellidos de los empleados en una única columna,

convirtiendo todos los caracteres en mayúscula.

```sql
SELECT UPPER(CONCAT(nombre, ' ', apellido1, ' ', apellido2)) AS nombre_completo FROM empleado;
+-----------------------------+
| nombre_completo             |
+-----------------------------+
| AARÓN RIVERO GÓMEZ          |
| ADELA SALAS DÍAZ            |
| ADOLFO RUBIO FLORES         |
| NULL                        |
| MARCOS LOYOLA MÉNDEZ        |
| MARÍA SANTANA MORENO        |
| NULL                        |
| PEPE RUIZ SANTANA           |
| JUAN GÓMEZ LÓPEZ            |
| DIEGO FLORES SALAS          |
| MARTA HERRERA GIL           |
| IRENE SALAS FLORES          |
| JUAN ANTONIO SÁEZ GUERRERO  |
+-----------------------------+
```



9. Lista el nombre y apellidos de los empleados en una única columna,

convirtiendo todos los caracteres en minúscula.

```sql
SELECT LOWER(CONCAT(nombre, ' ', apellido1, ' ', apellido2)) AS nombre_completo FROM empleado;
+-----------------------------+
| nombre_completo             |
+-----------------------------+
| aarón rivero gómez          |
| adela salas díaz            |
| adolfo rubio flores         |
| NULL                        |
| marcos loyola méndez        |
| maría santana moreno        |
| NULL                        |
| pepe ruiz santana           |
| juan gómez lópez            |
| diego flores salas          |
| marta herrera gil           |
| irene salas flores          |
| juan antonio sáez guerrero  |
+-----------------------------+
```



10. Lista el identificador de los empleados junto al nif, pero el nif deberá

aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la
otra la letra.

```sql
SELECT codigo, CONCAT(SUBSTRING(nif, 1, LEN(nif) - 1), ' ', RIGHT(nif, 1)) AS nif_separado
FROM empleado;
+--------+--------------+
| codigo | nif_separado |
+--------+--------------+
|      1 | 32481596 F   |
|      2 | Y5575632 D   |
|      3 | R6970642 B   |
|      4 | 77705545 E   |
|      5 | 17087203 C   |
|      6 | 38382980 M   |
|      7 | 80576669 X   |
|      8 | 71651431 Z   |
|      9 | 56399183 D   |
|     10 | 46384486 H   |
|     11 | 67389283 A   |
|     12 | 41234836 R   |
|     13 | 82635162 B   |
+--------+--------------+
```



11. Lista el nombre de cada departamento y el valor del presupuesto actual del

que dispone. Para calcular este dato tendrá que restar al valor del
presupuesto inicial (columna presupuesto ) los gastos que se han generado
(columna gastos ). Tenga en cuenta que en algunos casos pueden existir
valores negativos. Utilice un alias apropiado para la nueva columna columna
que está calculando.

```mysql
SELECT nombre , presupuesto - gasto AS presupuesto_Disponible
FROM departamento;
+------------------+------------------------+
| nombre           | presupuesto_Disponible |
+------------------+------------------------+
| Desarrollo       |                 114000 |
| Sistemas         |                 129000 |
| Recursos Humanos |                 255000 |
| Contabilidad     |                 107000 |
| I+D              |                  -5000 |
| Proyectos        |                      0 |
| Publicidad       |                  -1000 |
+------------------+------------------------+
```



12. Lista el nombre de los departamentos y el valor del presupuesto actual

ordenado de forma ascendente.

```mysql
SELECT  nombre, presupuesto - gasto AS presupuesto_actual
FROM departamento
ORDER BY presupuesto_actual ASC;
+------------------+--------------------+
| nombre           | presupuesto_actual |
+------------------+--------------------+
| I+D              |              -5000 |
| Publicidad       |              -1000 |
| Proyectos        |                  0 |
| Contabilidad     |             107000 |
| Desarrollo       |             114000 |
| Sistemas         |             129000 |
| Recursos Humanos |             255000 |
+------------------+--------------------+
```



13. Lista el nombre de todos los departamentos ordenados de forma

ascendente.

```mysql
SELECT nombre
FROM departamento  
ORDER BY nombre ASC;
+---------------------+
| Nombre_Departamento |
+---------------------+
| Contabilidad        |
| Desarrollo          |
| I+D                 |
| Proyectos           |
| Publicidad          |
| Recursos Humanos    |
| Sistemas            |
+---------------------+
```



14. Lista el nombre de todos los departamentos ordenados de forma

descendente.

```mysql
SELECT nombre  
FROM departamento  
ORDER BY nombre DESC;
+------------------+
| nombre           |
+------------------+
| Sistemas         |
| Recursos Humanos |
| Publicidad       |
| Proyectos        |
| I+D              |
| Desarrollo       |
| Contabilidad     |
+------------------+
```



15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma

alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su
nombre.

```mysql
SELECT apellido1, apellido2, nombre
FROM empleado
ORDER BY apellido1, apellido2, nombre;
+-----------+-----------+--------------+
| apellido1 | apellido2 | nombre       |
+-----------+-----------+--------------+
| Flores    | Salas     | Diego        |
| Gómez     | López     | Juan         |
| Herrera   | Gil       | Marta        |
| Loyola    | Méndez    | Marcos       |
| Rivero    | Gómez     | Aarón        |
| Rubio     | Flores    | Adolfo       |
| Ruiz      | NULL      | Pilar        |
| Ruiz      | Santana   | Pepe         |
| Sáez      | Guerrero  | Juan Antonio |
| Salas     | Díaz      | Adela        |
| Salas     | Flores    | Irene        |
| Santana   | Moreno    | María        |
| Suárez    | NULL      | Adrián       |
+-----------+-----------+--------------+
```



16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos

que tienen mayor presupuesto.

```mysql
SELECT nombre, presupuesto
FROM departamento
ORDER BY presupuesto DESC
LIMIT 3;
+------------------+-------------+
| nombre           | presupuesto |
+------------------+-------------+
| I+D              |      375000 |
| Recursos Humanos |      280000 |
| Sistemas         |      150000 |
+------------------+-------------+

```



17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos

que tienen menor presupuesto.

```mysql
SELECT nombre, presupuesto
FROM departamento
ORDER BY presupuesto ASC
LIMIT 3;
+--------------+-------------+
| nombre       | presupuesto |
+--------------+-------------+
| Proyectos    |           0 |
| Publicidad   |           0 |
| Contabilidad |      110000 |
+--------------+-------------+
```



18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que

tienen mayor gasto.

```mysql
SELECT nombre, presupuesto
FROM departamento
ORDER BY presupuesto DESC
LIMIT 2;
+------------------+-------------+
| nombre           | presupuesto |
+------------------+-------------+
| I+D              |      375000 |
| Recursos Humanos |      280000 |
+------------------+-------------+
```



19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que

tienen menor gasto.

```mysql
SELECT nombre, presupuesto
FROM departamento
ORDER BY presupuesto ASC
LIMIT 2;
+------------+-------------+
| nombre     | presupuesto |
+------------+-------------+
| Publicidad |           0 |
| Proyectos  |           0 |
+------------+-------------+
```



20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado . La

tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las
columnas de la tabla empleado .

```mysql
SELECT codigo, nif, nombre, apellido1, apellido2, codigo_departamento
FROM empleado
LIMIT 5 OFFSET 2;
+--------+-----------+---------+-----------+-----------+---------------------+
| codigo | nif       | nombre  | apellido1 | apellido2 | codigo_departamento |
+--------+-----------+---------+-----------+-----------+---------------------+
|      3 | R6970642B | Adolfo  | Rubio     | Flores    |                   3 |
|      4 | 77705545E | Adrián  | Suárez    | NULL      |                   4 |
|      5 | 17087203C | Marcos  | Loyola    | Méndez    |                   5 |
|      6 | 38382980M | María   | Santana   | Moreno    |                   1 |
|      7 | 80576669X | Pilar   | Ruiz      | NULL      |                   2 |
+--------+-----------+---------+-----------+-----------+---------------------+
```



21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de

aquellos que tienen un presupuesto mayor o igual a 150000 euros.

```mysql
SELECT nombre, presupuesto
FROM departamento
WHERE presupuesto  >= 150000;
+------------------+-------------+
| nombre           | presupuesto |
+------------------+-------------+
| Sistemas         |      150000 |
| Recursos Humanos |      280000 |
| I+D              |      375000 |
+------------------+-------------+
```



22. Devuelve una lista con el nombre de los departamentos y el gasto, de

aquellos que tienen menos de 5000 euros de gastos.

```mysql
SELECT nombre, gasto
FROM departamento
WHERE gasto  < 5000;
+--------------+-------+
| nombre       | gasto |
+--------------+-------+
| Contabilidad |  3000 |
| Proyectos    |     0 |
| Publicidad   |  1000 |
+--------------+-------+
```



23. Devuelve una lista con el nombre de los departamentos y el presupuesto, de

aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin
utilizar el operador BETWEEN .

```mysql
SELECT nombre
FROM departamento
WHERE  presupuesto >= 100000 AND presupuesto <= 200000;
+--------------+
| nombre       |
+--------------+
| Desarrollo   |
| Sistemas     |
| Contabilidad |
+--------------+
```



24. Devuelve una lista con el nombre de los departamentos que no tienen un

presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN .

```mysql
SELECT nombre
FROM departamento
WHERE NOT presupuesto >= 100000 AND presupuesto <= 200000;
+------------+
| nombre     |
+------------+
| Proyectos  |
| Publicidad |
+------------+
```



25. Devuelve una lista con el nombre de los departamentos que tienen un

presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN .

```mysql
SELECT nombre
FROM departamento
WHERE presupuesto BETWEEN 100000 AND 200000;
+--------------+
| nombre       |
+--------------+
| Desarrollo   |
| Sistemas     |
| Contabilidad |
+--------------+
```



26. Devuelve una lista con el nombre de los departamentos que no tienen un

presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN .

```mysql
SELECT codigo, nombre, presupuesto, gasto 
FROM departamento
WHERE NOT precio BETWEEN  100000 AND 200000;
+--------+------------------+-------------+--------+
| codigo | nombre           | presupuesto | gasto  |
+--------+------------------+-------------+--------+
|      3 | Recursos Humanos |      280000 |  25000 |
|      5 | I+D              |      375000 | 380000 |
|      6 | Proyectos        |           0 |      0 |
|      7 | Publicidad       |           0 |   1000 |
+--------+------------------+-------------+--------+
```



27. Devuelve una lista con el nombre de los departamentos, gastos y

presupuesto, de aquellos departamentos donde los gastos sean mayores
que el presupuesto del que disponen.

```mysql
SELECT nombre, gasto, presupuesto 
FROM departamento
WHERE gasto > presupuesto;
```



28. Devuelve una lista con el nombre de los departamentos, gastos y

presupuesto, de aquellos departamentos donde los gastos sean menores
que el presupuesto del que disponen.

```mysql
SELECT nombre, gasto, presupuesto 
FROM departamento
WHERE gasto < presupuesto;
+------------+--------+-------------+
| nombre     | gasto  | presupuesto |
+------------+--------+-------------+
| I+D        | 380000 |      375000 |
| Publicidad |   1000 |           0 |
+------------+--------+-------------+
```



29. Devuelve una lista con el nombre de los departamentos, gastos y

presupuesto, de aquellos departamentos donde los gastos sean iguales al
presupuesto del que disponen.

```mysql
SELECT nombre, gasto, presupuesto 
FROM departamento
WHERE gasto = presupuesto;
+-----------+-------+-------------+
| nombre    | gasto | presupuesto |
+-----------+-------+-------------+
| Proyectos |     0 |           0 |
+-----------+-------+-------------+
```



30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL .

    ```mysql
    SELECT codigo, nif, nombre, apellido1, apellido2, codigo_departamento
    FROM empleado
    WHERE apellido2 IS NULL;
    +--------+-----------+---------+-----------+-----------+---------------------+
    | codigo | nif       | nombre  | apellido1 | apellido2 | codigo_departamento |
    +--------+-----------+---------+-----------+-----------+---------------------+
    |      4 | 77705545E | Adrián  | Suárez    | NULL      |                   4 |
    |      7 | 80576669X | Pilar   | Ruiz      | NULL      |                   2 |
    +--------+-----------+---------+-----------+-----------+---------------------+
    ```

    

31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL .

    ```mysql
    SELECT codigo, nif, nombre, apellido1, apellido2, codigo_departamento
    FROM empleado
    WHERE apellido2 IS NOT NULL;
    +--------+-----------+--------------+-----------+-----------+---------------------+
    | codigo | nif       | nombre       | apellido1 | apellido2 | codigo_departamento |
    +--------+-----------+--------------+-----------+-----------+---------------------+
    |      1 | 32481596F | Aarón        | Rivero    | Gómez     |                   1 |
    |      2 | Y5575632D | Adela        | Salas     | Díaz      |                   2 |
    |      3 | R6970642B | Adolfo       | Rubio     | Flores    |                   3 |
    |      5 | 17087203C | Marcos       | Loyola    | Méndez    |                   5 |
    |      6 | 38382980M | María        | Santana   | Moreno    |                   1 |
    |      8 | 71651431Z | Pepe         | Ruiz      | Santana   |                   3 |
    |      9 | 56399183D | Juan         | Gómez     | López     |                   2 |
    |     10 | 46384486H | Diego        | Flores    | Salas     |                   5 |
    |     11 | 67389283A | Marta        | Herrera   | Gil       |                   1 |
    |     12 | 41234836R | Irene        | Salas     | Flores    |                NULL |
    |     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |                NULL |
    +--------+-----------+--------------+-----------+-----------+---------------------+
    ```

    

32. Lista todos los datos de los empleados cuyo segundo apellido sea López .

    ```mysql
    SELECT codigo , nif, nombre, apellido1 , apellido2 , codigo_departamento FROM empleado 
    WHERE apellido2 ='López';
    +--------+-----------+--------+-----------+-----------+---------------------+
    | codigo | nif       | nombre | apellido1 | apellido2 | codigo_departamento |
    +--------+-----------+--------+-----------+-----------+---------------------+
    |      9 | 56399183D | Juan   | Gómez     | López     |                   2 |
    +--------+-----------+--------+-----------+-----------+---------------------+
    ```

    

33. Lista todos los datos de los empleados cuyo segundo apellido

sea Díaz o Moreno . Sin utilizar el operador IN .

```mysql
SELECT codigo , nif, nombre, apellido1 , apellido2 , codigo_departamento FROM empleado 
WHERE apellido2 = 'Díaz' OR apellido2 = 'Moreno';
+--------+-----------+--------+-----------+-----------+---------------------+
| codigo | nif       | nombre | apellido1 | apellido2 | codigo_departamento |
+--------+-----------+--------+-----------+-----------+---------------------+
|      2 | Y5575632D | Adela  | Salas     | Díaz      |                   2 |
|      6 | 38382980M | María  | Santana   | Moreno    |                   1 |
+--------+-----------+--------+-----------+-----------+---------------------+
```



34. Lista todos los datos de los empleados cuyo segundo apellido

sea Díaz o Moreno . Utilizando el operador IN .

```mysql
SELECT codigo , nif, nombre, apellido1 , apellido2 , codigo_departamento FROM empleado 
WHERE apellido2  IN ('Díaz','Moreno');
+--------+-----------+--------+-----------+-----------+---------------------+
| codigo | nif       | nombre | apellido1 | apellido2 | codigo_departamento |
+--------+-----------+--------+-----------+-----------+---------------------+
|      2 | Y5575632D | Adela  | Salas     | Díaz      |                   2 |
|      6 | 38382980M | María  | Santana   | Moreno    |                   1 |
+--------+-----------+--------+-----------+-----------+---------------------+
```



35. Lista los nombres, apellidos y nif de los empleados que trabajan en el

departamento 3 .

```mysql
SELECT codigo , nif, nombre, apellido1 , apellido2 , codigo_departamento FROM empleado 
WHERE codigo_departamento = 3;
+--------+-----------+--------+-----------+-----------+---------------------+
| codigo | nif       | nombre | apellido1 | apellido2 | codigo_departamento |
+--------+-----------+--------+-----------+-----------+---------------------+
|      3 | R6970642B | Adolfo | Rubio     | Flores    |                   3 |
|      8 | 71651431Z | Pepe   | Ruiz      | Santana   |                   3 |
+--------+-----------+--------+-----------+-----------+---------------------+
```



36. Lista los nombres, apellidos y nif de los empleados que trabajan en los

departamentos 2 , 4 o 5 .

```mysql
SELECT codigo , nif, nombre, apellido1 , apellido2 , codigo_departamento FROM empleado 
WHERE codigo_departamento = 2 OR codigo_departamento = 4 OR codigo_departamento = 5;
+--------+-----------+---------+-----------+-----------+---------------------+
| codigo | nif       | nombre  | apellido1 | apellido2 | codigo_departamento |
+--------+-----------+---------+-----------+-----------+---------------------+
|      2 | Y5575632D | Adela   | Salas     | Díaz      |                   2 |
|      4 | 77705545E | Adrián  | Suárez    | NULL      |                   4 |
|      5 | 17087203C | Marcos  | Loyola    | Méndez    |                   5 |
|      7 | 80576669X | Pilar   | Ruiz      | NULL      |                   2 |
|      9 | 56399183D | Juan    | Gómez     | López     |                   2 |
|     10 | 46384486H | Diego   | Flores    | Salas     |                   5 |
+--------+-----------+---------+-----------+-----------+---------------------+
```





#### *Consultas multitabla (Composición interna)*

##### *Resuelva todas las consultas utilizando la sintaxis de SQL1 y SQL2 .*

1. Devuelve un listado con los empleados y los datos de los departamentos

donde trabaja cada uno.

```mysql
SELECT e.codigo, e.nombre, e.apellido1, e.apellido2, 
       d.codigo AS codigo_departamento, d.nombre AS nombre_departamento, 
       d.presupuesto, d.gasto
FROM empleado AS e
JOIN departamento AS d ON e.codigo_departamento = d.codigo;
+--------+---------+-----------+-----------+---------------------+---------------------+-------------+--------+
| codigo | nombre  | apellido1 | apellido2 | codigo_departamento | nombre_departamento | presupuesto | gasto  |
+--------+---------+-----------+-----------+---------------------+---------------------+-------------+--------+
|      1 | Aarón   | Rivero    | Gómez     |                   1 | Desarrollo          |      120000 |   6000 |
|      2 | Adela   | Salas     | Díaz      |                   2 | Sistemas            |      150000 |  21000 |
|      3 | Adolfo  | Rubio     | Flores    |                   3 | Recursos Humanos    |      280000 |  25000 |
|      4 | Adrián  | Suárez    | NULL      |                   4 | Contabilidad        |      110000 |   3000 |
|      5 | Marcos  | Loyola    | Méndez    |                   5 | I+D                 |      375000 | 380000 |
|      6 | María   | Santana   | Moreno    |                   1 | Desarrollo          |      120000 |   6000 |
|      7 | Pilar   | Ruiz      | NULL      |                   2 | Sistemas            |      150000 |  21000 |
|      8 | Pepe    | Ruiz      | Santana   |                   3 | Recursos Humanos    |      280000 |  25000 |
|      9 | Juan    | Gómez     | López     |                   2 | Sistemas            |      150000 |  21000 |
|     10 | Diego   | Flores    | Salas     |                   5 | I+D                 |      375000 | 380000 |
|     11 | Marta   | Herrera   | Gil       |                   1 | Desarrollo          |      120000 |   6000 |
+--------+---------+-----------+-----------+---------------------+---------------------+-------------+--------+
```



2. Devuelve un listado con los empleados y los datos de los departamentos

donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre
del departamento (en orden alfabético) y en segundo lugar por los apellidos
y el nombre de los empleados.

```mysql
SELECT  e.nombre, e.apellido1, e.apellido2, d.codigo , d.nombre 
FROM empleado AS e
JOIN departamento AS d ON e.codigo_departamento = d.codigo
ORDER BY d.nombre ASC;
+---------+-----------+-----------+--------+------------------+
| nombre  | apellido1 | apellido2 | codigo | nombre           |
+---------+-----------+-----------+--------+------------------+
| Adrián  | Suárez    | NULL      |      4 | Contabilidad     |
| Aarón   | Rivero    | Gómez     |      1 | Desarrollo       |
| María   | Santana   | Moreno    |      1 | Desarrollo       |
| Marta   | Herrera   | Gil       |      1 | Desarrollo       |
| Marcos  | Loyola    | Méndez    |      5 | I+D              |
| Diego   | Flores    | Salas     |      5 | I+D              |
| Adolfo  | Rubio     | Flores    |      3 | Recursos Humanos |
| Pepe    | Ruiz      | Santana   |      3 | Recursos Humanos |
| Adela   | Salas     | Díaz      |      2 | Sistemas         |
| Pilar   | Ruiz      | NULL      |      2 | Sistemas         |
| Juan    | Gómez     | López     |      2 | Sistemas         |
+---------+-----------+-----------+--------+------------------+
```



3. Devuelve un listado con el identificador y el nombre del departamento,

solamente de aquellos departamentos que tienen empleados.

```mysql
SELECT e.codigo , e.nombre, d.codigo, d.nombre 
FROM empleado AS e
JOIN departamento AS d ON e.codigo_departamento = d.codigo;
+--------+---------+--------+------------------+
| codigo | nombre  | codigo | nombre           |
+--------+---------+--------+------------------+
|      1 | Aarón   |      1 | Desarrollo       |
|      2 | Adela   |      2 | Sistemas         |
|      3 | Adolfo  |      3 | Recursos Humanos |
|      4 | Adrián  |      4 | Contabilidad     |
|      5 | Marcos  |      5 | I+D              |
|      6 | María   |      1 | Desarrollo       |
|      7 | Pilar   |      2 | Sistemas         |
|      8 | Pepe    |      3 | Recursos Humanos |
|      9 | Juan    |      2 | Sistemas         |
|     10 | Diego   |      5 | I+D              |
|     11 | Marta   |      1 | Desarrollo       |
+--------+---------+--------+------------------+
```



4. Devuelve un listado con el identificador, el nombre del departamento y el

valor del presupuesto actual del que dispone, solamente de aquellos
departamentos que tienen empleados. El valor del presupuesto actual lo
puede calcular restando al valor del presupuesto inicial
(columna presupuesto ) el valor de los gastos que ha generado
(columna gastos ).

```mysql
SELECT 	d.codigo, d.nombre, (d.presupuesto - d.gasto) AS presupuesto_actualmente
FROM departamento AS d
INNER JOIN empleado AS e ON d.codigo = e.codigo
GROUP BY d.codigo, d.nombre, d.presupuesto, d.gasto;
+--------+------------------+-------------------------+
| codigo | nombre           | presupuesto_actualmente |
+--------+------------------+-------------------------+
|      1 | Desarrollo       |                  114000 |
|      2 | Sistemas         |                  129000 |
|      3 | Recursos Humanos |                  255000 |
|      4 | Contabilidad     |                  107000 |
|      5 | I+D              |                   -5000 |
|      6 | Proyectos        |                       0 |
|      7 | Publicidad       |                   -1000 |
+--------+------------------+-------------------------+
```



5. Devuelve el nombre del departamento donde trabaja el empleado que tiene

el nif 38382980M .

```mysql
SELECT d.nombre 
FROM empleado e
INNER JOIN departamento AS d ON e.codigo_departamento = d.codigo
WHERE e.nif = '38382980M';
+------------+
| nombre     |
+------------+
| Desarrollo |
+------------+
```



6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz

Santana.

```mysql
SELECT  d.nombre
FROM  empleado AS e
INNER JOIN  departamento AS d ON e.codigo_departamento = d.codigo
WHERE e.nombre = 'Pepe' AND e.apellido1 = 'Ruiz' AND e.apellido2 = 'Santana';
+------------------+
| nombre           |
+------------------+
| Recursos Humanos |
+------------------+
```



7. Devuelve un listado con los datos de los empleados que trabajan en el

departamento de I+D . Ordena el resultado alfabéticamente.

```mysql
SELECT e.codigo ,e.nif, e.nombre , e.apellido1 , e.apellido2 
FROM empleado  AS e
INNER JOIN departamento d ON e.codigo_departamento = d.codigo
WHERE d.nombre = 'I+D'
ORDER BY e.apellido1, e.apellido2, e.nombre;
+--------+-----------+--------+-----------+-----------+
| codigo | nif       | nombre | apellido1 | apellido2 |
+--------+-----------+--------+-----------+-----------+
|     10 | 46384486H | Diego  | Flores    | Salas     |
|      5 | 17087203C | Marcos | Loyola    | Méndez    |
+--------+-----------+--------+-----------+-----------+
```



8. Devuelve un listado con los datos de los empleados que trabajan en el

departamento de Sistemas , Contabilidad o I+D . Ordena el resultado
alfabéticamente.

```sql
SELECT e.codigo, e.nif, e.nombre, e.apellido1, e.apellido2 
FROM empleado AS e
INNER JOIN departamento AS d ON e.codigo_departamento = d.codigo
WHERE d.nombre IN ('Sistemas', 'Contabilidad', 'I+D')
ORDER BY e.apellido1, e.apellido2, e.nombre;
+--------+-----------+---------+-----------+-----------+
| codigo | nif       | nombre  | apellido1 | apellido2 |
+--------+-----------+---------+-----------+-----------+
|     10 | 46384486H | Diego   | Flores    | Salas     |
|      9 | 56399183D | Juan    | Gómez     | López     |
|      5 | 17087203C | Marcos  | Loyola    | Méndez    |
|      7 | 80576669X | Pilar   | Ruiz      | NULL      |
|      2 | Y5575632D | Adela   | Salas     | Díaz      |
|      4 | 77705545E | Adrián  | Suárez    | NULL      |
+--------+-----------+---------+-----------+-----------+
```



9. Devuelve una lista con el nombre de los empleados que tienen los

departamentos que no tienen un presupuesto entre 100000 y 200000 euros.

```sql
SELECT e.nombre, e.apellido1, e.apellido2
FROM empleado AS e
INNER JOIN departamento AS d ON e.codigo_departamento = d.codigo
WHERE d.presupuesto NOT BETWEEN 100000 AND 200000
ORDER BY e.apellido1, e.apellido2, e.nombre;
+--------+-----------+-----------+
| nombre | apellido1 | apellido2 |
+--------+-----------+-----------+
| Diego  | Flores    | Salas     |
| Marcos | Loyola    | Méndez    |
| Adolfo | Rubio     | Flores    |
| Pepe   | Ruiz      | Santana   |
+--------+-----------+-----------+
```



10. Devuelve un listado con el nombre de los departamentos donde existe

algún empleado cuyo segundo apellido sea NULL . Tenga en cuenta que no
debe mostrar nombres de departamentos que estén repetidos.

```sql
SELECT DISTINCT d.nombre 
FROM empleado AS e
INNER JOIN departamento AS d ON e.codigo_departamento = d.codigo
WHERE e.apellido2 IS NULL;
+--------------+
| nombre       |
+--------------+
| Contabilidad |
| Sistemas     |
+--------------+
```



#### *Consultas multitabla (Composición externa)*

***Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN .***

1. Devuelve un listado con todos los empleados junto con los datos de los

departamentos donde trabajan. Este listado también debe incluir los
empleados que no tienen ningún departamento asociado.

```sql
SELECT e.codigo, e.nif, e.nombre, e.apellido1, e.apellido2, d.codigo, d.nombre, d.presupuesto, d.gasto
FROM empleado AS e
LEFT JOIN departamento  AS d ON e.codigo_departamento = d.codigo;
+--------+-----------+--------------+-----------+-----------+--------+------------------+-------------+--------+
| codigo | nif       | nombre       | apellido1 | apellido2 | codigo | nombre           | presupuesto | gasto  |
+--------+-----------+--------------+-----------+-----------+--------+------------------+-------------+--------+
|      1 | 32481596F | Aarón        | Rivero    | Gómez     |      1 | Desarrollo       |      120000 |   6000 |
|      2 | Y5575632D | Adela        | Salas     | Díaz      |      2 | Sistemas         |      150000 |  21000 |
|      3 | R6970642B | Adolfo       | Rubio     | Flores    |      3 | Recursos Humanos |      280000 |  25000 |
|      4 | 77705545E | Adrián       | Suárez    | NULL      |      4 | Contabilidad     |      110000 |   3000 |
|      5 | 17087203C | Marcos       | Loyola    | Méndez    |      5 | I+D              |      375000 | 380000 |
|      6 | 38382980M | María        | Santana   | Moreno    |      1 | Desarrollo       |      120000 |   6000 |
|      7 | 80576669X | Pilar        | Ruiz      | NULL      |      2 | Sistemas         |      150000 |  21000 |
|      8 | 71651431Z | Pepe         | Ruiz      | Santana   |      3 | Recursos Humanos |      280000 |  25000 |
|      9 | 56399183D | Juan         | Gómez     | López     |      2 | Sistemas         |      150000 |  21000 |
|     10 | 46384486H | Diego        | Flores    | Salas     |      5 | I+D              |      375000 | 380000 |
|     11 | 67389283A | Marta        | Herrera   | Gil       |      1 | Desarrollo       |      120000 |   6000 |
|     12 | 41234836R | Irene        | Salas     | Flores    |   NULL | NULL             |        NULL |   NULL |
|     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |   NULL | NULL             |        NULL |   NULL |
+--------+-----------+--------------+-----------+-----------+--------+------------------+-------------+--------+
```



2. Devuelve un listado donde sólo aparezcan aquellos empleados que no

tienen ningún departamento asociado.

```sql
SELECT e.codigo, e.nif, e.nombre, e.apellido1, e.apellido2
FROM empleado AS e
LEFT JOIN departamento AS d ON e.codigo_departamento = d.codigo
WHERE d.codigo IS NULL;
+--------+-----------+--------------+-----------+-----------+
| codigo | nif       | nombre       | apellido1 | apellido2 |
+--------+-----------+--------------+-----------+-----------+
|     12 | 41234836R | Irene        | Salas     | Flores    |
|     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |
+--------+-----------+--------------+-----------+-----------+
```



3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no

tienen ningún empleado asociado.

```sql
SELECT d.codigo, d.nombre, d.presupuesto, d.gasto
FROM departamento AS d
LEFT JOIN empleado AS e ON d.codigo = e.codigo_departamento
WHERE e.codigo_departamento IS NULL;
+--------+------------+-------------+-------+
| codigo | nombre     | presupuesto | gasto |
+--------+------------+-------------+-------+
|      6 | Proyectos  |           0 |     0 |
|      7 | Publicidad |           0 |  1000 |
+--------+------------+-------------+-------+
```



4. Devuelve un listado con todos los empleados junto con los datos de los

departamentos donde trabajan. El listado debe incluir los empleados que no
tienen ningún departamento asociado y los departamentos que no tienen
ningún empleado asociado. Ordene el listado alfabéticamente por el
nombre del departamento.

```sql
SELECT e.nombre,d.nombre 
FROM empleado AS e
LEFT JOIN departamento AS d ON e.codigo_departamento = d.codigo
UNION
SELECT e.nombre,d.nombre AS departamento
FROM empleado AS e
RIGHT JOIN departamento AS d ON e.codigo_departamento = d.codigo 
WHERE e.codigo_departamento IS NULL;
+--------------+------------------+
| nombre       | Departamento     |
+--------------+------------------+
| Aarón        | Desarrollo       |
| Adela        | Sistemas         |
| Adolfo       | Recursos Humanos |
| Adrián       | Contabilidad     |
| Marcos       | I+D              |
| María        | Desarrollo       |
| Pilar        | Sistemas         |
| Pepe         | Recursos Humanos |
| Juan         | Sistemas         |
| Diego        | I+D              |
| Marta        | Desarrollo       |
| Irene        | NULL             |
| Juan Antonio | NULL             |
| NULL         | Proyectos        |
| NULL         | Publicidad       |
+--------------+------------------+
```



5. Devuelve un listado con los empleados que no tienen ningún departamento

asociado y los departamentos que no tienen ningún empleado asociado.
Ordene el listado alfabéticamente por el nombre del departamento.

```sql
SELECT e.nombre,d.nombre AS departamento
FROM empleado AS e
LEFT JOIN departamento AS d ON e.codigo_departamento = d.codigo
UNION
SELECT e.nombre,d.nombre AS departamento
FROM empleado AS e
RIGHT JOIN departamento AS d ON e.codigo_departamento = d.codigo 
WHERE e.codigo_departamento IS NULL
ORDER BY departamento ASC;
+--------------+------------------+
| nombre       | departamento     |
+--------------+------------------+
| Irene        | NULL             |
| Juan Antonio | NULL             |
| Adrián       | Contabilidad     |
| Aarón        | Desarrollo       |
| María        | Desarrollo       |
| Marta        | Desarrollo       |
| Marcos       | I+D              |
| Diego        | I+D              |
| NULL         | Proyectos        |
| NULL         | Publicidad       |
| Adolfo       | Recursos Humanos |
| Pepe         | Recursos Humanos |
| Adela        | Sistemas         |
| Pilar        | Sistemas         |
| Juan         | Sistemas         |
+--------------+------------------+
```



#### *Consultas resumen*

1. Calcula la suma del presupuesto de todos los departamentos.

   ```sql
   SELECT SUM(presupuesto) AS Presupuesto_Total
   FROM departamento;
   +-------------------+
   | Presupuesto_Total |
   +-------------------+
   |           1035000 |
   +-------------------+
   ```

   

2. Calcula la media del presupuesto de todos los departamentos.

   ```sql
   SELECT AVG(presupuesto) AS media
   FROM departamento;
   +--------------------+
   | media              |
   +--------------------+
   | 147857.14285714287 |
   +--------------------+
   ```
   
   
   
3. Calcula el valor mínimo del presupuesto de todos los departamentos.

   ```sql
   SELECT MIN(presupuesto) AS Presupuesto_Minimo
   FROM departamento;
   +--------------------+
   | Presupuesto_Minimo |
   +--------------------+
   |                  0 |
   +--------------------+
   ```

   

4. Calcula el nombre del departamento y el presupuesto que tiene asignado,

del departamento con menor presupuesto.

```sql
SELECT nombre, presupuesto
FROM departamento
WHERE presupuesto = (SELECT MIN(presupuesto) FROM departamento);
+------------+-------------+
| nombre     | presupuesto |
+------------+-------------+
| Proyectos  |           0 |
| Publicidad |           0 |
+------------+-------------+
```



5. Calcula el valor máximo del presupuesto de todos los departamentos.

   ```sql
   SELECT MAX(presupuesto) AS Presupuesto_Maximo
   FROM departamento;
   +--------------------+
   | Presupuesto_Maximo |
   +--------------------+
   |             375000 |
   +--------------------+
   ```

   

6. Calcula el nombre del departamento y el presupuesto que tiene asignado,

del departamento con mayor presupuesto.

```sql
SELECT nombre, presupuesto
FROM departamento
WHERE presupuesto = (SELECT MAX(presupuesto) FROM departamento);
+--------+-------------+
| nombre | presupuesto |
+--------+-------------+
| I+D    |      375000 |
+--------+-------------+
```



7. Calcula el número total de empleados que hay en la tabla empleado .

   ```sql
   SELECT COUNT(codigo) AS total_empleados
   FROM empleado;
   +-----------------+
   | total_empleados |
   +-----------------+
   |              13 |
   +-----------------+
   ```

   

8. Calcula el número de empleados que no tienen NULL en su segundo

apellido.

```sql
SELECT COUNT(codigo) AS empleados
FROM empleado
WHERE apellido2 IS NOT NULL;
+--------------------------------+
| empleados                      |
+--------------------------------+
|                             11 |
+--------------------------------+
```



9. Calcula el número de empleados que hay en cada departamento. Tienes que

devolver dos columnas, una con el nombre del departamento y otra con el
número de empleados que tiene asignados.

```sql
SELECT d.nombre AS Departamento, COUNT(e.codigo) AS num_Empleados
FROM departamento AS d
LEFT JOIN empleado AS e ON d.codigo = e.codigo_departamento
GROUP BY d.nombre;
+------------------+-----------+
| Departamento     | Empleados |
+------------------+-----------+
| Desarrollo       |         3 |
| Sistemas         |         3 |
| Recursos Humanos |         2 |
| Contabilidad     |         1 |
| I+D              |         2 |
| Proyectos        |         0 |
| Publicidad       |         0 |
+------------------+-----------+
```



10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El

resultado debe tener dos columnas, una con el nombre del departamento y
otra con el número de empleados que tiene asignados.

```sql
SELECT d.nombre, COUNT(e.codigo) AS num_empleados
FROM empleado AS e
LEFT JOIN departamento AS d ON e.codigo_departamento = d.codigo
GROUP BY d.nombre
HAVING COUNT(e.codigo) > 2;
+------------+---------------+
| nombre     | num_empleados |
+------------+---------------+
| Desarrollo |             3 |
| Sistemas   |             3 |
+------------+---------------+
```



11. Calcula el número de empleados que trabajan en cada uno de los

departamentos. El resultado de esta consulta también tiene que incluir
aquellos departamentos que no tienen ningún empleado asociado.

```sql
SELECT d.nombre, COUNT(e.codigo) AS num_empleados
FROM departamento AS d
LEFT JOIN empleado AS e ON d.codigo = e.codigo_departamento
GROUP BY d.nombre;
+------------------+---------------+
| nombre           | num_empleados |
+------------------+---------------+
| Desarrollo       |             3 |
| Sistemas         |             3 |
| Recursos Humanos |             2 |
| Contabilidad     |             1 |
| I+D              |             2 |
| Proyectos        |             0 |
| Publicidad       |             0 |
+------------------+---------------+
```



12. Calcula el número de empleados que trabajan en cada unos de los

departamentos que tienen un presupuesto mayor a  200000 euros.

```sql
SELECT d.nombre, COUNT(e.codigo) AS num_empleados
FROM departamento AS d
LEFT JOIN empleado AS e ON d.codigo = e.codigo_departamento
WHERE d.presupuesto > 200000
GROUP BY d.nombre;
+------------------+---------------+
| nombre           | num_empleados |
+------------------+---------------+
| Recursos Humanos |             2 |
| I+D              |             2 |
+------------------+---------------+
```



#### *Subconsultas*

***Con operadores básicos de comparación***

1. Devuelve un listado con todos los empleados que tiene el departamento
    de Sistemas. (Sin utilizar INNER JOIN).

  ```sql
  SELECT e.codigo, e.nif, e.nombre, e.apellido1, e.apellido2
      -> FROM empleado  AS e
      -> WHERE e.codigo_departamento = (SELECT d.codigo FROM departamento  AS d WHERE d.nombre = 'Sistemas');
  +--------+-----------+--------+-----------+-----------+
  | codigo | nif       | nombre | apellido1 | apellido2 |
  +--------+-----------+--------+-----------+-----------+
  |      2 | Y5575632D | Adela  | Salas     | Díaz      |
  |      7 | 80576669X | Pilar  | Ruiz      | NULL      |
  |      9 | 56399183D | Juan   | Gómez     | López     |
  +--------+-----------+--------+-----------+-----------+
  ```

  

2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
     que tiene asignada.

     ```sql
     SELECT nombre, presupuesto
     FROM departamento
     WHERE presupuesto = (SELECT MAX(presupuesto) FROM departamento);
     +--------+-------------+
     | nombre | presupuesto |
     +--------+-------------+
     | I+D    |      375000 |
     +--------+-------------+
     ```

     

3. Devuelve el nombre del departamento con menor presupuesto y la cantidad
     que tiene asignada.Subconsultas con ALL y ANY

     ```sql
     SELECT nombre, presupuesto
     FROM departamento
     WHERE presupuesto <= ALL (SELECT presupuesto FROM departamento);
     +------------+-------------+
     | nombre     | presupuesto |
     +------------+-------------+
     | Proyectos  |           0 |
     | Publicidad |           0 |
     +------------+-------------+
     ```

     

4. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
     que tiene asignada. Sin hacer uso de MAX, ORDER BY ni LIMIT.

     ```sql
     SELECT nombre, presupuesto, gasto
     FROM departamento d1
     WHERE NOT EXISTS (  SELECT 1
     					FROM departamento AS d2
     					WHERE d2.presupuesto > d1.presupuesto
     					OR (d2.presupuesto = d1.presupuesto AND d2.gasto > d1.gasto)
     				);
     +--------+-------------+--------+
     | nombre | presupuesto | gasto  |
     +--------+-------------+--------+
     | I+D    |      375000 | 380000 |
     +--------+-------------+--------+
     ```

     

5. Devuelve el nombre del departamento con menor presupuesto y la cantidad
     que tiene asignada. Sin hacer uso de MIN, ORDER BY ni LIMIT.

     ```sql
     SELECT nombre, presupuesto, gasto
     FROM departamento AS d1
     WHERE NOT EXISTS (  SELECT 1
     					FROM departamento AS d2
     					WHERE d2.presupuesto < d1.presupuesto OR (d2.presupuesto = d1.presupuesto AND d2.gasto < d1.gasto));
     +-----------+-------------+-------+
     | nombre    | presupuesto | gasto |
     +-----------+-------------+-------+
     | Proyectos |           0 |     0 |
     +-----------+-------------+-------+
     ```

     

6. Devuelve los nombres de los departamentos que tienen empleados
     asociados. (Utilizando ALL o ANY).

     ```sql
     SELECT nombre
     FROM departamento
     WHERE codigo = ANY (SELECT codigo_departamento FROM empleado);
     +------------------+
     | nombre           |
     +------------------+
     | Desarrollo       |
     | Sistemas         |
     | Recursos Humanos |
     | Contabilidad     |
     | I+D              |
     +------------------+
     ```

     

7. Devuelve los nombres de los departamentos que no tienen empleados
     asociados. (Utilizando ALL o ANY). Subconsultas con IN y NOT IN

     ```sql
     SELECT nombre
     FROM departamento AS d
     WHERE 0 = ALL (
             SELECT COUNT(e.codigo)
             FROM empleado e
             WHERE e.codigo_departamento = d.codigo);
     +------------+
     | nombre     |
     +------------+
     | Proyectos  |
     | Publicidad |
     +------------+
     ```

     

8. Devuelve los nombres de los departamentos que tienen empleados
     asociados. (Utilizando IN o NOT IN).

     ```sql
     SELECT nombre
     FROM departamento
     WHERE codigo IN (SELECT codigo_departamento FROM empleado);
     +------------------+
     | nombre           |
     +------------------+
     | Desarrollo       |
     | Sistemas         |
     | Recursos Humanos |
     | Contabilidad     |
     | I+D              |
     +------------------+
     ```

     

9. Devuelve los nombres de los departamentos que no tienen empleados
     asociados. (Utilizando IN o NOT IN). Subconsultas con EXISTS y NOT EXISTS

     ```sql
     SELECT nombre
     FROM departamento d
     WHERE NOT EXISTS (
         SELECT 1 
         FROM empleado e
         WHERE e.codigo_departamento = d.codigo
     );
     +------------+
     | nombre     |
     +------------+
     | Proyectos  |
     | Publicidad |
     +------------+
     ```

     

10. Devuelve los nombres de los departamentos que tienen  no empleados
     asociados. (Utilizando EXISTS o NOT EXISTS).

     ```sql
     SELECT nombre
     FROM departamento d
     WHERE NOT EXISTS (SELECT 1 FROM empleado WHERE codigo_departamento = d.codigo);
     +------------+
     | nombre     |
     +------------+
     | Proyectos  |
     | Publicidad |
     +------------+
     ```

     

11. Devuelve los nombres de los departamentos que tienen empleados
      asociados. (Utilizando EXISTS o NOT EXISTS).

      ```sql
      SELECT nombre
      FROM departamento d
      WHERE EXISTS (SELECT 1 FROM empleado WHERE codigo_departamento = d.codigo);
      +------------------+
      | nombre           |
      +------------------+
      | Desarrollo       |
      | Sistemas         |
      | Recursos Humanos |
      | Contabilidad     |
      | I+D              |
      +------------------+
      ```

      
   
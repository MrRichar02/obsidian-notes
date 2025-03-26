### Constraints

#### WHERE

Con la palabra reservada WHERE podemos agregar una condición para filtrar la información de nuestro  SELECT, para la condición del WHERE podemos usar cosas de igual, diferente, mayor, menor, 
mayor o igual y menor o igual.  

#### BETWEEN ... AND ...
Podemos filtrar entre un rango de numeros usando las palabras reservadas BETWEEN y AND, entre ellas ponemos el primer numero y al final el ultimo

#### IN

Podemos usar la palabra reservada IN para filtrar entre una lista de datos

#### NOT

Podemos usar la palabra reservada NOT para negar las condiciones

#### Strings equal

Para comparar strings de una manera case sensitive podemos usar el = 

#### Strings LIKE

para comparar Strings de una manera no case sensitive podemos usar la palabra reservada LIKE

#### El uso de % y _

Cuando comparamos un string podemos usar los caracteres especiales % y _ para tener un comportamiento especial, si usamos el % se intentara buscar si la palabra coincide o esta en algún patrón 
después del uso de la palabra % o si esta en si la palabra  pero la coincidencia solo se buscara desde  luego de que este el carácter %, si usamos el carácter _ solo se buscara que coincida un carácter 
después del uso del carácter _ y no se aceptara que no hayan mas caracteres después para que coincida

#### AND y OR

podemos usar AND y OR para sumar condiciones 

### Sorting

#### DISTINCT

Si colocamos la palabra reservada DISTINCT justo después del SELECT nuestra búsqueda eliminara todas los elementos repetidos para asegurar que solo hay elementos únicos 

#### ORDER BY

Podemos ordenar una columna usando las palabras reservadas ORDER BY, luego de las palabras colocamos el nombre de la columna que deseamos ordenar, y luego del nombre de la columna podemos
colocar dos opciones `ASC` o `DESC` dependiendo de si lo queremos ordenar de manera ascendente o descendente, el valor por default si no ponemos nada es `ASC`

#### LIMIT

Algo que podemos adicionar a un ORDER BY es un LIMIT que como dice el nombre establecerá el limite de elementos que se mostraran 

#### OFFSET

Otra opción que podemos adicionar all ORDER BY es OFFSET que establece desde que posición se van a empezar a extraer elementos 

### JOINS

Podemos combinar en una respuesta de un SELECT dos tablas, para hacerlo hacemos uso de un JOIN (existen varios tipos de JOIN el tipo va antes de la palabra JOIN) luego colocamos el nombre de la 
otra tabla y después usando el ON creamos una relación entre dos columnas una de cada tabla

#### INNER JOIN

El INNER JOIN solo traerá los elementos donde ambos elementos de la relación existan

#### LEFT JOIN

El LEFT JOIN solo traerá los elementos que existan en la columna de la tabla de la izquierda osea la primera tabla que especificamos

#### RIGHT JOIN

El RIGHT JOIN solo traerá los elementos que existan en la columna de la tabla de la derecha osea la segunda tabla que especificamos 

#### FULL JOIN

El FULL JOIN traerá los elementos que existan tanto en la columna de la derecha como en la de la izquierda sin importar si no lo hacen en la otra 

### NULLS

En SQL el valor NULL significa una ausencia de datos, aunque puede ser útil en ciertas ocasiones la buena practica es evitar el uso de los NULLS, podemos verificar si un elemento es NULL usando lo 
siguiente `IS NULL` y podemos verificar si no es NULL usando lo siguiente `IS NOT NULL`

### Queries with expressions

Podemos agregar expresiones matemáticas para hacer una operación con elementos de columnas y  darle un nombre de columna diferente, esto lo debemos hacer justo después del SELECT, 
para asignar el nombre a la columna que representara el resultado de la operación usamos la palabra reservada `AS` 

También podemos usar expresiones matemáticas para las condiciones del WHERE

### Queries with aggregates

Ademas de las expresiones matemáticas podemos utilizar funciones aggregate que nos permiten obtener información de columnas y usando `AS` podemos crear otra columna con el resultado

#### Count

Esta función recibe un grupo de columnas o solo una columna y nos regresa el numero de filas que no son NULL del grupo o la columna 


#### MIN

Esta función recibe una columna o grupo de ellas, y nos regresa el menor numero de todas las filas de la columna 

#### MAX 

Esta función recibe una columna o grupo de ellas, y nos regresa el mayor numero de todas las filas de la columna 

#### AVG

Esta función recibe una columna o grupo de ellas, y nos regresa el promedio de todos los valores de las filas 

#### SUM

Esta función recibe una columna o grupo de ellas, y nos regresa la suma de todos los valores de las filas 

#### GROUP BY

Podemos usar las palabras reservadas GROUP BY para crear subgroups de filas entre las filas que tenemos usando el valor de otra columna, por ejemplo pasamos a la función de aggregate la columna
salario y luego al GROUP BY le pasamos la columna país, entonces las filas con el mismo país aportaran entre si para el resultado, y el resultado se dará por países 

#### HAVING

La expresión GROUP BY siempre es ejecutada luego de un WHERE por lo que para condicionar las filas seleccionadas para los subgroups usamos la expresión HAVING, el funcionamiento del HAVING, 
es el mismo que un WHERE


### Order of operations 

1. Lo primero que se ejecuta son el FROM y los JOINS para tener toda la data con la que vamos a trabajar 
2. luego se aplica el primer WHERE para ir descartando filas que no cumplan la condición del WHERE
3. luego se ejecuta el GROUP BY para crear los grupos de filas
4. luego se aplica el HAVING a los grupos de filas
5. después se procesan las expresiones que creamos en el SELECT con los nombres que le dimos al resultado de las operaciones
6. luego se ejecuta el ORDER BY dependiendo de si es ascendente o descendente 
7. por ultimo se ejecutan el LIMIT y OFFSET para terminar de descartar filas

NOTA(no es necesario que todos los pasos estén incluidos )


### Inserting values

Para agregar valores a una tabla usamos la expresión `INSERT INTO` luego colocamos el nombre de la tabla a la cual vamos a agregar valores,  luego tenemos dos opciones, podemos definir entre 
paréntesis  las columnas a las cuales vamos a insertar algún valor, si a la cuales no vamos a hacerlo tienen un valor por defecto luego usamos la expresión `VALUES` y entre paréntesis ponemos los
valores a insertar, también podemos poner directamente la expresión `VALUES` pero en este caso deberemos especificar los valores para todas las columnas. Después de la expresión `VALUES` podemos
hacer varias inserciones separando las usando comas 

### UPDATE data

Para actualizar los valores de filas ya insertadas, podemos usar la palabra reservada `UPDATE` luego colocamos el  nombre de la tabla, luego ponemos la palabra reservada SET, después ponemos 
uno a uno los valores nuevos para cada columna a modificar separados por comas y usando el nombre de las columnas, por ultimo debemos usar un WHERE ya que si no lo hacemos todas las filas 
serán  actualizadas

### DELETE rows

Si deseamos eliminar filas podemos usar las palabras reservadas `DELETE FROM` luego el nombre de la tabla en la cual queremos actuar y después un `WHERE` con la condición que nos filtra solo la fila 
que  queremos eliminar, si no ponemos el `WHERE` todas las filas de la tabla serán eliminada 

### Creating a table

Para crear una tabla en nuestra base de datos usamos las palabras reservadas `CREATE TABLE` luego colocamos el nombre de la tabla y después entre paréntesis y separados por comas definimos
las columnas de la tabla, lo primero que ponemos es el nombre de la tabla luego el tipo, luego le podemos poner una condición especial a la tabla si deseamos, finalmente podemos usar la palabra 
reservada `DEFAULT` para asignar un valor por defecto a la columna 

Ademas podemos adicionar una condición para solo crear la tabla si esta mo existe para hacerlo entre `CREATE TABLE` y el nombre de la tabla debemos poner lo siguiente `IF NOT EXISTS`

### Modifying tables

Podemos eliminar, añadir y modificar columnas utilizando la expresión `ALTER TABLE` luego colocamos el nombre de la tabla y las acciones que deseamos realizar

#### ADD

Con la palabra reservada `ADD` podemos añadir una columna para esto primero ponemos `ADD` luego el nombre de la columna, su tipo, una condición opcional y por ultimo podemos darle un valor por 
defecto usando la palabra reservada `DEFAULT` 

#### DROP

Para eliminar una columna usamos la palabra reservada `DROP` y luego colocamos el nombre de la columna que deseamos eliminar 

#### RENAME TO

Para cambiar el nombre de la tabla usamos la expresión `RENAME TO` y luego ponemos el nuevo nombre que deseamos asignar a la tabla 

#### DROP TABLE

Para eliminar una tabla podemos usar la expresión `DROP TABLE` y luego el nombre de la tabla, esto eliminará toda la información relacionada a la tabla, si alguna otra tabla depende de información de
la tabla que deseamos eliminar deberemos o eliminar ambas o modificar la tabla para que no dependa de la que vamos a eliminar, podemos usar `IF EXISTS` antes del nombre de la tabla para que solo 
se elimine si la tabla existe

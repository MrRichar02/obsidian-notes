### IIF

La función `IIF` recibe 3 parámetros el primero es una condición que va a evaluar, el segundo es lo que retornara si la condición es verdadera y el tercer parámetro es lo que retorna si la condición es
falsa 

#### BETWEEN ... AND ...

Podemos filtrar entre un rango de números usando las palabras reservadas BETWEEN y AND, entre ellas ponemos el primer numero y al final el ultimo

#### DISTINCT

Si colocamos la palabra reservada DISTINCT justo después del SELECT nuestra búsqueda eliminara todas los elementos repetidos para asegurar que solo hay elementos únicos 
#### AND y OR

podemos usar AND y OR para sumar condiciones 

#### Strings LIKE

para comparar Strings de una manera no case sensitive podemos usar la palabra reservada LIKE

### LIMIT

Nos permite limitar el numero de filas que queremos en la respuesta 

#### ORDER BY

Podemos ordenar una columna usando las palabras reservadas ORDER BY, luego de las palabras colocamos el nombre de la columna que deseamos ordenar, y luego del nombre de la columna podemos
colocar dos opciones `ASC` o `DESC` dependiendo de si lo queremos ordenar de manera ascendente o descendente, el valor por default si no ponemos nada es `ASC`
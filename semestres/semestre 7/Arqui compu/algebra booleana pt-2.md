[[Indice arqui de compu]] para ir al siguiente 
[[algebra booleana pt-1]] para ir al anterior 

## Formas canónicas 

Con las formas canónicas podemos obtener expresiones únicas para alguna función booleana que se represente usando tablas de verdad, entre las formas canónicas tenemos **la suma de min-términos (minterms)** y **el producto de max-términos (maxterms)** 

Tomamos suma como el operador OR {+} y producto como el operador AND {.}

### minterm 
- Es una función booleana que solo regresa 1 como salida en una de sus filas 
- La función esta compuesta de n variables y el minterm es un término producto de n literales, tiene una regla especial de que se complementan las variables donde el valor asignado por la combinación es 0 de lo contrario no se complementa la variable

### maxterm

- Es una función booleana que solo regresa 0 como salida en una de sus filas 
- La función esta compuesta de n variables y el maxterm es un término suma de n literales, tiene una regla especial de que se complementan las variables donde el valor asignado por la combinación es 1 de lo contrario no se complementa la variable


A continuación vamos a obtener el minterm y maxterm para las tres variables binarias X, Y, Z y también vamos a representar su notación 


| Número de fila | XYZ | Minterm | Notación minterm | Maxterm      | Notación Maxterm |
| -------------- | --- | ------- | ---------------- | ------------ | ---------------- |
| 0              | 000 | X´Y´Z´  | $m_0$            | X + Y + Z    | ${M_0}$          |
| 1              | 001 | X´Y´Z   | $m_1$            | X + Y + Z´   | ${M_1}$          |
| 2              | 010 | X´YZ´   | $m_2$            | X + Y´ + Z   | ${M_2}$          |
| 3              | 011 | X´YZ    | $m_3$            | X + Y´ + Z´  | ${M_3}$          |
| 4              | 100 | XY´Z´   | $m_4$            | X´ + Y +  Z  | ${M_4}$          |
| 5              | 101 | XY´Z    | $m_5$            | X´ + Y + Z´  | ${M_5}$          |
| 6              | 110 | XYZ´    | $m_6$            | X´ + Y´ + Z  | ${M_6}$          |
| 7              | 111 | XYZ     | $m_7$            | X´ + Y´ + Z´ | ${M_7}$          |
## Teorema de Morgan 

### ${m_i´ = M_i}$
### ${M_i´ = m_i}$


## Forma canónica "Suma de minterms"

Para expresar una función de esta forma debemos hacer la sumatoria de los minterms donde la función que queremos representar regresa 1 en la salida

veamos un ejemplo 

Tenemos la función ${F_1}$ con la siguiente tabla de verdad 

| Indice | xyz | ${F_1}$ | ${F_1´}$ |
| ------ | --- | ------- | -------- |
| 0      | 000 | 0       | 1        |
| 1      | 001 | 0       | 1        |
| 2      | 010 | 0       | 1        |
| 3      | 011 | 1       | 0        |
| 4      | 100 | 0       | 1        |
| 5      | 101 | 1       | 0        |
| 6      | 110 | 1       | 0        |
| 7      | 111 | 1       | 0        |

Para representar tanto a ${F_1}$ como a ${F_1´}$ usando la forma canónica de suma de minterms hacemos lo siguiente 

$\Large{F_1(x,y,z) = \sum (3, 5, 6, 7) = m_3 + m_5 + m_6 + m_7 = x´yz + xy´z + xyz´ + xyz}$

En la primera forma de la expresión en la sumatoria colocamos los indices de las filas donde la función da 1, luego colocamos esas filas en la notación de minterm y por ultimo reemplazamos la notación por el minter correspondiente para esa fila

$\Large{F_1´ = \sum (0,1,2,4) = m_0 + m_1 + m_2 + m_4 = x´y´z´ + x´y´z + x´yz´ + xy´z´}$

## Forma canónica "Producto de maxterms" 

Para expresar una función usando el producto de maxterms debemos de hacer el producto de todos los maxterms en los que la función a representar regrese 0 en la salida 

Veamos un ejemplo

Si tenemos una función ${F_1}$ y la siguiente es su tabla de verdad 


| Indice | xyz | ${F_1}$ | ${F_1´}$ |
| ------ | --- | ------- | -------- |
| 0      | 000 | 0       | 1        |
| 1      | 001 | 0       | 1        |
| 2      | 010 | 0       | 1        |
| 3      | 011 | 1       | 0        |
| 4      | 100 | 0       | 1        |
| 5      | 101 | 1       | 0        |
| 6      | 110 | 1       | 0        |
| 7      | 111 | 1       | 0        |
Para representar tanto a ${F_1}$ como a ${F_1´}$ con la forma de producto de maxterms hacemos lo siguiente 

$\Large{F_1(x,y,z) = \prod (0,1,2,4) = M_0 M_1 M_2 M_4 = (xyz) (xyz´) (xy´z) (x´yz)}$
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

Primero colocamos la productoria con los indices de las filas donde la función da 0, luego usamos la notación de maxterm para representar los indices y finalmente colocamos la forma de producto de maxterm que sería hacer le producto de los distintos maxterm en el orden que van apareciendo(en este caso 0, 1, 2 y 4)

$\Large{F_1´ = \prod (3, 5, 6, 7) = M_3 M_5 M_6 M_7 = (xy´z´) (x´yz´) (x´y´z) (x´y´z´)}$


## Pasar de una forma canónica a otra 

Para pasar debemos de intercambiar la sumatoria por productoria o viceversa y los indices que ubicamos en la operación también deben de ser cambiados por los que no están, entonces aplicando esto lo siguiente sería cierto 

$\large{F(X,Y,Z) = \prod (2,3,4,6) = \sum (0,1,5,7)}$

## Formas estándar 

### Suma de productos (SOP)

Es como una forma canónica de suma de minterms pero no es obligatorio que todos los terminos de producto cuenten con todas las variables que se incluyen en la función, un ejemplo es el siguiente 

${F(x,y,z) = xy + xy´z + x´yz}$


## Producto de sumas (PoS)

Es como la forma canónica de producto de maxterms pero no es obligatorio que todos los terminos suma incluyan todas las variables de la función, veamos un ejemplo

${F(x,y,z) = (x´+y´)(x+y´+z´)(x´+y+z)}$

### Como se obtienen?

para obtener las formas estándar se usan los teoremas del algebra booleana para simplificar las formas canónicas, esto hace que las formas estándar no  sean únicas para cada función 

Veamos un ejemplo:

${F(x,y,z) = xyz + xyz´ + xy´z + xy´z´ = xy + xy´ = x}$

## BCD

### ¿Qué son?

Es una forma de representar dígitos decimales utilizando 4 bits, tienen una rango desde ${0000_2}$ que representa al 0 hasta ${1001_2}$ que representa al 9, las combinaciones que van desde ${1010}$ que representa al 10 hasta ${1111}$ que representa al 15 no se utilizan 

### Tabla de verdad

| wxyz | F   |
| ---- | --- |
| 0000 | 0   |
| 0001 | 0   |
| 0010 | 0   |
| 0011 | 0   |
| 0100 | 0   |
| 0101 | 0   |
| 0110 | 0   |
| 0111 | 1   |
| 1000 | 1   |
| 1001 | 0   |
| 1010 | x   |
| 1011 | x   |
| 1100 | x   |
| 1101 | x   |
| 1110 | x   |
| 1111 | x   |
Las filas donde la función F regresa como resultado 0 pertenecen al conjunto OFF de F(w,x,y,z)
Las filas donde la función F regresa como resultado 1 pertenecen al conjunto ON de F(w,x,y,z)
Las filas donde la función F regresa como resultado x pertenecen al conjunto Don't care (DC) de F(w,x,y,z)

En este caso usamos la x para representar los don't care pero en la realidad no se regresa una x simplemente no se usan 

### Formas canónicas con don't care

En ambas formas se colocan los don't care pero en la suma de minterms se usa la d para representarlos y en el producto de maxterms se usa la D para representarlos, veamos un ejemplo 

$\large{J(w,x,y,z) = m_0 + m_2 + m_4 + m_6 + m_8 + d_{10} + d_{11} + d_{12} + d_{13} + d_{14} + d_{15}}$
$\large{=\sum (0,2,4,6,8) + d(10,11,12,13,14,15)}$

$\large{J(w,x,y,z) = M_1 + M_3 + M_5 + M_7 + M_9 + D_{10} + D_{11} + D_{12} + D_{13} + D_{14} + D_{15}}$
$\large{=\prod (1,3,5,7,9) + D(10,11,12,13,14,15)}$

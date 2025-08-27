[[Indice arqui de compu]] para ir al indice
[[algebra booleana pt-2]] para ir al anterior

## Cubos booleanos

Son una forma de representar las diferentes combinaciones de las variables, aunque se llamen cubos dependiendo de la dimensión en la que este va a tener una forma, por ejemplo en una dimensión va a ser una linea, en dos dimensiones va a ser un cuadrado y en tres dimensiones va a ser un cubo 

veamos unos ejemplos 
![[Pasted image 20250826160414.png]]

### Simplificación

Para simplificar primero debemos de marcar los puntos que pertenecen al conjunto ON de la función a simplificar, luego con estos puntos vamos a crear suconjuntos en el cubo, que son cubos de menor dimensión, por cada subconjunto va a ser un termino que agregamos para representar la función, para crear el termino hay que tener en cuenta dos cosas, la primera es cual es la dimensión del subconjunto que vamos a llamar m y esto lo vamos a restar a la dimensión del cubo que vamos a simplificar el cual vamos a llamar n, el resultado de esta resta nos va a dar el numero de variables que va a incluir el termino que va a representar el subconjunto, luego de esto para obtener la variable que vamos a agregar debemos observar en el subconjunto que formamos cual es la variable o las variables que no cambian de valor, estas van a ser las que vamos a conservar y dependiendo de si están en 1 o en 0 vamos a poner su versión negada o la normal

Veamos el siguiente ejemplo 

![[Pasted image 20250826161027.png]]

Aqui vemos que se forma un cuadro que tiene dimensión 2 que va a ser nuestro m, mientras que la dimensión del cubo grande es de 3, al hacer la resta obtenemos 1 entonces el termino final solo va a conservar una variable, para saber que variable es observamos cual es la variable que no cambia, en este caso para 110, 111, 100 y 101 vemos que la variable que no varía es la primera osea la X y como su valor está en 1 no ponemos su versión negada, entonces esta variable F se puede representar solo con X, F(X,Y,Z) = X

Nota: Para la simplificación debemos encontrar la menor cantidad de subconjuntos y que estos tengan la mayor dimensión posible pues así disminuimos la cantidad de términos y variables usadas para representar la función 


Veamos otro ejemplo

![[Pasted image 20250826161434.png]]

Aquí no podemos crear un cuadrado para todos los puntos que pertenecen al conjunto ON y nuestra mejor opción es definir tres subconjuntos todos de una dimensión, entonces van a tener dos variables que se van a conservar, no hay problema con que se compartan puntos entre los subconjuntos, en este caso se va a representar la función de esta manera 

F(X,Y,Z) = YZ + XY + XZ

### Problema de los cubos

El problema de usar los cubos es que cuando aumenta la dimensión se vuelve muy complicado realizar la implementación de la figura 

## Mapas de Karnaugh (Mapas K)

Es otro forma de realizar la simplificación de funciones booleanas, que tiene mas resistencia al aumentar las dimensiones en contrario que la cubos

Para realizar estos mapas vamos a hacer tablas y en las filas y columnas vamos a poner las variables con sus distintos posibles valores, existe una regla especial para ubicar los distintos valores y es que entre las columnas o las filas solo puede variar un bit del valor, en el caso donde tenemos dos variables no nos presenta un reto pues podemos hacer lo siguiente 
![[Pasted image 20250826162951.png]]

Ya cuando tenemos 3 variables si tenemos un reto porque en las filas o en las columnas debemos de ubicar dos variables y entre las distrintas combinaciones solo se pueden ir variando un bit, para esto podemos usar el código de gray que lo que nos dice es que para ir aumentando el numero de variables y que se siga cumpliendo que solo varia un bit solo tenemos que repetir la cadena de combinaciones que ya teníamos y revertirla

Por ejemplo para pasar a la forma en que se distribuyen las combinaciones cuando son dos variables en las filas o columnas ya sabemos que la cadena en la dimensión anterior es 01 entonces solo debemos ponerla invertida 

lo que nos da 

0
1
1
0

pero tenemos que agregar otro bit para representar las dos variables entonces lo que vamos a hacer es agregar a la izquierda de la primera mitad de arriba a abajo un 0 y a los demas un 1, lo que nos deja con lo siguiente 

00
01
11
10

Ahora observemoslo en la forma de la tabla 

![[Pasted image 20250826163436.png]]

Si pasaramos a usar 3 variables para las filas o columnas podríamos hacer lo mismo 

### Que va adentro de las celdas de la tabla ?

En las celdas encontramos en la parte inferior izquierda el valor decimal que obtenemos al calcular los bits que se cruzan en esa celda, debemos tomar en cuenta cuales son mas significativos que los otros, luego en la parte superior podemos encontrar si el valor retornado por la función para esa combinación es de 0 o 1 o también la representación del termino usando las variables, las variables estarán negadas si para esa combinación tienen un valor de 0
[[reconocimiento descendente]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice

https://www.youtube.com/watch?v=U2rDZQ84Cek

Tabla análisis sintáctico:

en esta tabla se obtiene el análisis de todos los caminos de derivación posibles sobre una gramática, consta de dos partes la acción y las transición 

veamos un ejemplo con la siguiente GIC

V -> aW
W -> bbW
W -> c

lo primero a hacer es agregar el símbolo no terminal inicial que suele ser S pero en este ejemplo será V'

V' -> V
V -> aW
W -> bbW
W -> c

el siguiente paso a realizar es obtener los primeros y segundos 

Primeros:

P(V') = {a}
P(V) = {a}
P(W) = {b, c}

SIguientes:
S(V') = {$}
S(V) = {$}
S(W) = {$}

Ahora vamos a ir avanzando entre estados, los estados se representan con In y n empieza en 0, ademas estos estados inician con la primera producción 

I0: 
  I1 V' -> .V            el . se conoce como función de cerradura

para el segundo estado vamos a poner lo que se produce luego de la función de cerradura

  I2 V -> .aW volvemos a poner .

en lo anterior tenemos que I0 produce I1 y I2, ahora vamos a derivar I1 para eso agarramos el I1 que teníamos antes (nota: por eso le puse como indentación a I1 y I2)

I1 V' -> V. si se fijan la única diferencia a como estaba antes es que movimos la función de cerradura, como luego de la función de cerradura no hay nada y estamos en la producción inicial V' ponemos el estado de aceptación 

aceptación
$

ahora derivemos a I2

I3 V -> a.W al igual que en I1 movemos la función cerradura y nos quedo en W entonces vamos a poner lo que genera W como la derivación de I2 nos da V a.W que no es igual a I2 nos toca crear un nuevo estado I3

  I4 W -> .bbW agregamos la función de cerradura al principio porque es la primera vez que la ponemos 

  I5 W -> .c agregamos la función de cerradura al principio porque es la primera vez que la ponemos

antes de agregar el I4 y I5 nos debemos de fijar en si ya existen los estados que tenga W -> .bbW o W -> .c en los estados anteriores como en este caso no sucede entonces agregamos I4 y I5

ahora vamos a derivar a I3

V -> aW. volvemos a mover la función de cerradura y como luego de la función de cerradura no hay nada osea que se termino la producción debemos de realizar una reducción, para eso primero enumeremos las producciones del 
GIC

0. V' -> V
1. V -> aW
2. W -> bbW
3. W -> c
luego con esa enumeración vamos a buscar el numero al que corresponde lo que esta antes de la función de cerradura V ->aW, en este caso corresponde al numero 1, entonces la reducción a realizar es para la producción 1, por lo
que se va a representar con R1

R1 V -> aW

ahora vamos a derivar I4

  I6 W -> b.bW movemos nuevamente la función de cerradura, como lo que obtenemos no se parece a ningún estado ya definido agregamos uno nuevo 

ahora vamos a derivar I5

  W -> c. movemos la función de cerradura y nuevamente nos queda nada al luego de la función de cerradura lo que indica un reducción asi que buscamos a con que coincide W -> c en la enumeración, en este caso es el numero 3
por lo que vamos a representar esta reducción con R3

ahora vamos a derivar I6

  I7 W -> bb.W nuevamente movemos la función de cerradura como es diferente a lo anterior agregamos nuevo estado, en este caso nos quedo al frente de la función de cerradura W entonces debemos poner lo que produce W, 
  como ya habíamos enumerado antes estas producciones con los estados I4, I5 no creamos nuevos estados 
  I4 W -> .bbW
  I5 W -> .c

ahora vamos a derivar I7

  W -> bbW. movemos la función de cerradura y vemos que nos queda nada luego de la función de cerradura lo que indica reducción buscamos la enumeración para W -> bbW y encontramos que es 2 entonces nos queda 
  R2 W -> bbW

para verificar que hemos terminado este proceso debemos de mirar que para cada producción del GIC este su reducción, para el primero V' -> que es la 0 su reducción es el estado de aceptación, para V -> aW su reducción es 
R1, para W -> bbW su reducción es R2 y para W -> c su reducción es R3, si nos fijamos ya llegamos a cada una entonces hemos finalizado correctamente 

Tabla de análisis de caminos de derivación:

en la columna de acción vamos a poner todos los símbolos no terminales y la de transición vamos a poner todos los símbolos no terminales exceptuando al inicial, luego empezamos desde 
el estado 0 I0 y lo que hacemos es primero mirar que produce ese estado, en este caso nos fijamos y I0 produce I1 V' -> .V y I2 V -> .aW, nos fijamos en que símbolo quedo luego 
de la función de cerradura, en esta caso son en I1 la V y en I2 la a, con esta información para este estado 0 en la columna de la V vamos a poner el numero del estado 1 porque en I1 es 
donde luego de . se encuentra la V, luego hacemos lo mismo para el otro símbolo en el estado 0 y en la columna a vamos a poner el numero del estado donde se encontró a la a que en 
este caso es I2 por lo que el numero sería 2 pero cuando el símbolo es terminal tenemos que agregar algo antes del numero, lo que agregamos es una d porque cuando el símbolo es 
terminal la acción es de desplazamiento entonces nos quedaría d2.

ahora vamos a seguir con el estado 1, en el estado 1 solo tenemos que nos genera el estado de aceptación con $ entonces en las coordenadas de estado 1 y con $ vamos a poner Acc

ahora vamos a seguir con el estado 2 el cual produce I3, I4 y I5, en I3 el símbolo luego de la función de cerradura es W por lo que en las coordenadas estado 2 y con W vamos a poner 3
luego con I4 nos queda b pero como es terminal vamos a poner es d4 en las coordenadas de estado 2 y b ya para I5 nos queda c y como es terminal se hace lo mismo que en I4

ahora vamos a seguir con el estado 3, en el estado tenemos a R1 esto significa que debemos de irnos a los siguientes de donde se produjo la reducción que en este caso es V -> aW, luego 
con los siguientes en todas las columnas de los elementos de los siguientes en la fila del estado 3 vamos a poner R1, en este caso es solo para $

ya con esta lógica podemos acabar de rellenar la tabla 

|         | Acción | <   | <   | <   | Transición | <   |
| ------- | ------ | --- | --- | --- | ---------- | --- |
| Estados | a      | b   | c   | $   | V          | W   |
| 0       | d2     |     |     |     | 1          |     |
| 1       |        |     |     | Acc |            |     |
| 2       |        | d4  | d5  |     |            | 3   |
| 3       |        |     |     | R1  |            |     |
| 4       |        | d6  |     |     |            |     |
| 5       |        |     |     | R3  |            |     |
| 6       |        | d4  | d5  |     |            | 7   |
| 7       |        |     |     | R2  |            |     |

Utilización del método

vamos a analizar la cadena abbc$ (nota: el parcero del video dijo que a veces se agrega el $)

empezamos con el estado 0 en la pila, luego en la entrada ponemos la cadena que vamos a analizar, para la acción miramos que tenemos el estado 0 y el símbolo mas a la derecha es una a, con esto nos vamos a la tabla que 
hicimos ahorita y vemos que en esas coordenadas nos da d2, esto lo ponemos en acción, ahora para la siguiente fila la acción d2 significa que debemos de tomar esa a y añadirla al estado lo que nos dejaría 0a y ademas 
debemos agregar un 2 al final lo que finalmente nos deja en la columna de pila 0a2, al desplazar la a a la pila debemos de quitarla de la entrada, entonces en la entrada nos quedaría bbc$, ahora para acción miramos en la tabla
para 2 y b lo que nos da d4, entonces debemos de desplazar b a la pila y agregar el 4 al final y quitar la b de la entrada. Ahora para la acción miramos en la tabla para 4 con b lo que nos da d6 entonces desplazamos a b a la pila
y lo quitamos de la entrada, para la acción vamos a mirar en la tabla para 6 y c lo que nos da d5 entonces desplazamos la c, agregamos el 5 al final y quitamos la c de la entrada, para la entrada miramos en la tabla para 6 y $
lo que nos da R3, osea la reducción 3 si nos fijamos en la GIC la 3 se refiere a W -> c entonces en la parte de acción vamos a poner R3 W -> c, esto significa que en la pila donde tengamos una c la vamos cambiar por una W y 
para cambiar el numero que acompañaba a la c vamos a comparar en la tabla para W con el numero que estaba justo antes de la c en nuestro caso es 6 al comparar en la tabla W y 6 nos da 7 entonces vamos a cambiar el 
numero que acompañaba a la c por 7 en el caso del ejemplo es cambiar a 5 por 7, ahora para la acción vamos a mirar en la tabla para 7 con $ lo que nos da R2,  otra reducción entonces hacemos lo mismo que pa la anterior, en 
este caso vamos a buscar reemplazar bbW por W si nos fijamos en la entrada ahorita tenemos 0a2b4b6W7  si no tomamos en cuenta los números tenemos abbW entonces la parte sin incluir la a es la que vamos reemplazar por 
W y para el numero que va a acompañar a esta W comparamos justo el numero antes de bbW que es 2 en este ejemplo con la W que vamos a reemplazar lo que nos da 3, entonces en la pila nos va a quedar 0a2W3 ahora para la 
acción miramos en la tabla para 3 con $ lo que nos da R1 osea otra reducción pero en este caso para V -> aW osea que en la pila debemos buscar para reemplzar aW por V y efectivamente esta por lo que lo reemplazamos y 
para el numero que va a acompañar a esta V miramos en la tabla para V con el numero que esta justo antes de aW que en este caso es 0 lo que nos da 1, entonces en la pila nos queda 0V1, para la acción miramos la tabla para 
1 con $ lo que nos da Acc lo que significa que terminamos y la cadena es valida y ponemos Acc en la acción 


(nota: si e algún momento alguna combinación de la pila y la entrada nos da en una parte de la tabla vacío significa que hay un error de sintaxis)

| Pila      | Entrada | Acción      |
| --------- | ------- | ----------- |
| 0         | abbc$   | d2          |
| 0a2       | bbc$    | d4          |
| 0a2b4     | bc$     | d6          |
| 0a2b4b6   | c$      | d5          |
| 0a2b4b6c5 | $       | R3 W -> c   |
| 0a2b4b6W7 | $       | R2 W -> bbw |
| 0a2W3     | $       | R1 V -> aW  |
| 0V1       | $       | Acc         |


Explicación mas clara del paso a paso:

Lo primero que vamos a hacer agregar un símbolo no terminal que suele ser S y que nos lleve al primer símbolo no terminal de la GIC, luego vamos a obtener los primeros y siguientes, después vamos a seguir con los estados In
empezamos con el I0 que produce al estado I1 que es el primer símbolo no terminal que agregamos al inicio y debemos agregar la función de cerradura como este I1 suele ser de la forma V' -> .V I0 va a producir a otro estado I2
el cual sera lo que produzca V agregándole al inicio de lo que produce la función de cerradura, luego continuamos derivando los demás estados y si lo que derivan estos estados no se ha generado antes formamos un nuevo 
estado, si alguna en alguna derivación nos queda que no hay nada luego de la función de cerradura significa que llegamos a la reducción y debemos de buscar en el GIC la producción que coincida con lo que esta antes del .
luego con la enumeración de esa producción formamos la reducción Rn, existe un caso especial para lo anterior y es cuando lo que esta antes del . la primera producción que agregamos al incio, en ese caso lo que se obtiene es 
el estado de aceptación $, sabemos que hemos finalizado cuando ya tenemos las reducciones para cada producción del GIC y el estado de aceptación

para realizar la tabla ponemos de filas los estados y de columnas primero los símbolos terminales de la gramática y luego los no terminales para llenar las filas de cada estado nos vamos sus derivaciones, observamos lo que 
derivan y en sus derivaciones que queda luego de la función de cerradura o si derivan es en una reducción, en el primer caso si luego de la función de cerradura queda un símbolo no terminal en la fila del estado para la 
columna de ese símbolo no terminal vamos a poner el numero de la derivación en la que se encontro osea que si estamos en las derivaciones de 0 y tenemos que en I1 nos queda luego del . la W para la fila 0 en la columna W
ponemos 1, en el caso de que el símbolo sea terminal vamos a hacer algo similar solo que antes del numero agregamos una d que implica desplazamiento, entonces digamos que en las derivaciones de 0 tenemos que en I2 
luego del . nos queda a entonces en la fila de 0 columna a pondríamos d2 finalmente en el caso de que encontremos una reducción vamos a hacer algo similar al anterior solo que cambiamos la d por una R y para los elementos 
de las columnas vamos a tomarlos de los siguientes de la producción a la que se le este haciendo la reducción entonces para el caso de las derivaciones de 0 si tenemos que I3 nos da R1 en la fila de 0 columna digamos que sus
siguientes son solo $ entonces solo sería la columna $ en la que ponemos R1, en el caso especial de que lo que tengamos en la derivación sea Acc hacemos lo mismo que antes solo que en lugar de poner algún Rn ponemos Acc

Para validar una cadena creamos una tabla con 3 columnas pila, entrada y acción, la columna de pila se inicia con 0 que es el primer estado, la columna de entrada se inicia con la cadena a validar y para la columna de acción 
tomamos el estado 0 y el símbolo que este mas a la izquierda de la cadena, estas seran nuestras coordenadas para la tabla, lo que nos de en la tabla es lo que ponemos en acción, nos puede salir para la acción un dn, o Rn o Acc
en el caso del dn lo que hacemos es tomar el símbolo mas a la izquierda de la cadena y lo añadimos por la derecha a la pila y luego de ese símbolo añadimos también por la derecha de la pila el numero n que acompañaba a la d, 
en el caso de que nos salga un Rn vamos a ir al GIC a buscar la producción n y luego con lo que encontremos intentaremos reemplzar en la pila según la producción que nos toque, por ejemplo si nos toca la producción W -> acW
intentaremos reemplazar acW por W, no vamos a encontrar literal acW en la pila sino algo como a2c3W4 y cuando reemplacemos para obtener el numero que va a acompañar a lo que reemplazamos lo que hacemos es tomar 
primero el símbolo que vamos a reemplazar y el numero que esta justo antes de lo que vamos a reemplazar, para el caso del ejemplo sería el numero que esta justo antes de a y esos dos valores nos servirán como coordenadas 
en la tabla, el valor que obtengamos de la tabla sera el numero que va a acompañar a lo que reemplacemos, finalmente si nos sale un Acc significa que la cadena es valida 

para ilustrar mas vemos como hago el lab 8 que hacer el taller #10

[[lab 8 teoria]]
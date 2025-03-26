[[Automatas finitos deterministicos]] para volver al anterior 
[[Indice teoría de lenguajes y lab]] para volver al indice 

Para minimizar a un AFD lo primero que hay que hacer es particionar los estados del 
AFD en dos grupos {$\large{G_1 , G_2}$} en el primer grupo se coloca los estados de aceptación
en el segundo se colocan el resto de los estados.



![[Pasted image 20240816142239.png]]
Para este AFD tenemos que $\large{G_1 = \{E\} \text{ y que } G_2 = \{A,B,C,D\}}$ el primer grupo no 
se puede refinar porque solo tiene un estado mientras que el segundo si se puede 
refinar, para hacer eso se realiza la siguiente tabla 

![[Pasted image 20240816142557.png]]

<b>Como interpreto la tabla ?</b>

bueno aqui las columnas se refieren a los símbolos que se le puede dar al AFD, en 
este caso son a y b, las filas se refieren a los estados, pero a los estados del grupo
que se esta analizando en el caso de la tabla en la imagen es el grupo $\large{G_2}$, en cada 
celda se ve el estado al que viajaría el AFD en el estado x con el símbolo y, por 
ejemplo para el estado A con el símbolo a se va al estado B y como vemos dice que
ese estado que nos dio de resultado pertenece al grupo $\large{G_2}$, la idea aquí es detectar 
en una columna cuales son los estados que resultan en ir a un grupo diferente que el 
de los demás estados, por ejemplo aquí el estado D con el símbolo b se va al grupo 1 
pero el resto de estados cuando se les da el símbolo b van al grupo 2 osea que el 
diferente es el estado D sabiendo esto ahora debemos de mover el estado D a otro
grupo

Según lo anterior debemos sacar al estado D del grupo 2 entonces nos quedaría que 
$\large{G_1 = \{E\} \text{, } G_2' = \{A,B,C\} \text{ y que } G_3 = \{D\}}$ notemos que el grupo 2 quedo como 
$\large{G_2'}$ esto es porque en si no es el mismo grupo sino una versión modificada de este
ahora volvemos a hacer el análisis para el nuevo grupo 2 que nos quedo 

![[Pasted image 20240816152743.png]]

En este caso se observa que el que tiene un resultado de grupo diferente es el estado
B cuando se le da el símbolo b ya que se va al grupo 3 el cual es diferente a los demás
resultados cuando se da el símbolo b al estado, entonces movemos el estado B a un 
nuevo grupo quedándonos:

$\large{G_1 = \{E\}, G_2'' = \{A,C\}, G_3 = \{D\}, G_4 = \{B\}}$

Si se observa se vuelve a modificar la notación del grupo 2 ya que sus elementos 
fueron modificados nuevamente y se creo un nuevo grupo para el estado B. 
Volvamos a realizar el análisis con la tabla 

![[Pasted image 20240816153902.png]]

Como se puede observar todos los estados del grupo $\large{G_2''}$ tienen el mismo resultado
en cuanto a grupos entonces hasta aquí se pueden retirar estados, en cuanto el 
resto de grupos solo tienen un estado entonces no se les puede retirar alguno 

Los estados del grupo $\large{G_2''}$ se fusionan en un solo estado y el AFD en forma de 
diagrama nos quedaría de la siguiente manera 

![[Pasted image 20240816154331.png]]

<b>Equivalencia entre AFD:</b>

Para que dos AFD sean equivalentes hay que particionar los estados de ambos AFD 
y  si obtenemos que los estados iniciales de ambos AFD luego de realizar una 
minimización quedan en el mismo grupo significa que si son equivalentes, veamos 
un ejemplo 

![[Pasted image 20240816160002.png]]

Los el primer grupo se forma de los estados de aceptación tanto del primer como 
del  segundo AFD y el resto de estados se van para el grupo 2, primero observemos 
si  podemos retirar algún estado  del grupo 1 para eso usamos la tabla 

![[Pasted image 20240816160241.png]]

Como se observa no se puede retirar algún estado del grupo 1, ahora hagamos lo
mismo pero para el grupo 2 

![[Pasted image 20240816160428.png]]

En este caso el estado s con el símbolo a nos da un grupo diferente que el que le da
al resto de estados con ese mismo símbolo, entonces es necesario sacarlo del grupo

Al realizar lo anterior nos quedan los grupos de la siguiente manera:
$\large{G_1 = \{q,r,w\}, G_2' = \{p,u,v\}, G_3 = \{s\}}$ se modifica la notación del grupo 2 
porque se modificaron los estados del grupo y se creo el grupo 3, ahora volvemos
a analizar el nuevo grupo 2 para ver si podemos quitar otro estado 

![[Pasted image 20240816160908.png]]
Todos los estados van al mismo grupo entonces no se pueden quitar, ya que no se 
pueden quitar mas estados de los grupos debemos fusionar los estados de los grupos

Teniendo en cuenta como quedaron finalmente los grupos 
$\large{G_1 = \{q,r,w\}, G_2' = \{p,u,v\}, G_3 = \{s\}}$ podemos observar que los estados 
iniciales de ambos AFD(los estados p y v ) quedaron en el mismo grupo( el grupo $\large{G_2'}$ 
esto nos indica que ambos AFD son equivalentes 

En forma de diagrama el AFD nos quería de la siguiente manera 

![[Pasted image 20240816161024.png]]

Como podemos observar no hay manera de llegar al estado s del grupo 3 entonces 
se le considera un estado muerto y se puede retirar, dando como resultado lo 
siguiente 

![[Pasted image 20240816161546.png]]

[[Autómatas finitos no deterministicos]]
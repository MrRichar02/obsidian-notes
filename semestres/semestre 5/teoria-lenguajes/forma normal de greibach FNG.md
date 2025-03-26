[[forma normal de chomsky FNC]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice 


Para que un GIC este en FNG debe de cumplir que la variable inicial no sea recursiva, que no tenga variables inutiles, que no tenga  producciones $\large{\lambda}$  y que todas las producciones sean de 
la forma A -> a o de la forma A -> $\large{a B_1 B_2 B_3 \dots B_k}$ 

Una variable es recursiva si tiene la siguiente forma A -> Aw donde $\large{w \in (V U \Sigma)}$ osea que w pertenece al conjunto de variables o al alfabeto para eliminar la recursividad tomamos en cuenta
que las producciones de una variable cualquiera se pueden dividir en dos clases 

A -> A$\large{\alpha_1}$|A$\large{\alpha_2}$|A$\large{\alpha_3 | \dots}$ A$\large{\alpha_n}$ 
A -> $\large{\beta_1}$|$\large{\beta_2}$|$\large{\beta_3 | \dots}$ $\large{\beta_m}$ 

donde $\large{\alpha_i, \beta_i \in (V U \Sigma)}$ osea que pertenecen al conjunto de variables unidos con el alfabeto y ademas el primer símbolo $\large{\beta_i}$ es diferente de A, sin alterar el lenguaje las producciones 
anteriores se pueden simular reemplazándolas por las siguientes 

A -> $\large{\beta_1 | \beta_2 | \dots | \beta_m | \beta_1Z | \beta_2Z | \dots | \beta_mZ}$ 
Z -> $\large{\alpha_1 | \alpha_2 | \dots | \alpha_m | \alpha_1Z | \alpha_2Z | \dots | \alpha_mZ}$  

aqui Z es una variable nueva 

veamos un ejemplo 

S -> AA|a
A -> AA|b

en este caso la recursividad se presenta con A primero definimos los alphas y betas em este caso solo son 1 por cada uno peor pueden ser mas 

$\large{\alpha_1}$ = A
$\large{\beta_1}$ = b

al aplicar la trasformación 

A -> $\large{\beta_1 | \beta_2 | \dots | \beta_m | \beta_1Z | \beta_2Z | \dots | \beta_mZ}$ 
Z -> $\large{\alpha_1 | \alpha_2 | \dots | \alpha_m | \alpha_1Z | \alpha_2Z | \dots | \alpha_mZ}$  

nos queda 

S -> AA|a
A -> b|bZ
Z -> A|AZ

Ahora donde este la A vamos a reemplazar por b|bZ lo que nos quedaría

S -> bA|bZA|a
A -> b|bZ
Z -> b|bZ|bZZ

si se dan cuenta solo se reemplaza la primera A en caso de haber mas de una y se reemplaza primero con una de las producciones y luego con la otra y si hay repetidos solo se deja uno 

y ya nos quedaría en FNG

veamos otro ejemplo 

S -> AB|BC
A -> AB|a
B -> AA|CB|a
C -> a|b

identificamos que la recursiva es otra vez A y ahora vamos a identificar los alphas y betas 

$\large{\alpha_1}$ = B
$\large{\beta_1}$ = a

hacemos la sustitución y nos queda 

S -> AB|BC
A -> a|aZ
B -> AA|CB|a
c -> a|b
Z -> B|BZ

ahora que hemos solucionado la recursividad vamos a primero mirar cuales producciones ya están en FNG y las que no miramos la manera de sustituir para que lo estén


S -> (a|aZ)B|BC
A -> a|aZ
B -> (a|aZ)A|CB|a
c -> a|b
Z -> B|BZ

aplicamos la sustitución 

S -> aB|aZB|BC
A -> a|aZ
B -> aA|aZA|CB|a
c -> a|b
Z -> B|BZ

Hacemos otra sustitución

S -> aB|aZB|BC
A -> a|aZ
B -> aA|aZA|(a|b)B|a
c -> a|b
Z -> B|BZ


S -> aB|aZB|BC
A -> a|aZ
B -> aA|aZA|aB|bB|a
c -> a|b
Z -> B|BZ

y hacemos otra sustitución 

S -> aB|aZB|BC
A -> a|aZ
B -> aA|aZA|aB|bB|a
c -> a|b
Z -> (aA|aZA|aB|bB|a)|(aA|aZA|aB|bB|a)Z

reemplazamos 

S -> aB|aZB|BC
A -> a|aZ
B -> aA|aZA|aB|bB|a
c -> a|b
Z -> aA|aZA|aB|bB|a|aAZ|aZAZ|aBZ|bBZ|aZ

hacemos lo que es la ultima sustitución 

S -> aB|aZB|(aA|aZA|aB|bB|a)C
A -> a|aZ
B -> aA|aZA|aB|bB|a
c -> a|b
Z -> aA|aZA|aB|bB|a|aAZ|aZAZ|aBZ|bBZ|aZ


reemplazamos

S -> aB|aZB|aAC|aZAC|aBC|bBC|aC
A -> a|aZ
B -> aA|aZA|aB|bB|a
c -> a|b
Z -> aA|aZA|aB|bB|a|aAZ|aZAZ|aBZ|bBZ|aZ

la idea es ir usando las variables que ya estan en FNG para convertir a las otras variables en FNG y con esas trasformar las que faltan en FNG basicamente es eso 

veamos otro ejemplo

S -> AB
A -> AB|CB|a
B -> AB|b
C -> AC|c

la de la recursividad es A 

$\large{\alpha_1}$ = B
$\large{\beta_1}$ = a

A -> $\large{\beta_1 | \beta_2 | \dots | \beta_m | \beta_1Z | \beta_2Z | \dots | \beta_mZ}$ 
Z -> $\large{\alpha_1 | \alpha_2 | \dots | \alpha_m | \alpha_1Z | \alpha_2Z | \dots | \alpha_mZ}$  

S -> AB
A -> a|aZ
A -> CB
B -> AB|b
C -> AC|c
Z -> B|BZ

separamos a A para reemplazar solo con una de las dos en este caso lo que obtenemos al quitar la recursividad 

S -> (a|aZ)B
A -> a|aZ
A -> CB
B -> (a|aZ)B|b
C -> (a|aZ)C|c
Z -> B|BZ


S -> aB|aZB
A -> a|aZ
A -> CB
B -> aB|aZB|b
C -> aC|aZC|c
Z -> B|BZ


S -> aB|aZB
A -> a|aZ
A -> (aC|aZC|c)B
B -> aB|aZB|b
C -> aC|aZC|c
Z -> (aB|aZB|b)|(aB|aZB|b)Z

S -> aB|aZB
A -> a|aZ
A -> aCB|aZCB|cB
B -> aB|aZB|b
C -> aC|aZC|c
Z -> aB|aZB|b|aBZ|aZBZ|bZ


otro ejemplo 

S -> SC|AA|a
A -> CA|AB|a
B -> AC|b
C -> CA|AS|b

este tiene varias recursividades, empecemos con la de S 

$\large{\alpha_1}$ = C
$\large{\beta_1}$ = a

A -> $\large{\beta_1 | \beta_2 | \dots | \beta_m | \beta_1Z | \beta_2Z | \dots | \beta_mZ}$ 
Z -> $\large{\alpha_1 | \alpha_2 | \dots | \alpha_m | \alpha_1Z | \alpha_2Z | \dots | \alpha_mZ}$  

S -> a|aZ
S -> AA
A -> CA|AB|a
B -> AC|b
C -> CA|AS|b
Z -> C|CZ

ahora vamos con la de A

$\large{\alpha_1}$ = B
$\large{\beta_1}$ = a

S -> a|aZ
S -> AA
A -> a|aX
A -> CA
B -> AC|b
C -> CA|AS|b
Z -> C|CZ
X -> B|BX

ahora vamos con el de C 

$\large{\alpha_1}$ = A
$\large{\beta_1}$ = b

S -> a|aZ
S -> AA
A -> a|aX
A -> CA
B -> AC|b
C -> b|bY
C -> AS
Z -> C|CZ
X -> B|BX
Y -> A|AY

ahora a reemplazar pero no lo voy a hacer porque que pereza la verdad jejej

[[reconocimiento descendente]]
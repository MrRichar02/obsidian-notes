[[gramaticas regulares]] para volver al anterior
[[Indice teoría de lenguajes y lab]] para ir al indice

En las gramáticas regular solo podíamos tener un símbolo no terminal a la derecha, 
para las gramáticas independientes del contexto, podemos tener 0 o más símbolos no
terminales al lado derecho por ejemplo

S -> aB|bA
A -> a|aS|bAA
B -> b|bS| aBB

Las gramáticas independientes del contexto tienen los mismos 4 componentes $\large{\Sigma}$, N, 
S, P

$\large{\Sigma}$: El alfabeto que es un conjunto de símbolos terminales 

N: Un conjunto de símbolos no terminales 

S: Un símbolo no terminal conocido como el símbolo inicial 

P: Una colección de reglas de sustitución de la forma A -> w donde:

EL lenguaje generado por un GIC se denota como L(G) y se conoce como un lenguaje 
independiente del contexto (LIC). Todas las G.r son GIC por ende todo los los 
lenguajes regular son LIC 

En los GIC pueden aparecer símbolos no terminales en cualquier parte de la cadena 
pero si aparecen significa que no se ha terminado de generar la cadena 

ejm 

S -> aSb|$\large{\lambda}$ 

S -> aSb-> aaSbb-> aaaSbbb-> aaa$\large{\lambda}$bbb -> aaabbb ->* $\large{a^nb^n}$ con n >= 0 

Se pone n porque el numero de aes y de bes siempre sera el mismo 

La denominación “independiente del contexto” significa que las sustituciones 
quedarán aplicadas en las cadenas independientemente de su posición, o sea, 
independientemente de los símbolos que la rodean.

Mas ejemplos uwu

(1):
S -> aS|$\large{\lambda}$ 
S -> aS -> aaS -> aaaS -> aaa$\large{\lambda}$ -> aaa ->* a*

(2):

S -> aS|bA|$\large{\lambda}$ 
A -> bA|b|$\large{\lambda}$ 

S -> aS -> aaS -> aaaS -> aaabA -> aaabbA -> aaabb$\large{\lambda}$ -> aaabb ->* $\large{a^*b^*}$ 

Los GIC son equivalentes si generan el mismo lenguaje

Otro ejemplo 

S -> aS|aA
A -> bA|b

en este caso este GIC produce el lenguaje a⁺b⁺ porque como no esta $\large{\lambda}$ al menos una 
vez tendremos tanto a la a como la b

otro ejemplo de un ejercicio del taller 

![[Pasted image 20240913121822.png]]


[[automatas de pila]]

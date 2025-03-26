[[gramaticas independientes del contexto]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice

Este tipo de autómatas son similares a los demas que hemos trabajado, en cuanto  a
que el siguiente estado depende del símbolo de entrada, y el estado actual, solo que 
se le añade una información adicional, esta información adicional se refiere al 
símbolo en el tope de la pila. 

Este tipo de autómatas no solo cambia de estado sino que apila o desapila un símbolo
de la pila o no hace nada

Un autómata de pila se representa como una 7-tupla M = (Q, ∑, 𝛤, ∆, q0, F, z0) donde

Q: es un conjunto finito de estados
$\large{\Sigma}$: es un alfabeto de entrada
$\large{\Gamma}$: es el alfabeto de la pila 
$\large{\Delta}$: es una regla de transición
$\large{q_0 \in Q}$ es el estado inicial o de partida 
$\large{z_0 \in \Gamma }$ es el símbolo inicial de la pila 
$\large{F \subseteq Q }$ Es el conjunto de estados finales o de aceptación 

Las transiciones del autómata dependen del alfabeto y los elementos de la pila, no es 
posible un movimiento si la pila esta vacía 

Lenguaje para un autómata de pila:

se puede definir de dos maneras, la primera se refiere al conjunto de entradas que 
llevan al autómata a un estado final lo que nos deja con la siguiente expresión (M)=
{w∈Σ/(q0, w, z0) →* (p, λ, ϒ),p∈F}.  La segunda se refiere al conjunto de entradas 
que vacían la pila para este caso en la expresión anterior no es relevante F 

Nota: que el autómata tenga en el tope a z0 se considera como si estuviera vacía 

veamos un ejemplo uwu

L = $\large{\{0^n 1^n / n \geq 0 \} }$ 

S -> oS1|$\large{\lambda}$ 

S -> 0S1 -> 00S11 -> 000S111 -> 000 $\large{\lambda}$ 111 -> 000111

Antes de plantear las transiciones del autómata debemos crear una estrategia, para
nuestro ejemplo la estrategia se piensa basándonos en que debemos tener el mismo
numero de 0 y de 1, por lo que será que apilamos cada 0 en la entrada y cuando 
empiecen a llegar los 1 desapilamos 

$\large{ (q_0, 0, z_0) -> (q_1, 0z_0)}$ 

Lo anterior significa que si estamos en el estado q0, con el elemento en el tope de la 
pila z0 y nos llega un 0, voy a pasar al estado q1 y voy a apilar el 0 quedándome el 0
en el tope de la pila 

$\large{ (q_1, 0, 0) -> (q_1, 00z_0)}$ 

Lo anterior significa que  que que si estoy en q1, con 0 en el tope de la pila y  me  
llega un 0 permanezco en el estado q1 y apilo el 0 en la pila, quedándome dos 0 
en  la pila y 0 otra vez en el tope de la pila  

$\large{ (q_1, 0, 0) -> (q_1, 000z_0)}$ 

Lo anterior significa que  que que si estoy en q1, con 0 en el tope de la pila y  me  
llega un 0 permanezco en el estado q1 y apilo el 0 en la pila, quedándome tres 0 
en  la pila y 0 otra vez en el tope de la pila  

$\large{ (q_1, 1, 0) -> (q_2, 00z_0)}$ 

Lo anterior significa que si estoy en q1, con 0 en el tope de la pila y me llega un 1 
cambio al estado q2 y desapilo el elemento en el tope de la pila por lo que quedan 
dos ceros 

$\large{ (q_2, 1, 0) -> (q_2, 0z_0)}$ 

Lo anterior significa que si estoy en q2, con 0 en el tope de la pila y me llega un 1 
permanezco en q2 y desapilo el elemento en el tope de la pila por lo que queda
un cero en la pila 

$\large{ (q_2, 1, 0) -> (q_2, z_0)}$ 

Lo anterior significa que si estoy en q2, con 0 en el tope de la pila y me llega un 1 
permanezco en q2 y desapilo el elemento en el tope de la pila por lo que la pila 
queda vacía la pila y solo queda z0  

$\large{ (q_2, \lambda, z_0) -> (q_0, z_0)}$ 

Lo anterior significa que si estoy en q2, con z0 en el tope de la pila y me llega $\large{\lambda}$ 
cambio al estado q0 y como vaciamos la pila q0 se considera estado de aceptación

Nota: cuando llega el símbolo vacío $\large{\lambda}$ y la pila esta vacía decimos que la palabra es 
aceptada 

Veamos otro ejemplo owo 

L = {w2w-1/ w ∈ (0+1)* }

S -> 0S0|1S1|2

Una cadena generada por este lenguaje es 01210

La estrategia es apilar los símbolos entrantes hasta que llegue un 2 luego de esto 
desapilamos  y si al final nos queda una pila vacía es una palabra aceptada 

$\large{ (q_0, 0, z_0) -> (q_1, 0z_0)}$ 
$\large{ (q_1, 1, 0) -> (q_2, 10z_0)}$ 
$\large{ (q_2, 2, 1) -> (q_2, 10z_0)}$ 
$\large{ (q_2, 1, 1) -> (q_2, 0z_0)}$ 
$\large{ (q_2, 0, 0) -> (q_2, z_0)}$ 
$\large{ (q_2, \lambda, z_0) -> (q_0, z_0)}$ 

Se acepta la palabra 

para este ejm $\large{\Delta}$ sería lo siguiente:

$\large{ (q_0, 0, z_0) -> (q_1, 0z_0)}$ 
$\large{ (q_0, 1, z_0) -> (q_1, 1z_0)}$ 
$\large{ (q_1, 2, z_0) -> (q_2, z_0)}$ 
$\large{ (q_1, 2, 1) -> (q_2, 10z_0)}$ 
$\large{ (q_2, \lambda, z_0) -> (q_0, z_0)}$ 

una gráfica ahí que hizo el profe uwu

![[Pasted image 20240918160604.png]]


otro ejemplo bien insano mufu 

L = {ww-1/ w ∈ (0+1)* } 

S → 0S0|1S1| λ

Estrategia:

Tomar el menor numero de símbolos y asumir que la primera repetición es el centro 
de la palabra y por ende se comenzara a desapilar 

ejm una cadena para el lenguaje es 10010111101001, iniciaríamos apilando el 1 luego 
el  0 y luego como nos llega otro 0 decimos que es el centro y después pasamos a 
desapilar. En el caso de que luego de desapilar hasta vaciar la pila el siguiente 
símbolo de entrada sea $\large{\lambda}$ significa que la palabra es aceptada , en nuestro caso nos 
llega 0 entonces hacemos algo que se llama backtracking, lo que significa volver al 
estado inicial y tomar la siguiente repetición.

una forma de verlo es 

10 010111101001, donde deje el espacio seria el punto medio 
el anterior no funciona entonces hacemos backtracking
100101 11101001, este tampoco funciona entonces hacemos backtraking otra vez
1001011 1101001 en este caso si funciona entonces aceptamos la cadena 


otro ejemplo mufu 

L={w ∈{a,b}* | w, L contienen la misma cantidad de aes que de bes

bbaaaabb cadena

$\large{ (q_0, b, z_0) -> (q_1, bz_0)}$ 
$\large{ (q_1, b, b) -> (q_1, bbz_0)}$ 
$\large{ (q_1, a, b) -> (q_0, bz_0)}$ 
$\large{ (q_0, a, b) -> (q_0, z_0)}$ 
$\large{ (q_0, a, z_0) -> (q_1, az_0)}$ 
$\large{ (q_1, a, a) -> (q_1, aaz_0)}$ 
$\large{ (q_1, b, a) -> (q_0, az_0)}$ 
$\large{ (q_0, b, a) -> (q_0, z_0)}$ 
$\large{ (q_0, \lambda, z_0) -> (q_2, z_0)}$ 

la cadena es aceptada 

para este ejm $\large{\Delta}$ sería lo siguiente:

$\large{ (q_0, a, z_0) -> (q_1, az_0)}$ 
$\large{ (q_0, b, z_0) -> (q_1, bz_0)}$ 
$\large{ (q_1, a, a) -> (q_1, az_0)}$ 
$\large{ (q_1, b, b) -> (q_1, bz_0)}$ 
$\large{ (q_1, a, b) -> (q_0, z_0)}$ 
$\large{ (q_1, b, a) -> (q_0, z_0)}$ 
$\large{ (q_1, \lambda, z_0) -> (q_2, z_0)}$ 

[[arboles de derivacion y analisis sintactico]]
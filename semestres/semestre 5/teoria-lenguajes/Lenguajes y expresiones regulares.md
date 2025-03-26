[[Autómatas finitos no deterministicos]] para volver al anterior
[[Indice teoría de lenguajes y lab]] para volver al indice 


Una expresión regular se usa para representar lenguajes regulares o tipo 3, permite 
sencillez y exactitud, ademas de permitir los símbolos del alfabeto $\large{\Sigma}$, se usan los 
siguientes 

$\large{\phi}$ Para representar el lenguaje vacío (que no tiene ningún elemento)
$\large{\lambda}$ Para representar la palabra vacía 
"+" para la unión 
.: para la concatenación, aunque no se suele escribir
"*" para el cierre o estrella de kleene


La concatenación y unión de dos expresiones regulares da como resultados otra 
expresión regular 

Veamos un ejemplo:

se tiene el alfabeto $\large{\Sigma}$ ={0, 1} entonces 01 + 011 nos da como resultado el siguiente 
lenguaje L = {01, 011}.  $0^*10^*$  representa el lenguaje que tiene al menos un 1 y que 
puede tener un numero n de 0 a la derecha y un numero m de 0 a la izquierda
osea que "*" significa que puede no estar o repetirse n veces 

Veamos otro ejemplo:

Se tiene $\large{\Sigma}$ = {a, b, c} entonces (a + b)* seria todas las posibles combinaciones que 
tienen a y b por ejemplo ab, aaabb, bbaaa, etc 


Propiedades de la unión:

Asociativa	(α + β) + ϒ = α + (β + ϒ)
Conmutativa	α + β = β + α
Elemento neutro (Ф)	α + Ф = α
Idempotencia	α + α = α

Propiedades de la concatenación:

 Asociativa	(αβ)ϒ = α(βϒ)
 Distributiva respecto a la unión.	α(β + ϒ) = αβ + αϒ
 Elemento neutro (λ)	αλ = λα = α
 αФ = Ф
 No es conmutativa

Propiedades del cierre de Kleene(*):

λ* = λ
Ф* = λ
α* α* = α*
$\large{α*α = αα*}$
(α*)* = α*
α* = λ + αα*
α* = λ + α + α2 + … + αn + αn+1 α*
A⁺ = A*.A = A.A* (A⁺ se denomina clausura positiva)
La clausula positiva es igual al cierre de kleene solo que esta asegura que por lo 
menos este una vez el símbolo 

A* A* = A*
(A* )^n = A* para todo n ≥1
(A*)* = A*
A⁺ A⁺⊆ A⁺
(A⁺)* = A*
(A⁺)⁺ = A⁺
Si A y B son lenguajes sobre ∑*, entonces (A U B)* = (A*B*)*

Los lenguajes:

Se representan de una manera diferente ya que se le coloca {} a cada símbolo 
entonces, ademas las expresiones regulares se derivan de los lenguajes

por ejemplo para el lenguaje $\large{A= {b}*. { a } . { b }*}$ una expresión regular seria $\large{b*ab*}$ 

Se puede decir que las expresiones regulares son expresiones generatrices para un
lenguajes especifico 

[[automatas con trasiciónes λ]]
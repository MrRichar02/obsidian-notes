[[automatas de pila]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice 

UN árbol de derivación es algo esencial de hacer cuando estamos comprobando si una cadena pertenece a un lenguaje o no, en estos tipos de arboles los nodos son los símbolos no terminales
mientras que las hojas del árbol son los los símbolos terminales. Como se menciono anteriormente los árboles se aplican a cadenas ya hechas y no a gramáticas que pueden llevar
a construir varias cadenas, por ejemplo para 
S -> AB1AaB
A  -> aA|a
B -> bBa|b

y creamos la siguiente derivación 

S -> AB -> aAB -> aaAB -> aabBa -> aaabba para esta derivación el árbol correspondiente sería 

![[Pasted image 20240930125926.png]]

Veamos otro ejemplo en este caso para 

S -> BAa
A -> bBC|a
B -> bB|b|$\large{\lambda}$ 
C -> aB|aa

para la siguiente derivación 

S -> BAa -> bBAa -> bbBAa -> bbbAa -> bbbaa

el árbol para esta derivación sería 

![[Pasted image 20240930130517.png]]

Veamos otro ejemplo 

$\Large{\Sigma = \{0,1,+,*,(,)\}}$  

S -> S + S| S * S|(S)|0S|1S|0|1

para la siguiente derivación 

S -> S + S -> 1 + S -> 1 + (S) -> 1 + (S + S) -> 1 + (S + S * S) 1 + (1 + S * S) -> 1 + (1 + 1 * S) -> 1 + (1 + 1 * 0)

el árbol sería (creo que el profe trasformo a una S de una en un 1 pero bueno)

![[Pasted image 20240930132018.png]]

Veamos otro ejemplo

$\Large{\Sigma_T = \{ id, cte, (, ), +, -, *, /\}}$ Símbolos terminales
$\Large{\Sigma_N = \{ <expre>, <op>\}}$ Símbolos no terminales 

$\Large{S = <expre>}$ Símbolo inicial

$\Large{<expre> -> <expre><op><expre> | (<expre>) | id | cte}$ 

$\Large{<op> -> + | - | * | /}$ 

la derivación es 

$\Large{<expre> -> <expre><op><expre> -> <expre> + <expre> -> id + <expre> -> id + <expre><op><expre> -> id + <expre> * <expre> -> id +cte * <expre> -> id +cte * id}$

en este caso esta gramática es ambigua porque se pueden encontrar mas de un árbol para esta derivación 

![[Pasted image 20240930160240.png]]

para resolver la ambigüedad se añade prelación en los operadores lo que hace que nos quede

$\Large{ <termino>, <op - adt>}$ operadores de suma y resta
$\Large{<factor>, <op - mult>}$ operadores de multiplicación y división 

de ese modo las reglas de sustitución serían 

![[Pasted image 20240930163442.png]]

para esta gramática el árbol sería 

![[Pasted image 20240930163519.png]]

[[gramaticas de lenguajes de prog]]
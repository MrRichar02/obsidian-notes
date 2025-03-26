[[automatas con trasiciónes λ]] para volver al anterior 
[[Indice teoría de lenguajes y lab]] para volver al indice


Las gramáticas regulares son otra forma de representar las cadenas aceptadas por un 
lenguaje, por ejemplo para el siguiente autómata:

![[Pasted image 20240911101032.png]]

el proceso para que acepte una cadena es que vaya avanzado entre estados hasta 
llegar al de aceptación, para representarlo como una gramática regular primero 
observamos que todas las cadenas empiezan por a y luego sigue una parte final,
representamos esa parte final con E, ahora para representar esto sería 

S -> aE donde "->" significa "genera a" ahora para representar a E tomamos en cuenta
que puede tomar dos caminos el primero con las aes y la b al final y el segundo con 
las bes y la b al final, entonces nos queda que E -> A y E -> B, ya que las listas de aes 
y la lista de bes se pueden representar como A -> aA y B -> bB y para asegurar la b al 
final colocamos que tanto A como B también pueden generar a b solo

Ahora para representar estas gramáticas regulares normalmente se ponen en una 
columna y se va poniendo que puede generar cada letra, hagamos lo para el ejm 
anterior

S -> aE
E -> A
E -> B
A -> aA
A -> b
B -> bB
B -> b

Las letras mayúsculas representan una cadena final que aun no se ha generado y se 
pueden tomar sus genera a como si estuviéramos reemplazando la letra por lo que 
genera. Como se puedo observar nos toco poner algunas letras mayúsculas dos 
veces pero existe una forma de no tener que hacer esto y es haciendo uso del 
operador |  que representa "o", haciendo uso de operador nos quedaría 

S -> aE
E -> A|B
A -> aA|b
B -> bB|b

Las letras mayúsculas se conocen como símbolos no terminales ya que indican que 
que deben ser sustituidos mientras que los símbolos que pertenecen al alfabeto $\large{\Sigma}$ 
se conocen como símbolos terminales 

Una G.r tiene $\large{\Sigma}$, N, S, P

donde:

$\large{\Sigma}$: El alfabeto que es un conjunto de símbolos terminales 

N: Un conjunto de símbolos no terminales 

S: Un símbolo no terminal conocido como el símbolo inicial 

P: Una colección de reglas de sustitución de la forma A -> w donde:

A $\large{\in}$ N y w es una palabra que puede tener o no un símbolo terminal , en caso de que 
lo tenga debe aparecer a la derecha y como máximo debe ser 1 

para el ejemplo anterior estos elementos tendrían lo siguientes valores

$\large{\Sigma}$ = { a, b }
N = { S, E, A, B }
S 
P:
S -> aE
E -> A|B
A -> aA|b
B -> bB|b

[[gramaticas independientes del contexto]]
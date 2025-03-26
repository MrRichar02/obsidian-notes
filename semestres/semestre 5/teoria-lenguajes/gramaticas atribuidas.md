[[gramaticas de lenguajes de prog]] para ir al anterior
[[Indice teoría de lenguajes y lab]] para ir al indice 

Las gramáticas regulares representan características morfológicas de un lenguaje de programación, las GIC se encargan de la parte sintáctica de los lenguajes de programación 
las gramáticas recién mencionadas no son suficientes para representar el aspecto semántico de un lenguaje de programación y ahí es donde son importantes las gramáticas atribuidas

Una semántica se puede dividir en dos aspectos, el estático y el dinámico, la semántica estática se ocupa de que se cumplan las condiciones de construcción de un programa para que 
este tenga un significado correcto por ejemplo para que A <- 5 + B sea semánticamente correcta B debe admitir la operación + con el 5 y a A debe de ser posible asignarle el resultado 
la semántica dinámica se encarga de que se traduzca el significado de una construcción a un código que pueda ser ejecutado por la maquina 

Gramática atribuida:

una GIC se define como G = $\large{ \{ \Sigma_T, \Sigma_N, S, P \}}$ y una gramática atribuida se define como GA = {G, AS, FS}, donde AS se refiere a atributos y FS se refiere a funciones semánticas, se nos 
permite definir aspectos semánticos para la gramática, en estas gramáticas los símbolos pueden tener atributos referentes a su tipo y a su valor, el tipo puede ser por ejemplo 
integer, string, boolean, etc, el valor por ejemplo para un integer puede ser 250 y se representa de la siguiente manera X.tipo, X.valor para asignarles su valor se hace por ejemplo 
de la siguiente manera X.tipo = entero, X.valor = 236

Atributos heredados y atributos sintetizados

se tiene el siguiente árbol 
![[Pasted image 20241016170248.png]]

luego 
![[Pasted image 20241016170609.png]]

Se empiezan a asignar los valores y tipos desde las hojas a los padres y si existe a la misma altura otro nodo y entres estos dos hay una operación se realiza la operación, cuando la 
asignación se realiza de esta manera se conoce como gramática sintetizada o gramática S-atribuida

Ahora veamos otra situación

D -> TL
T -> int | real 
L -> L, id | id

real id1, id2, id3

D -> TL -> realL -> realL,id -> realL,id,id -> realid1,id2,id3

ahora a hacer el árbol 

![[Pasted image 20241016171914.png]]

para este caso los atributos se pasan entre hermanos o de los padres a los hijos y se conoce como gramática heredada o gramática L-atribuida, este tipo de gramática también puede operar a veces como una sintetizada, por ejemplo en el árbol anterior se empezó desde el real que esta mas a la izquierda se subió hasta T y ya luego se paso de hermano a hermano y
después de padre a hijo 

Veamos otra situación 

en este caso vamos a cambiar el real por int 

![[Pasted image 20241016172720.png]]

los números indican el orden en se van trasmitiendo los atributos 

veamos otra situación uwu 


![[Pasted image 20241016173050.png]]

![[Pasted image 20241016173342.png]]

![[Pasted image 20241016173400.png]]

en este caso el padre de 3/4 sería real porque int/int = real y se realiza de manera que sea una gramática sintetizada 




[[simplificacion de GIC]]
[[forma normal de greibach FNG]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice 

Lo primero que hay que hacer para el reconocimiento ascendente es encontrar los primeros y segundos, para hallar los primeros debemos de buscar en las reglas de sustitución de los símbolos terminales
el primer símbolo terminal al que llegan en sus reglas, osea si tenemos por ejemplo S -> aB aquí en el conjunto de los primeros de S tendríamos P(S) = {a}, para los segundos existen unas reglas con las cuales
los vamos a hallar y una forma sin reglas, primero que todo aqui vamos a mirar en las reglas de sustitución donde aparece el símbolo no terminal a evaluar, por ejemplo para evaluar T miraríamos las reglas
donde aparece T por ejemplo S -> aTb en este caso un elemento del conjunto S(T) sería b, este caso anterior sería el ideal pero hay reglas para demás casos, vamos a verlas

reglas para los siguiente 
- Los siguientes para el primer símbolo terminal que suele ser S son solamente {$}
- Si tenemos S -> $\large{\alpha}$A entonces S(A) = S(S)
- Si tenemos S -> $\large{\alpha}$B$\large{\beta}$ entonces S(B) = P($\large{\beta}$) y en el caso de que $\large{\lambda \in}$  P($\large{\beta}$), S(B) = P($\large{\beta}$) U S(S)

ya con estas reglas y la explicación de los primeros podemos encontrar los primeros y siguiente, ahora veamos unos ejemplos


S -> aBCd
B -> CB|b
C -> cc|$\large{\lambda}$ 

Primeros:

P(S) = {a}
P(B) = {b, c, $\large{\lambda}$}
P(C) = {c, $\large{\lambda}$} 

Siguientes:

S(S) = {$}
S(B) = {c, a}
S(C) = {d, b, c}

otro ejemplo uwu

S -> BC
B -> $\large{\lambda}$| m
C -> $\large{\lambda}$| s

P(S) = {m, $\large{\lambda}$}
P(B) = {m, $\large{\lambda}$}
P(C) = {s, $\large{\lambda}$} 

S(S) = {$}
S(B) = {s, m}
S(C) = {$}

otro ejemplo owo

E -> TE'
E' -> +TE|-TE|$\large{\lambda}$ 
T -> FT'
T' -> $*FT|/FT|\large{\lambda}$ 
F -> (E)|num|id

Primeros:

P(E) = {(, num, id)
P(E') = {+, -, $\large{\lambda}$)
P(T) = {(, num, id}
P(T') = {$*, /, \large{\lambda}$}
P(F) = {(, num, id}

Siguientes:

S(E) = {$, )}
S(E') = {$, )}
S(T) = {+, -, $, )}
S(T') = {+, -, $, )}
S(F) = {$*$, /, +, -, $, )}

otro ejemplo mufu

E -> T+E|T
T -> F$*$T|F
F -> a|b|(E)

P(E) = {a, b, (}
P(T) = {a, b, (}
P(F) = {a, b, (}

S(E) = {$, )}
S(T) = {+, $, )}
S(F) = {$*$, +, $, )}

ultimo ejemplo moh

E -> T+E|T
T -> F$*$T|F
F -> (E)|id|num|$\large{\lambda}$ 

P(E) = {(, id, num, $\large{\lambda}$}
P(T) = {(, id, num, $\large{\lambda}$}
P(F) = {(, id, num, $\large{\lambda}$}

S(E) = {$, )}
S(T) = {+, $, )}
S(F) = {$*$, +, $, )}

Ahora vamos a pasar al desarrollo de la tabla de análisis sintáctico LL(1)

vamos a ilustrar primero la construcción de la tabla usando un ejemplo 

GIC:

E -> TE'
E' -> +TE'|-TE'|$\large{\lambda}$
T -> FT'
T' -> $*$FT'|/FT'|$\large{\lambda}$
F -> (E)|num|id


Primeros:

P(E) = {(, num, id}
P(E') = {+, -, $\large{\lambda}$}
P(T) = {(, num, id}
P(T') = {$*$, /, $\large{\lambda}$}
P(F) = {(, num, id}

SIguiente:

S(E) = {$, )}
S(E') = {$, )}
S(T) = {+, -, $, )}
S(T') = {+, -, $, )}
S(F) = {+, /, *, -, $, )}

Para ir ubicando en la tabla en la fila de E nos dirigimos a los primeros y vemos sus elementos el primero por el que vamos a buscar es (, al observar la GIC vemos que la primera sustiución
que se hace desde E para llegar ( es TE' por lo que en el cuadro dirección (E, ( ) vamos a poner TE', para num pasa lo mismo la primera sustitución que se hace desde E es TE' por lo que 
hacemos lo mismo que con ( y finalmente pasa lo mismo con el id, ya hemos finalizado con E ahora seguimos con E', la primera sustitución que debemos hacer para llegar de E' a + es 
+TE' entonces lo ponemos en el cuadro, para - es -TE', ahora respecto al $\large{\lambda}$ debemos dirigirnos a los siguientes de E' vemos que tenemos los elementos $ y ) ahora en las posiciones (E',$) y
(E', )) vamos a colocar $\large{\lambda}$, ahora con esta lógica que hemos construido podemos finalizar la tabla 

|     | +                 | -                 | $*$    | /    | (   | )                 | num | id  | $                 |
| --- | ----------------- | ----------------- | ------ | ---- | --- | ----------------- | --- | --- | ----------------- |
| E   |                   |                   |        |      | TE' |                   | TE' | TE' |                   |
| E'  | +TE'              | -TE'              |        |      |     | $\large{\lambda}$ |     |     | $\large{\lambda}$ |
| T   |                   |                   |        |      | FT' |                   | FT' | FT' |                   |
| T'  | $\large{\lambda}$ | $\large{\lambda}$ | $*$FT' | /FT' |     | $\large{\lambda}$ |     |     | $\large{\lambda}$ |
| F   |                   |                   |        |      | (E) |                   | num | id  |                   |


ahora que construimos la tabla podemos validar cadenas con la tabla, vamos a tener dos columnas la pila y la entrada, la pila empieza con $ seguido del primer símbolo no terminal que en 
este caso es E, en la entrada va a estar la cadena la cual vamos a evaluar y al final de la cadena ponemos $, si al final tanto en pila como en entrada solo nos queda $ significa que la 
cadena es valida, para ir validando lo que hacemos es comparar el símbolo no terminal de mas a la derecha con el símbolo mas a la izquierda de la cadena, en el primer caso sería E con num
y eso lo tomamos como las coordenadas de la tabla lo que nos daría TE', entonces reemplazamos a E por el resultado pero al revés osea reemplazamos E por E'T y la cadena sigue igual,
ahora comparamos T con num lo que nos da FT' e invertido es T'F ahora comparamos a F con num lo que nos da num como solo es un símbolo al invertirlo quedaría igual, como tanto el 
símbolo que esta mas a la derecha de la pila como el que esta más a la izquierda de la entrada son iguales los podemos cancelar, ahora vamos a comparar T' con + lo que nos da como 
resultado $\large{\lambda}$ por lo que T' desaparece, ya con esta lógica podemos terminar de validar la cadena 

| pila         | entrada           |
| ------------ | ----------------- |
| $E           | num+id$*$num$     |
| $E'T         | num+id$*$num$     |
| $E'T'F       | num+id$*$num$<br> |
| $E'T'num     | num+id$*$num$<br> |
| $E'T'        | +id$*$num$        |
| $E'          | +id$*$num$        |
| $E'T+        | +id$*$num$        |
| $E'T         | id$*$num$         |
| $E'T'F       | id$*$num$         |
| $E'T'id      | id$*$num$         |
| $E'T'        | $*$num$           |
| $\$$E'T'F$*$ | $*$num$           |
| $E'T'F       | num$              |
| $E'T'num     | num$              |
| $E'T'        | $                 |
| $E'          | $                 |
| $            | $                 |

como al final tanto en la pila como en la cadena solo quedo $ la cadena es validada 

[[reconocimiento ascendente]]
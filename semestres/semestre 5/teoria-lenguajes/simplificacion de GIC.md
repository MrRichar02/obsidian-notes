[[gramaticas atribuidas]] para ir al anterior 
[[Indice teoría de lenguajes y lab]] para ir al indice 

Los arboles creados a partir de una derivación de un GIC pueden ser muy tupidos o innecesariamente profundos, por lo que es necesario encontrar una forma estándar  


el primer paso para esto es limpiar las gramáticas, lo que significa deshacerse de los símbolos y producciones inútiles.

ejem

tenemos el siguiente GIC

S -> Aa| B| D
B -> b
A -> aA| bA| B
C -> abd

En este caso partiendo de S no existe alguna derivación en la que C pueda hacer parte ya que ninguna de las demás tiene a C en sus reglas de sustitución, por otro lado D si esta incluido 
entre las reglas de sustitución pero no se especifica ninguna regla de sustitución para D por lo que también es inútil, B también es innecesario ya que se puede reemplazar por b y 
sería lo mismo, ya que vamos a eliminar a d el símbolo terminal d no va a aparecer.


Definiciones insanas:

Una variable A es terminable si en sus reglas de sustitución existe alguna forma de llegar a un símbolo terminal que no este acompañado de no terminales 

Una variable A es accesible o alcanzable si existe alguna regla de sustitución por la cual pueda llegar a ella, S es alcanzable por definición 

A es una variable inútil si no es o alcanzable o terminable 

existen algoritmos con los cuales podemos a partir de una gramática G crear una gramática G' la cual es equivalente a G pero no tiene variables inútiles 

Algoritmo para encontrar terminales 

veamos un ejemplo 

S -> ACD | bBd | ab
A -> aB | aA | C
B -> aDS | aB
C -> aCS | CB | CC
D -> bD | ba
E -> AB | aDb

TERM1 = {S} por definición 

TERM2 = {S} U {D} = {S, D} porque en la regla 5 vemos que D se puede sustituir por ba que es terminal 

TERM3 = {S, D} U {B} = {S, D, B} porque por sus reglas de sustitución puede ir a D y S que son terminales 

TERM4 = {S, D, B} U {A} = {S, D, B, A} porque según las reglas de sustitución de A este puede ir a B que es terminal 

TERM5 = {S, D, B, A} U {E} = {S, D, B, A, E}  porque según las reglas de sustitución de E este puede ir a A, B y D que son terminales

Term6 = {S, D, B, A, E} U { } = {S, D, B, A, E} no se agrego a C porque en todas sus reglas de sustitución depende de el mismo por lo que nunca sería terminal 

TERM = {S, D, B, A, E} 

Ahora eliminamos las variables que no quedaron adentro del conjunto TERM quedándonos 

S -> ACD | bBd | ab
A -> aB | aA | C
B -> aDS | aB
D -> bD | ba
E -> AB | aDb

Como C no es terminable y la eliminamos entonces debemos eliminar las reglas de sustitución que incluyan a C 

S -> bBd | ab
A -> aB | aA 
B -> aDS | aB
D -> bD | ba
E -> AB | aDb

Algoritmo para encontrar las variables alcanzables 

veamos un ejemplo

S -> aS | AaB | ACS
A -> aS | AaB | AC
B -> bB | DB | BB
C -> aDa | ABD | ab
D -> aD | DD | ab
E -> FF | aa
F -> aE | EF

ALC1 = {S} por ser la raiz

ALC2 {S} U {A} = {S, A} por la regla de sustitución de S

ALC3 = {S, A} U {B} = {S, A, B} por la regla de sustitución de S

ALC4 = {S, A, B} U {C} = {S, A, B, C} por la regla de sustitución de S

ALC5 = {S, A, B, C} U {D} = {S, A, B, C, D} por la regla de sustitución de B

ALC6 = {S, A, B, C, D} U { } = {S, A, B, C, D} ya que no existe regla que de sustitución con la cual llegar a E y por ende no existe la regla para llegar a F que ofrece E

ALC = {S, A, B, C, D}

se eliminan las variables a las que no se puede acceder y queda 

S -> aS | AaB | ACS
A -> aS | AaB | AC
B -> bB | DB | BB
C -> aDa | ABD | ab
D -> aD | DD | ab

Eliminar producciones $\Large{\lambda}$, estas producciones se refieren a una variable A que con 1 o mas sustituciones puede llegar a producir $\Large{\lambda}$ ( Nota: La única producción $\Large{\lambda}$ permitida es S)

veamos un ejemplo 

S -> AB | ACA | ab
A -> aAa | B | CD
B -> bB | bA
C -> cC | $\Large{\lambda}$ 
D -> aDc | CC | ABb

ANUL1 = {C} por la regla de sustitución de C 

ANUL2 = {C} U {D} = {C, D} por la regla de sustitución de D

ANUL3 = {C, D} U {A} = {C, D, A} por la regla de sustitución de A

ANUL4 = {C, D, A} U {} = {C, D, A}

ahora sabiendo lo anterior no vamos a eliminar los que son producciones $\Large{\lambda}$ sino que nos vamos a aprovechar de que pueden resultar en ese valor para añadir mas reglas de 
sustitución, entonces veamos sabemos que C puede llegar a ser $\Large{\lambda}$ entonces ademas vemos en sus reglas de sustitución que tiene a cC, si en este caso reemplazamos a C por $\Large{\lambda}$ y nos 
quedaría c, entonces agregamos c como otra regla de sustitución, lo que nos dejaría con 

S -> AB | ACA | ab
A -> aAa | B | CD
B -> bB | bA
C -> cC | $\Large{\lambda}$ | c 
D -> aDc | CC | ABb

Ahora sabiendo lo anterior podemos hacer lo mismo no solo en las reglas de sustitución de C sino en la de todos los símbolos no terminales, y no solo con C sino con C, D y A
lo que nos dejaría lo siguiente:

S -> AB | ACA | ab | B | CA | AA | AC | A | C
A -> aAa | B | CD | aa | C | D
B -> bB | bA | b 
C -> cC | c
D -> aDc | CC | ABb | ac | C | Bb

Nota al aplicar todas estas nuevas reglas de sustitución podemos eliminar la regla que llevaba a $\Large{\lambda}$ 

Eliminar las producciones unitarias 

Una producción unitaria es de la forma A -> B

veamos un ejemplo tenemos a 

1. S -> AS | AA | BA | $\Large{\lambda}$ 
2. A -> aA | a
3. B -> bB | bC | C
4. C -> aA | bA | B | ab

encontremos los conjuntos de variables unitarias 

UNIT1(S) = {S}
UNIT1(S) = {S} U {}
UNIT1(S) = {S}

UNIT1(A) = {A}
UNIT1(A) = {A} U {}
UNIT1(A) = {A}

UNIT1(B) = {B}
UNIT1(B) = {B} U {C}
UNIT1(B) = {B, C}

UNIT1(C) = {C}
UNIT1(C) = {C} U {B}
UNIT1(C) = {C, B}

Ahora que sabemos cuales variables son variables unitarias, en este caso en las reglas de sustitución de B tenemos una C solita y en las reglas de sustitución de C tenemos una B solita
Lo que vamos a hacer es reemplazar primero esa C en las reglas de sustitución de B por todas las reglas de sustitución de C y luego vamos a hacer el mismo reemplazo pero en las 
reglas de sustitución de C con B lo que nos deja con el siguiente resultado

1. S -> AS | AA | BA | $\Large{\lambda}$ 
2. A -> aA | a
3. B -> bB | bC | aA | bA | ab
4. C -> aA | bA |  ab | bB | bC

Algo a resaltar es que cuando estamos reemplazando si las reglas tienen una regla que lleva a solo un símbolo no terminal entonces no lo colocamos al reemplazar por eso es que no 
colocamos la regla de C o d B al reemplazar


Veamos otro ejemplo 

1. S -> ACA | CA | AA | A | C | $\Large{\lambda}$ 
2. A -> aAa | aa | B | C 
3. B -> cC | D | C 
4. C -> bC 
5. D -> aA | $\Large{\lambda}$ 

UNIT(S) = {S}
UNIT(S) = {S} U {A} = {S, A}
UNIT(S) = {S, A} U {C} = {S, A, C}
UNIT(S) = {S, A, C} U {B} = {S, A, C, B}
UNIT(S) = {S, A, C, B} U {D} = {S, A, C, B, D}
UNIT(S) = {S, A, C, B} U {} = {S, A, C, B, D}

UNIT(A) = {A} 
UNIT(A) = {A} U {B} = {A, B}
UNIT(A) = {A, B} U {C} = {A, B, C}
UNIT(A) = {A, B, C} U {D} = {A, B, C, D}
UNIT(A) = {A, B, C} U {} = {A, B, C, D}

UNIT(B) = {B}
UNIT(B) = {B} U {C} = {B, C}
UNIT(B) = {B, C} U {D} = {B, C, D}
UNIT(B) = {B, C} U {} = {B, C, D}

UNIT(C) = {C}
UNIT(C) = {C} U {} = {c}

UNIT(D) = {D}
UNIT(D) = {D} U {} = {D}

Lo que nos deja como resultado lo siguiente

1. S -> ACA | CA | AA | aAa | aa | cC | aA | $\Large{\lambda}$ | bC   
2. A -> aAa | aa | cC | aA | $\Large{\lambda}$ | bC  
3. B -> cC | aA | $\Large{\lambda}$ | bC 
4. C -> bC 
5. D -> aA | $\Large{\lambda}$ 


Para llevar un GIC a su forma estandar simplificada aplicamos primero los algoritmos para encontrar las variables terminales y alcanzables, estos dos pueden hacerse en el orden que se 
quiera luego 

[[forma normal de chomsky FNC]]
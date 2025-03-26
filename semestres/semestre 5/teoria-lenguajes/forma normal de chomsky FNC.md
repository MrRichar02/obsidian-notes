[[simplificacion de GIC]] para ir al anterior
[[Indice teoría de lenguajes y lab]] para ir al indice


Para llevar nuestro GIC a una forma FNC debemos de hacer que todas las producciones sean de la forma S -> a o que sean de la forma S -> AA(necesariamente no tienen que ser iguales 
las  de la derecha) para hacer eso primero debemos tener la GIC simplificada aplicando en orden primero los terminales luego los alcanzables luego las producciones $\large{\lambda}$  y por ultimo 
las producciones unitarias luego de esto vamos a trasformar lo que nos haya quedado en la forma FNC para esto usamos trucos como por ejemplo crear mas variables y le damos 
las reglas de sustitución que mas nos convengan para ver esto observemos los ejemplos de clase  

primer ejemplo clase forma normal de Chomsky (FNC)


En este caso no esta en FNC
S -> aB | bA
A -> a | aS | bAA
B -> b | bS | aBB

En este caso si esta en FNC

S -> aB | bA
A -> a | CS | bE
B -> b | DS | aF
C -> a 
D -> b
E -> AA
F -> BB

segundo ejemplo FNC

En este caso no esta en FNC
S -> aBA | bA | a
A -> ab | AbA
B -> b

En este caso si esta en FNC
S -> CBA | BA | C
A -> CB | DA
B -> b
C -> a
D -> AB

Tercer ejemplo mas cargado 

Dada la siguiente gramática, expresarla en FNC.

S -> AB | aBC | SBS
A -> aA | Da | C
B -> bbB | b
C -> cC | $\Large{\lambda}$ 

primero vamos a simplificar este GIC

empecemos con los terminales 


TERM1 = {B} 
TERM2 = {B} U {C} = {B, C}
TERM3 = {B, C} U {A} = {B, C, A}
TERM4 = {B, C, A} U {S} = {B, C, A, S}
TERM5 = {B, C, A, S} U {} = {B, C, A, S}

TERM = {B, C, A, S}

Ahora vamos con los alcanzables

ALC1 = {S} 
ALC2 = {S} U {A} = {S, A}
ALC3 = {S, A} U {B} = {S, A, B}
ALC4 = {S, A, B} U {C} = {S, A, B, C}
ALC5 = {S, A, B} U {} = {S, A, B, C}

ALC = {S, A, B, C}

Ahora eliminemos las producciones $\Large{\lambda}$ 

ANUL1 = {C}
ANUL2 = {C} U {A} = {C, A}
ANUL3 = {C, A} U {} = {C, A}

ANUL = {C, A}

Ahora tomemos acciones para resolver en C y en A

S -> AB | aBC | SBS | B | aB
A -> aA | C | a 
B -> bbB | b
C -> cC | c

Ahora eliminemos las producciones unitarias 

UNIT1 = {A}
UNIT2 = {A} U {S} = {A, S}
UNIT2 = {A, S} U {} = {A, S}

UNIT = {A, S}

S -> AB | aBC | SBS | bbB | b | aB
A -> aA | cC | c | a 
B -> bbB | b
C -> cC | c

Ahora esta gramática simplificada la vamos a expresar en FNC 

S -> AB | AE | FS | BD | b | AB
A -> AA | CC | c | a 
B -> BD | b
C -> CC | c
D -> BB
E -> BC
F -> SB

Cuarto ejemplo cargadito de amor 

Primero miremos los terminales 

S → aASb | BAb
A → Aa | a | λ
B → BAB | bAb
C → cCS | λ

TERM1 = {C} 
TERM2 = {C} U {A} = {C, A}
TERM3 = {C, A} U {B} = {C, A, B}
TERM4 = {C, A, B} U {S} = {C, A, B, S}
TERM5 = {C, A, B, S} U {} = {C, A, B, S}

TERM = {C, A, B, S}

Ahora miremos los alcanzables

ALC1 = {S}
ALC2 = {S} U {A} = {S, A}
ALC3 = {S, A} U {B} = {S, A, B}
ALC4 = {S, A, B} U {} = {S, A, B}

ALC = {S, A, B}

S → aASb | BAb
A → Aa | a | λ
B → BAB | bAb

Ahora eliminemos las producciones $\Large{\lambda}$ 

ANUL1 = {A}
ANUL2 = {A} U {} = {A}

ANUL = {A} U {} = {A}

S → aASb | BAb | aSb | Bb
A → Aa | a 
B → BAB | bAb | BB | bb

Ahora eliminemos las producciones unitarias 

UNIT1 = {}

UNIT = {}


Simplificado queda 

S → aASb | BAb | aSb | Bb
A → Aa | a 
B → BAB | bAb | BB | bb

Ahora que tenemos la GIC simplificada pasemosla a FNC 

S → CG | BE | CF | BD
A → AC | a 
B → HB | DE | BB | DD
C -> a
D -> b
E -> AD
F -> SD
G -> AF
H -> AB

[[forma normal de greibach FNG]]

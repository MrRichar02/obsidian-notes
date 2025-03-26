S -> id=E
E -> TE'
E' -> +TE'
E' -> $\large{\lambda}$
T -> FT'
T' -> $*$FT'
T' -> /FT'
T' -> $\large{\lambda}$
F -> (E)
F -> id
F -> num

cadena a evaluar id = id + num$*$(id + id / num)

Lo primero que vamos a hacer es agregar el estado inicial S'

S' -> S
S -> id=E
E -> TE'
E' -> +TE'
E' -> $\large{\lambda}$
T -> FT'
T' -> $*$FT'
T' -> /FT'
T' -> $\large{\lambda}$
F -> (E)
F -> id
F -> num

ahora vamos a encontrar los primeros y siguientes 

primeros:

P(S') = {id}
P(S) = {id}
P(E) = {(, id, num}
P(E') = {+, $\large{\lambda}$}
P(T) = {(, id, num}
P(T') = {$*$, /, $\large{\lambda}$}
P(F) = {(, id, num}

siguientes:

S(S') = {$}
S(S) = {$}
S(E) = {$, )}
S(E') = {$, )}
S(T) = {+, $, )}
S(T') = {+, $, )}
S(F) = {$*$, /, +, $, )}

vamos a enumerar las producciones GIC:

0. S' -> S
1. S -> id=E
2. E -> TE'
3. E' -> +TE'
4. E' -> $\large{\lambda}$
5. T -> FT'
6. T' -> $*$FT'
7. T' -> /FT'
8. T' -> $\large{\lambda}$
9. F -> (E)
10. F -> id
11. F -> num

ahora vamos a hacer las derivaciones de los estados iniciando en I0

I0:
  I1 S' -> .S
  I2 S -> .id=E

I1:
  S' -> S.
  aceptación
  $

I2:
  I3 S -> id.=E

I3:
  I4 S -> id=.E
  I5 E -> .TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num
  
I4:
  R1 S -> id=E.

I5:
  I10 E -> T.E'
  I11 E' -> .+TE'
  I12 E' -> .$\large{\lambda}$

I6:
  I13 T -> F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I7:
  I17 F -> (.E)
  I5 E -> .TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I8: 
  R10 F -> id.

I9:
  R11 F -> num.

I10:
  R2 E -> TE'.

I11:
  I18 E' -> +.TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I12:
  R4 E' -> $\large{\lambda}$.

I13:
  R5 T -> FT'.

I14:
  I19 T' -> $*$.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I15:
  I20 T' -> /.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I16:
  R8 T' -> $\large{\lambda}$.

I17:
  I21 F -> (E.)

I18:
  I22 E' -> +T.E'
  I11 E' -> .+TE'
  I12 E' -> .$\large{\lambda}$

I19:
  I23 T' -> $*$F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I20:
  I24 T' -> /F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I21:
  R9 F -> (E).

I22:
  R3 E' -> +TE'.

I23:
  R6 T' -> $*$FT'.

I24:
  R7 T' -> /FT'.



Ahora vamos a hacer la tabla de análisis de caminos de derivación:

|         | Acción | <   | <   | <                 | <   | <   | <   | <   | <   | <   | Transición | <   | <   | <   | <   | <   |
| ------- | ------ | --- | --- | ----------------- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
| Estados | id     | =   | +   | $\large{\lambda}$ | $*$ | /   | (   | )   | num | $   | S          | E   | E'  | T   | T'  | F   |
| 0       | d2     |     |     |                   |     |     |     |     |     |     | 1          |     |     |     |     |     |
| 1       |        |     |     |                   |     |     |     |     |     | acc |            |     |     |     |     |     |
| 2       |        | d3  |     |                   |     |     |     |     |     |     |            |     |     |     |     |     |
| 3       | d8     |     |     |                   |     |     | d7  |     | d9  |     |            | 3   |     | 5   |     | 6   |
| 4       |        |     |     |                   |     |     |     |     |     | R1  |            |     |     |     |     |     |
| 5       |        |     | d11 | d12               |     |     |     |     |     |     |            |     | 10  |     |     |     |
| 6       |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 13  |     |
| 7       | d8     |     |     |                   |     |     | d7  |     | d9  |     |            | 17  |     | 5   |     | 6   |
| 8       |        |     | R10 |                   | R10 | R10 |     | R10 |     | R10 |            |     |     |     |     |     |
| 9       |        |     | R11 |                   | R11 | R11 |     | R11 |     | R11 |            |     |     |     |     |     |
| 10      |        |     |     |                   |     |     |     | R2  |     | R2  |            |     |     |     |     |     |
| 11      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     | 18  |     | 6   |
| 12      |        |     |     |                   |     |     |     | R4  |     | R4  |            |     |     |     |     |     |
| 13      |        |     | R5  |                   |     |     |     | R5  |     | R5  |            |     |     |     |     |     |
| 14      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     |     |     | 19  |
| 15      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     |     |     | 20  |
| 16      |        |     | R8  |                   |     |     |     | R8  |     | R8  |            |     |     |     |     |     |
| 17      |        |     |     |                   |     |     |     | d21 |     |     |            |     |     |     |     |     |
| 18      |        |     | d11 | d12               |     |     |     |     |     |     |            |     | 22  |     |     |     |
| 19      |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 23  |     |
| 20      |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 24  |     |
| 21      |        |     | R9  |                   | R9  | R9  |     | R9  |     | R9  |            |     |     |     |     |     |
| 22      |        |     |     |                   |     |     |     | R3  |     | R3  |            |     |     |     |     |     |
| 23      |        |     | R6  |                   |     |     |     | R6  |     | R6  |            |     |     |     |     |     |
| 24      |        |     | R7  |                   |     |     |     | R7  |     | R7  |            |     |     |     |     |     |

Ahora podemos validar la cadena, para hacerlo vamos a agregar $ al final de la cadena evaluar


| Pila      | Entrada                | Acción      |
| --------- | ---------------------- | ----------- |
| 0         | id=id+num*(id+id/num)$ | d2          |
| 0id2      | =id+num*(id+id/num)$   | d3          |
| 0id2=3    | id+num*(id+id/num)$    | d8          |
| 0id2=3id8 | +num*(id+id/num)$      | R10 F -> id |
| 0id2=3F6  | +num*(id+id/num)$      |             |
|           |                        |             |
|           |                        |             |
|           |                        |             |
|           |                        |             |
|           |                        |             |
|           |                        |             |
|           |                        |             |


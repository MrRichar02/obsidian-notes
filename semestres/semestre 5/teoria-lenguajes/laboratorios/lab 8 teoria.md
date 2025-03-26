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
S(T) = {+, id, num, )}
S(T') = {+, id, num, )}
S(F) = {$*$, /,  +, id, num, )}

ahora vamos a hacer las derivaciones de los estados iniciando en I0

I0:
  I1 S' -> .S
  I2 S -> .id=E

I1 S' -> .S:
  S' -> S.
  aceptación
  $

I2 S -> .id=E:
  I3 S -> id.=E

I3 S -> id.=E:
  I4 S -> id=.E
  I5 E -> .TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

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

I4 S -> id=.E:
  R1 S -> id=E.

I5 E -> .TE':
  I10 E -> T.E'
  I11 E' -> .+TE'
  I12 E' -> .$\large{\lambda}$

I6 T -> .FT':
  I13 T -> F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I7 F -> .(E):
  I17 F -> (.E)
  I5 E -> .TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I8 F -> .id:
  R10 F -> id.

I9 F -> .num:
  R11 F -> num.

I10 E -> T.E':
  R2 E -> TE'.

I11 E' -> .+TE':
  I18 E' -> +.TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I12 E' -> .$\large{\lambda}$:
  R4 E' -> $\large{\lambda}$.

I13 T -> F.T':
  R5 T -> FT'.

I14 T' -> .$*$FT':
  I19 T' -> $*$.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I15 T' -> ./FT':
  I20 T' -> /.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I16 T' -> .$\large{\lambda}$:
  R8 T' -> $\large{\lambda}$.

I17 F -> (.E):
  I21 F -> (E.)

I18 E' -> +.TE':
  I22 E' -> +T.E'
  I11 E' -> .+TE'
  I12 E' -> .$\large{\lambda}$

I19 T' -> $*$.FT':
  I23 T' -> $*$F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I20 T' -> /.FT':
  I24 T' -> /F.T'
  I14 T' -> .$*$FT'
  I15 T' -> ./FT'
  I16 T' -> .$\large{\lambda}$

I21 F -> (E.):
  R9 F -> (E).

I22 E' -> +T.E':
  R3 E' -> +TE'.

I23 T' -> $*$F.T':
  R6 T' -> $*$FT'.

I24 T' -> /F.T':
  R7 T' -> /FT'.

Ahora vamos a hacer la tabla de análisis de caminos de derivación:

|         | Acción | <   | <   | <                 | <   | <   | <   | <   | <   | <   | Transición | <   | <   | <   | <   | <   |
| ------- | ------ | --- | --- | ----------------- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
| Estados | id     | =   | +   | $\large{\lambda}$ | $*$ | /   | (   | )   | num | $   | S          | E   | E'  | T   | T'  | F   |
| 0       | d2     |     |     |                   |     |     |     |     |     |     | 1          |     |     |     |     |     |
| 1       |        |     |     |                   |     |     |     |     |     | ACC |            |     |     |     |     |     |
| 2       |        | d3  |     |                   |     |     |     |     |     |     |            |     |     |     |     |     |
| 3       | d8     |     |     |                   |     |     | d7  |     | d9  |     |            | 4   |     | 5   |     | 6   |
| 4       |        |     |     |                   |     |     |     |     |     | R1  |            |     |     |     |     |     |
| 5       |        |     | d11 | d12               |     |     |     |     |     |     |            |     | 10  |     |     |     |
| 6       |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 13  |     |
| 7       | d8     |     |     |                   |     |     | d7  |     | d9  |     |            | 17  |     | 5   |     | 6   |
| 8       | R10    |     | R10 |                   | R10 | R10 |     | R10 |     |     |            |     |     |     |     |     |
| 9       | R11    |     | R11 |                   | R11 | R11 |     | R11 |     |     |            |     |     |     |     |     |
| 10      |        |     |     |                   |     |     |     | R2  |     | R2  |            |     |     |     |     |     |
| 11      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     | 18  |     | 6   |
| 12      |        |     |     |                   |     |     |     | R4  |     | R4  |            |     |     |     |     |     |
| 13      | R5     |     | R5  |                   |     |     |     | R5  | R5  |     |            |     |     |     |     |     |
| 14      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     |     |     | 19  |
| 15      | d8     |     |     |                   |     |     | d7  |     | d9  |     |            |     |     |     |     | 20  |
| 16      | R8     |     | R8  |                   |     |     |     | R8  | R8  |     |            |     |     |     |     |     |
| 17      |        |     |     |                   |     |     |     | d21 |     |     |            |     |     |     |     |     |
| 18      |        |     | d11 | d12               |     |     |     |     |     |     |            |     | 22  |     |     |     |
| 19      |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 23  |     |
| 20      |        |     |     | d16               | d14 | d15 |     |     |     |     |            |     |     |     | 24  |     |
| 21      | R9     |     | R9  |                   | R9  | R9  |     | R9  | R9  |     |            |     |     |     |     |     |
| 22      |        |     | R3  | R3                |     |     |     |     |     |     |            |     |     |     |     |     |
| 23      | R6     |     | R6  |                   |     |     |     | R6  | R6  |     |            |     |     |     |     |     |
| 24      | R7     |     | R7  |                   |     |     |     | R7  | R7  |     |            |     |     |     |     |     |

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



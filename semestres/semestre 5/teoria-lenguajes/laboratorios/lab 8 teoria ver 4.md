Estudiante: Ricardo Medina Herrera

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

S(S') = { $ }
S(S) = { $ }
S(E) = { $ , ) }
S(E') = { $ , ) }
S(T) = { + , $ , ) }
S(T') = { +, $ , ) }
S(F) = { $*$ , / , + , $ , ) }

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

I0:
  I1 S' -> .S
  I2 S -> .id=E

I1:
  S' -> S.
  acceptación
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
  R4 E' -> .

I6:
  I12 T -> F.T'
  I13 T' -> .$*$FT'
  I14 T' -> ./FT'
  R8 T' -> .

I7:
  I15 F -> (.E)
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
  I16 E' -> +.TE'
  I6 T -> .FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I12:
  R5 T -> FT'.

I13:
  I17 T' -> $*$.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I14:
  I18 T' -> /.FT'
  I7 F -> .(E)
  I8 F -> .id
  I9 F -> .num

I15:
  I19 F -> (E.)

I16:
  I20 E' -> +T.E'
  I11 E' -> .+TE'
  R4 E' -> .

I17:
  I21 T' -> $*$F.T'
  I13 T' -> .$*$FT'
  I14 T' -> ./FT'
  R8 T' -> .

I18:
  I22 T' -> /F.T'
  I13 T' -> .$*$FT'
  I14 T' -> ./FT'
  R8 T' -> .

I19:
  R9 F -> (E).

I20:
  R3 E' -> +TE'.

I21:
  R6 T' -> $*$FT'.

I22:
  R7 T' -> /FT'.


|         | Acción | <   | <   | <   | <   | <   | <   | <   | <   | <   | Transición | <   | <   | <   | <   | <   |
| ------- | ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
| EStados | id     | =   | +   | $*$ | /   | (   | )   | id  | num | $   | S          | E   | E'  | T   | T'  | F   |
| 0       | d2     |     |     |     |     |     |     |     |     |     | 1          |     |     |     |     |     |
| 1       |        |     |     |     |     |     |     |     |     | acc |            |     |     |     |     |     |
| 2       |        | d3  |     |     |     |     |     |     |     |     |            |     |     |     |     |     |
| 3       | d8     |     |     |     |     | d7  |     |     | d9  |     |            | 4   |     | 5   |     | 6   |
| 4       |        |     |     |     |     |     |     |     |     | R1  |            |     |     |     |     |     |
| 5       |        |     | d11 |     |     |     | R4  |     |     | R4  |            |     | 10  |     |     |     |
| 6       |        |     | R8  | d13 | d14 |     | R8  |     |     | R8  |            |     |     |     | 12  |     |
| 7       | d8     |     |     |     |     | d7  |     |     | d9  |     |            | 15  |     | 5   |     | 6   |
| 8       |        |     | R10 | R10 | R10 |     | R10 |     |     | R10 |            |     |     |     |     |     |
| 9       |        |     | R11 | R11 | R11 |     | R11 |     |     | R11 |            |     |     |     |     |     |
| 10      |        |     |     |     |     |     | R2  |     |     | R2  |            |     |     |     |     |     |
| 11      | d8     |     |     |     |     | d7  |     |     | d9  |     |            |     |     | 16  |     | 6   |
| 12      |        |     | R5  |     |     |     | R5  |     |     | R5  |            |     |     |     |     |     |
| 13      | d8     |     |     |     |     | d7  |     |     | d9  |     |            |     |     |     |     | 17  |
| 14      | d8     |     |     |     |     | d7  |     |     | d9  |     |            |     |     |     |     | 18  |
| 15      |        |     |     |     |     |     | d19 |     |     |     |            |     |     |     |     |     |
| 16      |        |     | d11 |     |     |     | R4  |     |     | R4  |            |     | 20  |     |     |     |
| 17      |        |     | R8  | d13 | d14 |     | R8  |     |     | R8  |            |     |     |     | 21  |     |
| 18      |        |     | R8  | d13 | d14 |     | R8  |     |     | R8  |            |     |     |     | 22  |     |
| 19      |        |     | R9  | R9  | R9  |     | R9  |     |     | R9  |            |     |     |     |     |     |
| 20      |        |     |     |     |     |     | R3  |     |     | R3  |            |     |     |     |     |     |
| 21      |        |     | R6  |     |     |     | R6  |     |     | R6  |            |     |     |     |     |     |
| 22      |        |     | R7  |     |     |     | R7  |     |     | R7  |            |     |     |     |     |     |

  
| Pila                                | Entrada                | Acción                      |
| ----------------------------------- | ---------------------- | --------------------------- |
| 0                                   | id=id+num*(id+id/num)$ | d2                          |
| 0id2                                | =id+num*(id+id/num)$   | d3                          |
| 0id2=3                              | id+num*(id+id/num)$    | d8                          |
| 0id2=3id8                           | +num*(id+id/num)$      | R10 F -> id                 |
| 0id2=3F6                            | +num*(id+id/num)$      | R8 T' -> $\large{\lambda}$  |
| 0id2=3F6T'12                        | +num*(id+id/num)$      | R5 T -> FT'                 |
| 0id2=3T5                            | +num*(id+id/num)$      | d11                         |
| 0id2=3T5+11                         | num*(id+id/num)$       | d9                          |
| 0id2=3T5+11num9                     | $*$(id+id/num)$        | R11 F -> num                |
| 0id2=3T5+11F6                       | $*$(id+id/num)$        | d13                         |
| 0id2=3T5+11F6*13                    | (id+id/num)$           | d7                          |
| 0id2=3T5+11F6*13(7                  | id+id/num)$            | d8                          |
| 0id2=3T5+11F6*13(7id8               | +id/num)$              | R10 F -> id                 |
| 0id2=3T5+11F6*13(7F6                | +id/num)$              | R8 T' -> $\large{\lambda}$  |
| 0id2=3T5+11F6*13(7F6T'12            | +id/num)$              | R5 T -> FT'                 |
| 0id2=3T5+11F6*13(7T5                | +id/num)$              | d11                         |
| 0id2=3T5+11F6*13(7T5+11             | id/num)$               | d8                          |
| 0id2=3T5+11F6*13(7T5+11id8          | /num)$                 | R10 F -> id                 |
| 0id2=3T5+11F6*13(7T5+11F6           | /num)$                 | d14                         |
| 0id2=3T5+11F6*13(7T5+11F6/14        | num)$                  | d9                          |
| 0id2=3T5+11F6*13(7T5+11F6/14num9    | )$                     | R11 F -> num                |
| 0id2=3T5+11F6*13(7T5+11F6/14F18     | )$                     | R8 T' -> $\large{\lambda}$  |
| 0id2=3T5+11F6*13(7T5+11F6/14F18T'22 | )$                     | R7 T' -> /FT'               |
| 0id2=3T5+11F6*13(7T5+11F6T'12       | )$                     | R5 T -> FT'                 |
| 0id2=3T5+11F6*13(7T5+11T16          | )$                     | R4  E' -> $\large{\lambda}$ |
| 0id2=3T5+11F6*13(7T5+11T16E'20      | )$                     | R3 E' -> +TE'               |
| 0id2=3T5+11F6*13(7T5E'10            | )$                     | R2 E -> TE'                 |
| 0id2=3T5+11F6*13(7E15               | )$                     | d19                         |
| 0id2=3T5+11F6*13(7E15)19            | $                      | R9 F -> (E)                 |
| 0id2=3T5+11F6*13F17                 | $                      | R8 T' -> $\large{\lambda}$  |
| 0id2=3T5+11F6*13F17T'21             | $                      | R6 T' -> $*$FT'             |
| 0id2=3T5+11F6T'12                   | $                      | R5 T -> FT'                 |
| 0id2=3T5+11T16                      | $                      | R4 E' -> $\large{\lambda}$  |
| 0id2=3T5+11T16E'20                  | $                      | R3 E' -> +TE'               |
| 0id2=3T5E'10                        | $                      | R2 E -> TE'                 |
| 0id2=3E4                            | $                      | R1 S -> id=E                |
| 0S1                                 | $                      | acc                         |

Como nos llego a acc se valida la cadena 


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

Lo primero que vamos a hacer es simplificar la GIC para retirar las producciones $\large{\lambda}$

ANUL = {T', E' }

S -> id=E
E -> TE'
E -> T
E' -> +TE'
E' -> +T
T -> FT'
T -> F
T' -> $*$FT'
T' -> $*$F
T' -> /FT'
T' -> /F
F -> (E)
F -> id
F -> num

ahora eliminemos las producciones unitarias en este caso para E -> T y T -> F

S -> id=E
E -> TE'
E -> FT'
E' -> +TE'
E' -> +T
T -> FT'
T -> TE'
T' -> $*$FT'
T' -> $*$F
T' -> /FT'
T' -> /F
F -> (E)
F -> id
F -> num

Ahora vamos a agregar el estado inicial S'

S' -> S
S -> id=E
E -> TE'
E -> FT'
E' -> +TE'
E' -> +T
T -> FT'
T -> TE'
T' -> $*$FT'
T' -> $*$F
T' -> /FT'
T' -> /F
F -> (E)
F -> id
F -> num

Ahora vamos a sacar los primeros y siguientes 

primeros:

P(S') = {id}
P(S) = {id}
P(E) = {(, id, num}
P(E') = {+}
P(T) = {(, id, num}
P(T') = {$*$, /}
P(F) = {(, id, num}

siguientes:

S(S') = {$}
S(S) = {$}
S(E) = {$, )}
S(E') = {$, )}
S(T) = {+, $, )}
S(T') = {+, $, )}
S(F) = {$*$, /, +, $, )}

vamos a enumerar las producciones del GIC

0. S' -> S
1. S -> id=E
2. E -> TE'
3. E -> FT'
4. E' -> +TE'
5. E' -> +T
6. T -> FT'
7. T -> TE'
8. T' -> $*$FT'
9. T' -> $*$F
10. T' -> /FT'
11. T' -> /F
12. F -> (E)
13. F -> id
14. F -> num

ahora vamos a hacer las derivaciones de los estados empezando en I0

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
  I6 E -> .FT'
  I7 T -> .FT'
  I8 T -> .TE'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I4:
  R1 S -> id=E.

I5:
  I12 E -> T.E'
  I13 E' -> .+TE'
  I14 E' -> .+T

I6:
  I15 E -> F.T'
  I16 T' -> .$*$FT'
  I17 T' -> .$*$F
  I18 T' -> ./FT'
  I19 T' -> ./F

I7:
  I20 T -> F.T'
  I16 T' -> .$*$FT'
  I17 T' -> .$*$F
  I18 T' -> ./FT'
  I19 T' -> ./F

I8:
  I21 T -> T.E'
  I13 E' -> .+TE'
  I14 E' -> .+T

I9: 
  I22 F -> (.E)
  I5 E -> .TE'
  I6 E -> .FT'
  I7 T -> .FT'
  I8 T -> .TE'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I10:
  R13 F -> id.

I11:
  R14 F -> num.

I12:
  R2 E -> TE'.

I13:
  I23 E' -> +.TE'
  I7 T -> .FT'
  I8 T -> .TE'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I14:
  I24 E' -> +.T
  I7 T -> .FT'
  I8 T -> .TE'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I15:
  R3 E -> FT'.

I16:
  I25 T' -> $*$.FT'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I17:
  I26 T' -> $*$.F
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I18:
  I27 T' -> /.FT'
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I19:
  I28 T' -> /.F
  I9 F -> .(E)
  I10 F -> .id
  I11 F -> .num

I20:
  R6 T -> FT'.

I21:
  R7 T -> TE'.

I22:
  I29 F -> (E.)

I23:
  I30 E' -> +T.E'
  I13 E' -> .+TE'
  I14 E' -> .+T

I24:
  R5 E' -> +T.

I25:
  I31 T' -> $*$F.T'
  I16 T' -> .$*$FT'
  I17 T' -> .$*$F
  I18 T' -> ./FT'
  I19 T' -> ./F

I26:
  R9 T' -> $*$F.

I27:
  I32 T' -> /F.T'
  I16 T' -> .$*$FT'
  I17 T' -> .$*$F
  I18 T' -> ./FT'
  I19 T' -> ./F

I28:
  R11 T' -> /F.

I29:
  R12 F -> (E).

I30:
  R4 E' -> +TE'.

I31:
  R8 T' -> $*$FT'.

I32:
  R10 T' -> /FT'.


  






  
|         | Acción | <   | <       | <        | <       | <   | <   | <   | <   | Transición | <   | <   | <    | <   | <   |
| ------- | ------ | --- | ------- | -------- | ------- | --- | --- | --- | --- | ---------- | --- | --- | ---- | --- | --- |
| Estados | id     | =   | +       | $*$      | /       | (   | )   | num | $   | S          | E   | E'  | T    | T'  | F   |
| 0       | d2     |     |         |          |         |     |     |     |     | 1          |     |     |      |     |     |
| 1       |        |     |         |          |         |     |     |     | acc |            |     |     |      |     |     |
| 2       |        | d3  |         |          |         |     |     |     |     |            |     |     |      |     |     |
| 3       | d10    |     |         |          |         | d9  |     | d11 |     |            | 4   |     | 5,8  |     | 6,7 |
| 4       |        |     |         |          |         |     |     |     | R1  |            |     |     |      |     |     |
| 5       |        |     | d13,d14 |          |         |     |     |     |     |            |     | 12  |      |     |     |
| 6       |        |     |         | d16, d17 | d18,d19 |     |     |     |     |            |     |     |      | 15  |     |
| 7       |        |     |         | d16, d17 | d18,d19 |     |     |     |     |            |     |     |      | 20  |     |
| 8       |        |     | d13,d14 |          |         |     |     |     |     |            |     | 21  |      |     |     |
| 9       | d10    |     |         |          |         | d9  |     | d11 |     |            | 22  |     | 5,8  |     | 6,7 |
| 10      |        |     | R13     | R13      | R13     |     | R13 |     | R13 |            |     |     |      |     |     |
| 11      |        |     | R14     | R14      | R14     |     | R14 |     | R14 |            |     |     |      |     |     |
| 12      |        |     |         |          |         |     | R2  |     | R2  |            |     |     |      |     |     |
| 13      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     | 23,8 |     | 7   |
| 14      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     | 24,8 |     | 7   |
| 15      |        |     |         |          |         |     | R3  |     | R3  |            |     |     |      |     |     |
| 16      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     |      |     | 25  |
| 17      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     |      |     | 26  |
| 18      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     |      |     | 27  |
| 19      | d10    |     |         |          |         | d9  |     | d11 |     |            |     |     |      |     | 28  |
| 20      |        |     | R6      |          |         |     | R6  |     | R6  |            |     |     |      |     |     |
| 21      |        |     | R7      |          |         |     | R7  |     | R7  |            |     |     |      |     |     |
| 22      |        |     |         |          |         |     | d29 |     |     |            |     |     |      |     |     |
| 23      |        |     | d13,d14 |          |         |     |     |     |     |            |     | 30  |      |     |     |
| 24      |        |     |         |          |         |     | R5  |     | R5  |            |     |     |      |     |     |
| 25      |        |     |         | d16,d17  | d18,d19 |     |     |     |     |            |     |     |      | 31  |     |
| 26      |        |     | R9      |          |         |     | R9  |     | R9  |            |     |     |      |     |     |
| 27      |        |     |         | d16,d17  | d18,d19 |     |     |     |     |            |     |     |      | 32  |     |
| 28      |        |     | R11     |          |         |     | R11 |     | R11 |            |     |     |      |     |     |
| 29      |        |     | R12     | R12      | R12     |     | R12 |     | R12 |            |     |     |      |     |     |
| 30      |        |     |         |          |         |     | R4  |     | R4  |            |     |     |      |     |     |
| 31      |        |     | R8      |          |         |     | R8  |     | R8  |            |     |     |      |     |     |
| 32      |        |     | R10     |          |         |     | R10 |     | R10 |            |     |     |      |     |     |


| Pila       | Entrada                | Acción      |
| ---------- | ---------------------- | ----------- |
| 0          | id=id+num*(id+id/num)$ | d2          |
| 0id2       | =id+num*(id+id/num)$   | d3          |
| 0id2=3     | id+num*(id+id/num)$    | d10         |
| 0id2=3id10 | +num*(id+id/num)$      | R13 F -> id |
| 0id2=3F6   | +num*(id+id/num)$      |             |
|            |                        |             |
|            |                        |             |
|            |                        |             |
|            |                        |             |
|            |                        |             |
|            |                        |             |
|            |                        |             |


  





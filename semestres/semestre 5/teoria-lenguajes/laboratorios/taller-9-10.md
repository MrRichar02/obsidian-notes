S   → var=E                      
E   → TE'
E'  → +TE'
E'  → λ
T   → FT'
T'  → $*$FT'
T'  → /FT'
T'  → λ
F   → (E)
F   → num

vamos a añadir S'

S' -> S
S   → var=E                      
E   → TE'
E'  → +TE'
E'  → λ
T   → FT'
T'  → $*$FT'
T'  → /FT'
T'  → λ
F   → (E)
F   → num

Ahora vamos a encontrar los primeros y los siguientes 

primeros:

P(S') = {var}
P(S) = {var}
P(E) = {(, num}
P(E') = {+, $\large{\lambda}$}
P(T) = {(, num}
P(T') = {$*$, /, $\large{\lambda}$}
P(F) = {(, num}

siguientes:

S(S') = {$}
S(S) = {$}
S(E) = {$, )}
S(E') = {$, ),}
S(T) = {+, $, )}
S(T') = {+, $, )}
S(F) = {$*$, /, +, $, )}


0. S' -> S
1. S   → var=E                      
2. E   → TE'
3. E'  → +TE'
4. E'  → λ
5. T   → FT'
6. T'  → $*$FT'
7. T'  → /FT'
8. T'  → λ
9. F   → (E)
10. F   → num

ahora vamos con los estados 

I0:
  I1 S' -> .S
  I2 S -> .var=E

I1:
  S' -> S.
  aceptación
  $

I2:
  I3 S -> var.=E

I3:
  I4 S -> var=.E
  I5 E   → .TE'
  I6 T   → .FT'
  I7 F   → .(E)
  I8 F   → .num

I4:
  R1 S -> var=E.

I5:
  I9 E -> T.E'
  I10 E'  → .+TE'
  R4 E'  → .

I6:
  I11 T   → F.T'
  I12 T'  → .$*$FT'
  I13 T'  → ./FT'
  R8 T'  → .

I7:
  I14 F   → (.E)
  I5 E   → .TE'
  I6 T   → .FT'
  I7 F   → .(E)
  I8 F   → .num

I8:
  R10 F   → num.

I9:
  R2 E -> TE'.

I10:
  I15 E'  → +.TE'
  I6 T   → .FT'
  I7 F   → .(E)
  I8 F   → .num

I11:
  R5 T   → FT'.

I12:
  I16 T'  → $*$.FT'
  I7 F   → .(E)
  I8 F   → .num

I13:
  I17 T'  → /.FT'
  I7 F   → .(E)
  I8 F   → .num

I14:
  I18 F   → (E.)

I15:
  I19 E'  → +T.E'
  I10 E'  → .+TE'
  R4 E'  → .

I16:
  I20 T'  → $*$F.T'
  I12 T'  → .$*$FT'
  I13 T'  → ./FT'
  R8 T'  → .

I17:
  I21 T'  → /F.T'
  I12 T'  → .$*$FT'
  I13 T'  → ./FT'
  R8 T'  → .

I18:
  R9 F   → (E).

I19:
  R3 E'  → +TE'.

I20:
  R6 T'  → $*$FT'.

I21:
  R7 T'  → /FT'.

|         | Acción | <   | <   | <   | <   | <   | <   | <   | <   | Transición | <   | <   | <   | <   | <   |
| ------- | ------ | --- | --- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
| EStados | var    | =   | +   | $*$ | /   | (   | )   | num | $   | S          | E   | E'  | T   | T'  | F   |
| 0       | d2     |     |     |     |     |     |     |     |     | 1          |     |     |     |     |     |
| 1       |        |     |     |     |     |     |     |     | acc |            |     |     |     |     |     |
| 2       |        | d3  |     |     |     |     |     |     |     |            |     |     |     |     |     |
| 3       |        |     |     |     |     | d7  |     | d8  |     |            | 4   |     | 5   |     | 6   |
| 4       |        |     |     |     |     |     |     |     | R1  |            |     |     |     |     |     |
| 5       |        |     | d10 |     |     |     | R4  |     | R4  |            |     | 9   |     |     |     |
| 6       |        |     | R8  | d12 | d13 |     | R8  |     | R8  |            |     |     |     | 11  |     |
| 7       |        |     |     |     |     | d7  |     | d8  |     |            | 14  |     | 5   |     | 6   |
| 8       |        |     | R10 | R10 | R10 |     | R10 |     | R10 |            |     |     |     |     |     |
| 9       |        |     |     |     |     |     | R2  |     | R2  |            |     |     |     |     |     |
| 10      |        |     |     |     |     | d7  |     | d8  |     |            |     |     | 15  |     | 6   |
| 11      |        |     | R5  |     |     |     | R5  |     | R5  |            |     |     |     |     |     |
| 12      |        |     |     |     |     | d7  |     | d8  |     |            |     |     |     |     | 16  |
| 13      |        |     |     |     |     | d7  |     | d8  |     |            |     |     |     |     | 17  |
| 14      |        |     |     |     |     |     | d18 |     |     |            |     |     |     |     |     |
| 15      |        |     | d10 |     |     |     | R4  |     | R4  |            |     | 19  |     |     |     |
| 16      |        |     | R8  | d12 | d13 |     | R8  |     | R8  |            |     |     |     | 20  |     |
| 17      |        |     | R8  | d12 | d13 |     | R8  |     | R8  |            |     |     |     | 21  |     |
| 18      |        |     | R9  | R9  | R9  |     | R9  |     | R9  |            |     |     |     |     |     |
| 19      |        |     |     |     |     |     | R3  |     | R3  |            |     |     |     |     |     |
| 20      |        |     | R6  |     |     |     | R6  |     | R6  |            |     |     |     |     |     |
| 21      |        |     | R7  |     |     |     | R7  |     | R7  |            |     |     |     |     |     |


| Pila                                 | Entrada                    | Acción                     |
| ------------------------------------ | -------------------------- | -------------------------- |
| 0                                    | var=num+num*(num+num/num)$ | d2                         |
| 0var2                                | =num+num*(num+num/num)$    | d3                         |
| 0var2=3                              | num+num*(num+num/num)$     | d8                         |
| 0var2=3num8                          | +num*(num+num/num)$        | R10 F -> num               |
| 0var2=3F6                            | +num*(num+num/num)$        | R8 T' -> $\large{\lambda}$ |
| 0var2=3F6T'11                        | +num*(num+num/num)$        | R5 T -> FT'                |
| 0var2=3T5                            | +num*(num+num/num)         | d10                        |
| 0var2=3T5+10                         | num*(num+num/num)$         | d8                         |
| 0var2=3T5+10num8                     | *(num+num/num)$            | R10 F -> num               |
| 0var2=3T5+10F6                       | *(num+num/num)$            | d12                        |
| 0var2=3T5+10F6*12                    | (num+num/num)$             | d7                         |
| 0var2=3T5+10F6*12(7                  | num+num/num)$              | d8                         |
| 0var2=3T5+10F6*12(7num8              | +num/num)$                 | R10 F -> num               |
| 0var2=3T5+10F6*12(7F6                | +num/num)$                 | R8 T' -> $\large{\lambda}$ |
| 0var2=3T5+10F6*12(7F6T'11            | +num/num)$                 | R5 T -> FT'                |
| 0var2=3T5+10F6*12(7T5                | +num/num)$                 | d10                        |
| 0var2=3T5+10F6*12(7T5+10             | num/num)$                  | d8                         |
| 0var2=3T5+10F6*12(7T5+10num8         | /num)$                     | R10 F -> num               |
| 0var2=3T5+10F6*12(7T5+10F6           | /num)$                     | d13                        |
| 0var2=3T5+10F6*12(7T5+10F6/13        | num)$                      | d8                         |
| 0var2=3T5+10F6*12(7T5+10F6/13num8    | )$                         | R10 F -> num               |
| 0var2=3T5+10F6*12(7T5+10F6/13F17     | )$                         | R8 T' -> $\large{\lambda}$ |
| 0var2=3T5+10F6*12(7T5+10F6/13F17T'21 | )$                         | R7 T' -> /FT'              |
| 0var2=3T5+10F6*12(7T5+10F6T'11       | )$                         | R5 T -> FT'                |
| 0var2=3T5+10F6*12(7T5+10T15          | )$                         | R4 E' -> $\large{\lambda}$ |
| 0var2=3T5+10F6*12(7T5+10T15E'19      | )$                         | R3 E' -> +TE'              |
| 0var2=3T5+10F6*12(7T5E'9             | )$                         | R2 E -> TE'                |
| 0var2=3T5+10F6*12(7E14               | )$                         | d18                        |
| 0var2=3T5+10F6*12(7E14)18            | $                          | R9 F -> (E)                |
| 0var2=3T5+10F6*12F16                 | $                          | R8 T' -> $\large{\lambda}$ |
| 0var2=3T5+10F6*12F16T'20             | $                          | R6 T' -> $*$FT'            |
| 0var2=3T5+10F6T'11                   | $                          | R5 T -> FT'                |
| 0var2=3T5+10T15                      | $                          | R4 E' -> $\large{\lambda}$ |
| 0var2=3T5+10T15E'19                  | $                          | R3 E' -> +TE'              |
| 0var2=3T5E'9                         | $                          | R2 E -> TE'                |
| 0var2=3E4                            | $                          | R1 S -> var=E              |
| 0S1                                  | $                          | acc                        |
|                                      |                            |                            |
|                                      |                            |                            |
|                                      |                            |                            |
|                                      |                            |                            |















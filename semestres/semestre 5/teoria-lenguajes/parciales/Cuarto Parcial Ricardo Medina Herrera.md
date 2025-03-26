![[Pasted image 20241129124730.png]]

Teoría de lenguajes.                                         Nombre: Ricardo Medina Herrera
Examen final 
Prof: Rubén Darió Ángel Correa.                     C.C: 1036251162
29 de noviembre de 2024


![[Pasted image 20241129180310.png]]
Se realiza el primer punto 

0. S -> E
1. E -> TE'
2. E' -> +TE'
3. E' -> $\large{\lambda}$
4. T -> FT'
5. T' -> $*$FT'
6. T' -> $\large{\lambda}$
7. F -> (E)
8. F -> id

primeros y siguientes 

P(S) = {(, id)}
P(E) = {(, id)}
P(E') = {+, $\large{\lambda}$}
P(T) = {(, id)}
P(T') = {$*$, $\large{\lambda}$}
P(F) = {(, id)}

S(S) = { $ }
S(E) = { $, ) }
S(E') = { $, ) }
S(T) = { +, $, ) }
S(T') = { +, $ , ) }
S(F) = { * , +, $ , ) }

I0:
  I1 S -> .E
  I2 E -> .TE'
  I3 T -> .FT'
  I4 F -> .(E)
  I5 F -> .id

I1:
  S -> E.
  acc

I2:
  I6 E -> T.E'
  I7 E' -> .+TE'
  R3 E' -> .

I3:
  I8 T -> F.T'
  I9 T' -> .$*$FT'
  R6 T' -> .

I4:
  I10 F -> (.E)
  I2 E -> .TE'
  I3 T -> .FT'
  I4 F -> .(E)
  I5 F -> .id

I5:
  R8 F -> id.

I6:
  R1 E -> TE'.

I7:
  I11 E' -> +.TE'
  I3 T -> .FT'
  I4 F -> .(E)
  I5 F -> .id

I8:
  R4 T -> FT'.

I9:
  I12 T' -> $*$.FT'
  I4 F -> .(E)
  I5 F -> .id

I10:
  I13 F -> (E.)

I11:
  I14 E' -> +T.E'
  I7 E' -> .+TE'
  R3 E' -> .

I12:
  I15 T' -> $*$F.T'
  I9 T' -> .$*$FT'
  R6 T' -> .

I13:
  R7 F -> (E).

I14:
  R2 E' -> +TE'.

I15:
  R5 T' -> $*$FT'.


|     | Acción | <   | <   | <   | <   | <   | Transición | <   | <   | <   | <   |
| --- | ------ | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- |
|     | +      | *   | (   | )   | id  | $   | E          | E'  | T   | T'  | F   |
| 0   |        |     | d4  |     | d5  |     | 1          |     | 2   |     | 3   |
| 1   |        |     |     |     |     | acc |            |     |     |     |     |
| 2   | d7     |     |     | R3  |     | R3  |            | 6   |     |     |     |
| 3   | R6     | d9  |     | R6  |     | R6  |            |     |     | 8   |     |
| 4   |        |     | d4  |     | d5  |     | 10         |     | 2   |     | 3   |
| 5   | R8     | R8  |     | R8  |     | R8  |            |     |     |     |     |
| 6   |        |     |     | R1  |     | R1  |            |     |     |     |     |
| 7   |        |     | d4  |     | d5  |     |            |     | 11  |     | 3   |
| 8   | R4     |     |     | R4  |     | R4  |            |     |     |     |     |
| 9   |        |     | d4  |     | d5  |     |            |     |     |     | 12  |
| 10  |        |     |     | d13 |     |     |            |     |     |     |     |
| 11  | d7     |     |     | R3  |     | R3  |            | 14  |     |     |     |
| 12  | R6     | d9  |     | R6  |     | R6  |            |     |     | 15  |     |
| 13  | R7     | R7  |     | R7  |     | R7  |            |     |     |     |     |
| 14  |        |     |     | R2  |     | R2  |            |     |     |     |     |
| 15  | R5     |     |     | R5  |     | R5  |            |     |     |     |     |



| Pila           | Entrada       | Acción                     |
| -------------- | ------------- | -------------------------- |
| 0              | (id$*$id)+id$ | d4                         |
| 0(4            | id$*$id)+id$  | d5                         |
| 0(4id5         | $*$id)+id$    | R8 F -> id                 |
| 0(4F3          | $*$id)+id$    | d9                         |
| 0(4F3*9        | id)+id$       | d5                         |
| 0(4F3*9id5     | )+id$         | R8 F -> id                 |
| 0(4F3*9F12     | )+id$         | R6 T' -> $\large{\lambda}$ |
| 0(4F3*9F12T'15 | )+id$         | R5 T' -> $*$FT'            |
| 0(4F3T'8       | )+id$         | R4 T -> FT'                |
| 0(4T2          | )+id$         | R3 E' -> $\large{\lambda}$ |
| 0(4T2E'6       | )+id$         | R1 E -> TE'                |
| 0(4E10         | )+id$         | d13                        |
| 0(4E10)13      | +id$          | R7 F -> (E)                |
| 0F3            | +id$          | R6 T' -> $\large{\lambda}$ |
| 0F3T'8         | +id$          | R4 T -> FT'                |
| 0T2            | +id$          | d7                         |
| 0T2+7          | id$           | d5                         |
| 0T2+7id5       | $             | R8 F -> id                 |
| 0T2+7F3        | $             | R6 T' -> $\large{\lambda}$ |
| 0T2+7F3T'8     | $             | R4 T -> FT'                |
| 0T2+7T11       | $             | R3 E' -> $\large{\lambda}$ |
| 0T2+7T11E'14   | $             | R2 E' -> +TE'              |
| 0T2E'6         | $             | R1 E -> TE'                |
| 0E1            | $             | acc                        |
como llegamos a acc la cadena es aceptada 
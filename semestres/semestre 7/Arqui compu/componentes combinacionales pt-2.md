[[Indice arqui de compu]] para ir al indice
[[componentes combinacionales pt-1]] para ir al anterior 

## Semisumador

Recibe en su entrada dos dígitos y retorna el resultado de la suma y el acarreo, veamos su tabla de verdad


| A   | B   | C   | S   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   | 1   | 0   | 1   |
| 1   | 0   | 0   | 1   |
| 1   | 1   | 1   | 0   |

S(A, B) = ${A \oplus B}$
C(A, B) = ${AB}$

### Sumador completo de 1 bit

Tiene tres entradas los dos dígitos y el acarreo de entrada y dos salidas el resultado y el acarreo, veamos su tabla de verdad


| A   | B   | $C_{in}$ | ${C_{out}}$ | S   |
| --- | --- | -------- | ----------- | --- |
| 0   | 0   | 0        | 0           | 0   |
| 0   | 0   | 1        | 0           | 1   |
| 0   | 1   | 0        | 0           | 1   |
| 0   | 1   | 1        | 1           | 0   |
| 1   | 0   | 0        | 0           | 1   |
| 1   | 0   | 1        | 1           | 0   |
| 1   | 1   | 0        | 1           | 0   |
| 1   | 1   | 1        | 1           | 1   |

S(${A,B,C_{in}}$) = ${A \oplus B \oplus C_{in}}$
${C_{out}}$(${A,B,C_{in}}$) = ${AB + C_{in} (A \oplus B) }$

Haciendo el diseño el full adder queda asi:
![[Pasted image 20250906221032.png]]

### Diseño de sumar de 4 bits

![[Pasted image 20250906221319.png]]

## Multiplicador

El multiplicador de un bit es la operación AND
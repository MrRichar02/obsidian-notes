[[algebra booleana pt-1]] para regresar 

### Tabla de verdad para el operador OR

| A   | B   | X = A + B |
| --- | --- | --------- |
| 0   | 0   | 0         |
| 0   | 1   | 1         |
| 1   | 0   | 1         |
| 1   | 1   | 1         |

### Tabla de verdad para el operador AND

| A   | B   | X = A . B |
| --- | --- | --------- |
| 0   | 0   | 0         |
| 0   | 1   | 0         |
| 1   | 0   | 0         |
| 1   | 1   | 1         |

### Tabla de verdad para el operador NOT(Inversión, Negación o Complemento)

| A   | X = A´ |
| --- | ------ |
| 0   | 1      |
| 1   | 0      |

### Tabla de verdad Operador NOR (NOT OR)

| A   | B   | X = (A + B)´ = ${A \downarrow B}$ |
| --- | --- | --------------------------------- |
| 0   | 0   | 1                                 |
| 0   | 1   | 0                                 |
| 1   | 0   | 0                                 |
| 1   | 1   | 0                                 |
Solo es obtenemos 1 cuando todos son 0

### Tabla de verdad operador NAND (NOT AND)

| A   | B   | X = (A . B)´ = ${A \uparrow B}$ |
| --- | --- | ------------------------------- |
| 0   | 0   | 1                               |
| 0   | 1   | 1                               |
| 1   | 0   | 1                               |
| 1   | 1   | 0                               |
Solo obtenemos 0 cuando todos son 1

### Tabla de verdad operador XOR (Exclusive OR)

| A   | B   | ${X = A \oplus B}$ |
| --- | --- | ------------------ |
| 0   | 0   | 0                  |
| 0   | 1   | 1                  |
| 1   | 0   | 1                  |
| 1   | 1   | 0                  |
Solo obtenemos 1 cuando son diferentes

### Tabla de verdad XNOR (Exclusive NOR)


| A   | B   | ${X = (A \oplus B)´ = A \odot B}$ |
| --- | --- | --------------------------------- |
| 0   | 0   | 1                                 |
| 0   | 1   | 0                                 |
| 1   | 0   | 0                                 |
| 1   | 1   | 1                                 |
Solo obtenemos 1 cuando son iguales
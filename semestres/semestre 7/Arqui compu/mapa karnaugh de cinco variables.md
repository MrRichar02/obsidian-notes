[[algebra booleana pt-3]] para volver

Tenemos la función $\large{F(v,w,x,y,z) = \sum (2,5,7,8,10,13,15,17,19,21,23,24,29,31)}$

Para simplificar esta función usando mapas de karnaugh vamos a usar dos mapas de 4 variables donde vamos a tratar las mismas variables(w,x,y,z) respecto a la v la vamos a tratar entre ambos mapas, para el primero su valor será de 0 y para el segundo su valor será de 1

creamos los mapas 

## V = 0

| yz/wx |     |        |        | w         | w         |     |
| ----- | --- | ------ | ------ | --------- | --------- | --- |
|       |     | 00     | 01     | 11        | 10        |     |
|       | 00  | $_0$ 0 | $_4$ 0 | $_{12}$ 0 | $_8$ 1    |     |
|       | 01  | $_1$ 0 | $_5$ 1 | $_{13}$ 1 | $_9$ 0    | z   |
| y     | 11  | $_3$ 0 | $_7$ 1 | $_{15}$ 1 | $_{11}$ 0 | z   |
| y     | 10  | $_2$ 1 | $_6$ 0 | $_{14}$ 0 | $_{10}$ 1 |     |
|       |     |        | x      | x         |           |     |
## V = 1

| yz/wx |     |           |           | w         | w         |     |
| ----- | --- | --------- | --------- | --------- | --------- | --- |
|       |     | 00        | 01        | 11        | 10        |     |
|       | 00  | $_{16}$ 0 | $_{20}$ 0 | $_{28}$ 0 | $_{24}$ 1 |     |
|       | 01  | $_{17}$ 1 | $_{21}$ 1 | $_{29}$ 1 | $_{25}$ 0 | z   |
| y     | 11  | $_{19}$ 1 | $_{23}$ 1 | $_{31}$ 1 | $_{27}$ 0 | z   |
| y     | 10  | $_{18}$ 0 | $_{22}$ 0 | $_{30}$ 0 | $_{26}$ 0 |     |
|       |     |           | x         | x         |           |     |

Para formar los grupos entre celdas de las dos tablas podemos imaginar que ponemos las tablas una encima de otra y para que se forme el grupo la celda debe tocar a la otra, igualmente deben ser grupos con una cantidad que sea potencia de 2

Sabiendo esto ya podemos ponernos a formar los implicantes primos 

Implicantes primos:

- v´x´yz´ casillas: 2, 10
- XZ Casillas: 5, 7, 13, 15, 21, 23, 29, 31
- v´wx´z´ casillas: 8, 10
- wx´y´z´ casillas 8, 24
- vw´z casillas: 17, 19, 21, 23

Implicantes primos esenciales:

- v´x´yz´ casillas 2, 10
- XZ Casillas: 5, 7, 13, 15, 21, 23, 29, 31
- wx´y´z´ casillas 8, 24
- vw´z casillas: 17, 19, 21, 23
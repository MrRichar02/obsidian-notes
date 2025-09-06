[[Indice arqui de compu]] para ir al indice
[[algebra booleana pt-3]] para ir al anterior

### Circuitos combinacionales

Reciben n entradas y regresan m salidas 

### Circuitos secuenciales 

Es como un circuito secuencial pero se añade una parte donde se pueden almacenar información, se llama secuencial porque en esta parte donde se puede almacenar información se van a guardar estados que van a ir siendo enviados a la entrada del circuito combinacional y luego con la salida se va a formar el nuevo estado, esto de una forma cíclica

## Bloques funcionales 

Son bloques que realizan tareas comunes, que se saben de antemano y que se reutilizan sobre los diseños 

## Procedimiento de diseño de un sistema combinacional 

- Con las especificaciones del circuito, se determinan el numero de entradas y salidas y le damos un nombre a cada uno(normalmente se usan letras del alfabeto en mayúscula)
- Construimos la tabla de verdad donde se expresen la relación entre las entradas y salidas 
- Con la tabla de verdad obtenemos la versión simplificada de la función 
- Luego dibujamos el esquema del diseño del circuito 
- Finalmente lo probamos 

## Decoder

Se especifica como n:m o nxm, aquí n son las entradas y m son las salidas, tiene una regla de que ${(m \leq 2^n )}$

Se encarga de transformar códigos validos en una única salida, gracias a que solo activa una salida se pueden usar para habilitar selectivamente componentes 

### Ejemplo decoder 2:4


| $EA_1A_0$ | $C_0$ | $C_1$ | $C_2$ | $C_3$ |
| --------- | ----- | ----- | ----- | ----- |
| 0XXX      | 0     | 0     | 0     | 0     |
| 100       | 1     | 0     | 0     | 0     |
| 101       | 0     | 1     | 0     | 0     |
| 110       | 0     | 0     | 1     | 0     |
| 111       | 0     | 0     | 0     | 1     |

Aquí la variable E se encarga de activar el componente 

## Encoder

Se especifica como m:n o mxn donde m son las enradas y n las salidas, aqui se cumple que ${m \leq 2^n}$

El encoder solo puede tener una de sus entradas activas 

### Ejemplo encoder 4:2


| ${D_3 D_2 D_1 D_0}$     | $A_1$ | $A_0$ |
| ----------------------- | ----- | ----- |
| 0001                    | 0     | 0     |
| 0010                    | 0     | 1     |
| 0100                    | 1     | 0     |
| 1000                    | 1     | 1     |
| Combinaciones restantes | X     | X     |

## Encoder con prioridad

Es un encoder que permite que más de una entrada sea 1, y decide con que entrada se queda dependiendo de la prioridad, podemos definir esta prioridad por ejemplo con de modo descendiente desde el MSB

Se añade una salida extra que indica si el código de salida es valido o no

### Ejemplo encoder con prioridad 4:2
Usamos la prioridad descendente del MSB

| ${D_3 D_2 D_1 D_0}$ | $A_1$ | $A_0$ | V   |
| ------------------- | ----- | ----- | --- |
| 0000                | X     | X     | 0   |
| 0001                | 0     | 0     | 1   |
| 001X                | 0     | 1     | 1   |
| 01XX                | 1     | 0     | 1   |
| 1XXX                | 1     | 1     | 1   |

## Demultiplexor (Demux)

Se encarga de dirigir un valor de la entrada a una salida, para esto usa algo conocido como switches, veamos un ejemplo simple donde el valor a dirigir será Y y los switches se representan con s


| ${S_1 S_0}$ | ${D_3 D_2 D_1 D_0}$ |
| ----------- | ------------------- |
| 00          | 000Y                |
| 01          | 00Y0                |
| 10          | 0Y00                |
| 11          | Y000                |

Podemos expresar el valor que van a tener las salidas de la siguiente forma 

${D_3 = Y S_1 S_0}$
${D_3 = Y S_1 S_0´}$
${D_3 = Y S_1´ S_0}$
${D_3 = Y S_1´ S_0´}$

## Multiplexor (Mux)

Se encarga de seleccionar un valor de la entrada y dirigirlo a la salida para esto se usan switches, se le conoce como selector de datos. Veamos un ejemplo


| ${S_1 S_0}$ | Y     |
| ----------- | ----- |
| 00          | $D_0$ |
| 01          | $D_1$ |
| 10          | $D_2$ |
| 11          | $D_3$ |

Para este tabla ${Y = D_3 S_1 S_0 + D_2 S_1 S_0´ + D_1 S_1´ S_0 + D_0 S_1´ S_0´}$

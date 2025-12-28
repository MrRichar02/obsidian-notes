Nombre: Ricardo Medina Herrera
CC: 1036251162

![[Pasted image 20251203080436.png]]

![[Pasted image 20251203080512.png]]

![[Pasted image 20251203080832.png]]

la instrucción actual esta en la fila 2 columna 3 (+8) y si lo pasamos a binario es lo siguiente 

00010000101000000000000000001100

dividamos el numero para obtener sus  partes

000100 00101 00000 0000000000001100

con el opcode identificamos que no es una instrucción r y al mirar su opcode en la tabla vemos que pertenece a la instrucción beq osea que es una instrucción de tipo inmediata, tenemos que rs sería el registro a1 el cual tiene un valor de de 0, el rt sería el registro zero con un valor también de 0 y finalmente el campo inmediate tiene un valor de 12

![[Pasted image 20251203082121.png]]

Se realiza una operación de resta y luego se compara si el resultado de la resta es igual a 0, finalmente la alu regresa el resultado de si es o no igual a 0

![[Pasted image 20251203082158.png]]

el valor de la salida del multiplexor será el next pc en nuestro caso estamos realizando una operación de control para ver si los dos registros tienen el mismo valor, que en este caso lo tienen entonces le sumamos el valor del campo inmediate al valor actual del pc para obtener el valor de nextpc que será lo que retorne el multiplexor, teniendo un valor actual de pc de 0x0040001c al sumarle 12 nos daría 0x400028

![[Pasted image 20251203082929.png]]
La siguiente instrucción que será ejecuta será 0x20a5fffc esto porque el valor del nextpc será sumarle 12 al actual entonces la siguiente instrucción sera como avanzar desde la actual palabra a la tercera que le sigue que en este caso observando la memoria es la que se menciono

![[Pasted image 20251203083234.png]]
![[Pasted image 20251203083405.png]]
![[Pasted image 20251203083352.png]]
![[Pasted image 20251203100500.png]]
se toma un total de 11 ciclos de reloj para completar la ejecución

![[Pasted image 20251203090306.png]]

![[Pasted image 20251203090602.png]]
Según el enunciado el procesador tendría un tamaño de palabra de 2 bytes(16 bits), entonces al cada palabra tener 2 bytes solo se necesita un offset de byte de un bit para elegir entre alguna de las dos, cada bloque tendrá 4 palabras entonces es necesario un offset de bloque de 2 bits para poder escoger entre cualquiera de las 4 palabras de un bloque, tenemos un tamaño para la cache de 16 palabras y cada bloque guarda 4 palabras eso nos daría que se tienen 4 bloques en la memoria cache, entonces se necesita un tamaño de index de 2 bits para poder escoger entre los 4 bloques, el procesador soporta direcciones de 16 bits, al restar a estos 16 bits el offset y el index nos quedan 11 bits para el tag

![[Pasted image 20251203092200.png]]

## 12422
0011000010000 110
Offset = 110
index = 00
Miss

| V   | Tag   | Data       |
| --- | ----- | ---------- |
| 1   | 0x184 | Mem[0x610] |
| 0   |       |            |
| 0   |       |            |
| 0   |       |            |
## 5200
0001010001010 000
Offset = 000
index = 10
Miss

| V   | Tag   | Data       |
| --- | ----- | ---------- |
| 1   | 0x184 | Mem[0x610] |
| 0   |       |            |
| 1   | 0xa2  | Mem[0x28a] |
| 0   |       |            |
## 12416
0011000010000 000
Offset = 000
index = 00
Hit

| V   | Tag   | Data       |
| --- | ----- | ---------- |
| 1   | 0x184 | Mem[0x610] |
| 0   |       |            |
| 1   | 0xa2  | Mem[0x28a] |
| 0   |       |            |
## 18654
0100100011011 110
Offset = 110
index = 11
Miss

| V   | Tag   | Data       |
| --- | ----- | ---------- |
| 1   | 0x184 | Mem[0x610] |
| 0   |       |            |
| 1   | 0xa2  | Mem[0x28a] |
| 1   | 0x246 | Mem[0x91b] |

![[Pasted image 20251203094648.png]]
Se realizaron cuatro accesos de los cuales tres fueron fallos, podemos calcular la tase de fallos así: 3/4 = 0.75, osea que se tuvo una tasa de fallos del 75%
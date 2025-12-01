## Localidad 

En un momento dado de un programa este realiza la mayor parte de accesos a memoria a ciertas direcciones, entonces es importante saber identificar cuales serán para mantenerlos en la cache, de esto salen los siguiente dos tipos de localidad

### Localidad temporal 

Se refiere a que es probable que es probable que se vuelva acceder a los datos recientemente accedidos, esto puede contemplar una situación como un bucle 

### Localidad espacial

Se refiere a que es probable que se acceda a los datos que están almacenados cerca en cuanto a su ubicación en la memoria con respecto a los datos recientemente accedidos. Un ejemplo de esta localidad es cuando se recorre un array

### AMAT (Average Memory Access Time)
Hit Time + (1 - h) Miss penalty

## Bloque

### Partes del bloque

El bloque se compone de un Index, bit de validez, tag y finalmente la data  

Dirección de bloque: Para obtener la dirección de bloque se le van a quitar una cantidad de bits a la dirección de byte, esta cantidad va a depender de cuantos bytes se genera una palabra en el caso de la arquitectura de 32 se forma de 4 entonces se deben quitar los 2 bits menos significativos que son los que nos permiten generar 4 combinaciones.

Index de la cache: $\large{\text{Dirección de bloque } \% \text{ \# de bloques en la cache}}$. 

Alternativa index de la cache: Tomar la dirección de bloque y usar la cantidad de bytes menos significativos que serían necesarios para representar todas las combinaciones para la cantidad de bloques, por ejemplo si se tienen 8 bloques se van a tomar los 3 bits menos significativos y el valor que nos den estos será el index

Bit de validez: Sirve para representar hay información útil en el bloque que es cuando su valor es 1 y cuando es 0 significa que no hay información relevante 

Tag: El tag representa la parte de la dirección de byte queda luego de retirar los bits menos significativos para obtener la dirección de bloque y los bits que representan la dirección de bloque, con los bits restantes podemos diferenciar entre datos que tienen la misma dirección de bloque 

### Bloque con tamaño mayor a una palabra

Cuando se tiene un bloque con un tamaño mayor a una palabra se debe de tener una forma para identificar cual palabra va ser donde se van a guardar los datos, para esto se debe de tener en cuenta el tamaño del bloque en cuanto a palabras y cuantos bits son necesarios para representar todas las posibles combinaciones según el tamaño, por ejemplo si el tamaño es de dos palabras solo se necesita un bit para representar las dos posibles combinaciones estos bits van ser bits adicionales que se toman de la dirección de byte antes de crear la dirección de bloque.
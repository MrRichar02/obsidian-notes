## Localidad 

En un momento dado de un programa este realiza la mayor parte de accesos a memoria a ciertas direcciones, entonces es importante saber identificar cuales serán para mantenerlos en la cache, de esto salen los siguiente dos tipos de localidad

### Localidad temporal 

Se refiere a que es probable que es probable que se vuelva acceder a los datos recientemente accedidos, esto puede contemplar una situación como un bucle 

### Localidad espacial

Se refiere a que es probable que se acceda a los datos que están almacenados cerca en cuanto a su ubicación en la memoria con respecto a los datos recientemente accedidos. Un ejemplo de esta localidad es cuando se recorre un array

### AMAT (Average Memory Access Time)
Hit Time + (1 - h) Miss penalty

## Partes de la cache

### Bloque

#### Partes del bloque

El bloque se compone de un Index, bit de validez, tag y finalmente la data  

Dirección de bloque: Para obtener la dirección de bloque se debe tener la dirección de byte y el tamaño de los bloques, para calcularla se toma la dirección de byte y se le quita una cantidad de bytes empezando desde los menos significativos, la cantidad de bytes a quitar serán los necesarios para cubrir un numero de combinaciones que sea igual tamaño del bloque, entonces si el tamaño del bloque es de una palabra osea que tiene 4 bytes, se necesita cubrir 4 combinaciones y para esto se necesitan 2 bits

Index de la cache: $\large{\text{Dirección de bloque } \% \text{ \# de bloques en la cache}}$. 

Alternativa index de la cache: Tomar la dirección de bloque y usar la cantidad de bytes menos significativos que serían necesarios para representar todas las combinaciones para la cantidad de bloques, por ejemplo si se tienen 8 bloques se van a tomar los 3 bits menos significativos y el valor que nos den estos será el index

Bit de validez: Sirve para representar hay información útil en el bloque que es cuando su valor es 1 y cuando es 0 significa que no hay información relevante 

Tag: El tag representa la parte de la dirección de byte queda luego de retirar los bits menos significativos para obtener la dirección de bloque y los bits que representan la dirección de bloque, con los bits restantes podemos diferenciar entre datos que tienen la misma dirección de bloque 


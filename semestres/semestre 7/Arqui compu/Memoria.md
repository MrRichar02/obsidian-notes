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

Dirección de bloque: Para calcularla debemos eliminar una cantidad de bits menos significativos a la dirección de byte, la cantidad de bits a eliminar serán la cantidad que sea necesaria para representar un numero de combinaciones igual al tamaño de un bloque en cuanto a bytes, por ejemplo si tenemos bloques de tamaño de una palabra (4 bytes) debemos tener bits suficientes para realizar 4 combinaciones, en este caso sería necesarios 2 bits, los bits necesarios se conocen como offset y se quitan para finalmente tener la dirección de bloque

Index de la cache: $\large{\text{Dirección de bloque } \% \text{ \# de bloques en la cache}}$. 

Alternativa index de la cache: Tomar la dirección de bloque y usar la cantidad de bytes menos significativos que serían necesarios para representar todas las combinaciones para la cantidad de bloques, por ejemplo si se tienen 8 bloques se van a tomar los 3 bits menos significativos y el valor que nos den estos será el index

Bit de validez: Sirve para representar hay información útil en el bloque que es cuando su valor es 1 y cuando es 0 significa que no hay información relevante 

Tag: El tag representa la parte de la dirección de byte queda luego de retirar los bits menos significativos para obtener la dirección de bloque y los bits que representan la dirección de bloque, con los bits restantes podemos diferenciar entre datos que tienen la misma dirección de bloque 

## Bloque con tamaño mayor a una palabra

Cuando un bloque tiene un tamaño mayor a una palabra se necesita una forma de elegir entre las palabras dentro del bloque para realizar la comparación de si son el dato que se busca con el tag, para hacer esto dividimos el offset en dos, los dos bits menos significativos serán el offset de byte y el resto serán el offset de bloque, con este offset de bloque es que definimos cual palabra del bloque es a la que se hace referencia. 

Veamos un ejemplo de como partir la dirección de byte para obtener las distintas partes 
![[Pasted image 20251201194814.png]]


## Tipos de caches

### Emplazamiento directo (Direct-mapped cache)
Un bloque ocupa un solo lugar de la cache

### Completamente asociativa (Fully associative)
Un bloque puede ocupar cualquier lugar de la cache por ende para verificar si un dato esta presente en la cache se deben de revisar todas las posiciones de la cache, esto suele realizarse de forma paralela pero aún así es muy costoso

### Asociativa por conjuntos de n-vías (n-way set associative)
Tenemos subconjuntos de una cantidad de bloques, para mapear un dato usamos la siguiente operación $\large{\text{dirección de bloque } \% \text{ \# conjuntos de bloques}}$ y también podemos tomar los bits menos significativos necesarios para realizar una cantidad de combinaciones iguales al tamaño de subconjuntos que se tenga en la memoria cache. Para buscar un dato que mapea a un subconjunto se revisan todos los bloques del subconjunto y si el dato no esta se puede remplazar el valor de uno de los bloques del subconjunto teniendo un criterio, el criterio puede ser remplazar el que lleva más tiempo sin ser utilizado para esto se debería de tener un conjunto de bits que pueden representar un numero de combinaciones iguales a la cantidad de bloques por subconjunto para ir clasificando los bloques, otra solución más simple es realizar el remplazo de forma aleatoria.
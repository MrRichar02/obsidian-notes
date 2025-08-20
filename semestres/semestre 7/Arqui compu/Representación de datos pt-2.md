[[Indice arqui de compu]] para ir al indice
[[Representación de datos pt-1]] para ir al anterior 

Los datos que procesa o almacena un computador están en forma binaria, en una cadena de dígitos binarios que tiene una longitud que es un  potencia de 2, ya sea 2³ = 8, 2⁴ = 16, 2⁵ = 32 o 2⁶ = 64 bits

Un dato se convierte en información cuando se realiza una interpretación de el mismo, ya que un mismo dato puede tener varias interpretaciones dependiendo del contexto en el que se encuentre, en la siguiente imagen se puden observar varias posibles interpretaciones para la cadena $\large{{10101011}_2}$ 
![[Pasted image 20250815164106.png]]

## Representación de números binarios positivos

Cuando se representa un numero positivo usando una cadena de binarios para conocer el valor del numero se emplea la técnica de conversión de binario a decimal,

por ejemplo $\large{{01110011}_2 = 115}$ 

para calcular el valor sumamos las potencias de 2 donde haya un 1

En este tipo de representación podemos tener $\large{2^n}$ números diferentes, donde n es el tamaño de la cadena y los números positivos que se pueden representar van desde 0 hasta $\large{2^n - 1}$ 

## Representación de números binarios negativos 

### Representación signo-magnitud 

En esta representación los números constan de dos partes un bit que se encarga de representar el signo y el resto de los bits que actuan como en la representación de números binarios positivos, la primera parte se conoce como signo y la otra como magnitud(de ahí el nombre xd)

El bit que representa el signo será el primero de izquierda a derecha y si es 0 significa que es positivo "+", si es 1 significa que es negativo "-"

El rango de posibles representaciones es el siguiente $\large{[-(2^{n-1} - 1), +(2^{n-1} -1)]}$ 

Un problema de esta representación es que existen dos maneras de representar el 0, por ejemplo en el caso de n = 4 podemos representarlo de la siguiente manera 

0000 = +0
1000 = -0

### Representación complemento a uno ($C_1$)

En esta representación para un numero positivo D la forma de calcular su versión negativa D' sería la siguiente 

$\large{D' = (2^n - 1) - D}$ 

Donde n es el tamaño de la cadena de dígitos binarios 

Veamos un ejemplo 

Determinar la forma negativa del número 7 en la representación complemento a uno con un n = 4

La forma de representar a 7 con un n de 4 es la siguiente $\large{{0111}_2}$ básicamente seleccionamos las potencias de 2 que al sumarlas nos den 7

Ahora realizamos la operación $\large{2^4 -1}$ que nos da 15 y en su forma binaria con n = 4 nos queda $\large{{1111}_2}$ 

Ahora realizamos la operación de resta entre binarios 

Préstamo
0 0 0

1 1 1 1
0 1 1 1

Resultado
1 0 0 0

Para saber si un numero representado en binario es negativo o positivo nos fijamos en el primer dígito de izquierda a derecha, si es 0 el número es positivo y si es 1 el número es negativo.

Para conocer el valor de un numero a decimal primero nos fijamos en si es positivo o negativo, si es positivo podemos calcular el valor sumando las potencias en las que estén los 1's. Si es negativo tendremos que pasarlo de su forma D' a su forma D invirtiendo la formula 

$\large{D = (2^n - 1) - D'}$ 

Nota: algo que sucede es que cuando un numero D se pasa a su complemento ocurre que todos los 1's de la parte de la magnitud se vuelven 0's y los 0's se vuelven 1's entonces para trasformarlo de regreso no tenemos que hacer la operación inversa siempre sino solo cambiamos los 0's por 1's y los 1's por 0's

Un problema de esta representación que tiene dos formas de representar el 0, veamos esto tomando un n = 4

las formas que tenemos para representar el 0 son 
- 1111
- 0000

### Representación complemento a dos ($C_2$)

En esta representación el signo del número también va a ser representado por el primer dígito de izquierda a derecha este dígito se conoce como el bit más significativo(MSB) si es 0 significa que el número es positivo y si es 1 significa que es negativo 

En esta representación para calcular la forma negativa de un numero D calculamos su complemento a dos $\large{D_{C_2}}$ con la siguiente formula 

$\large{D_{C_2} = ((2^n - 1) -D ) + 1 = 2^n -D}$ 

Algo a notar es que se pueden obtener resultados que sobrepasen la capacidad de representación dada por el tamaño de la cadena n, estos casos se deben de ignorar

En esta representación solo existe una forma de representar el 0, veamos esto en un ejemplo con n = 4 

0000 sería la única forma de representar el 0 

El rango de representación es el siguiente $\large{[-2^{n-1}, 2^{n-1}-1]}$

### Suma 

La suma se realiza de la misma forma que se presento antes, lo único a vigilar es que existe la posibilidad de superar el rango de los números que se pueden representar, por ejemplo si teniendo un n = 4 sumamos 5 y 6 nos pasaríamos del rango que llega hasta 7, estos casos se conocen como overflow

Las formas en que podemos detectar un overflow son las siguientes :

 - Si el bit de signo es distinto al de los demás sumandos
 - Si el bit de acarreo de salida que sale sumar los últimos bits es distinto al bit de signo del resultado de la suma 

### Resta

Al realizar la resta no debemos preocuparnos por el overflow ya que no pude suceder a menos que al aplicar la resta justo se convierta en una suma

Para realizar una resta de por ejemplo A - B, en lugar de hacerla asi directamente podemos primero aplicar el signo negativo al B y luego que sea una suma, entonces quedaría asi A + (-B) 

[[algebra booleana pt-1]] para ir al siguiente 
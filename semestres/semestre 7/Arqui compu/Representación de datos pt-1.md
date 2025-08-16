## Señales análogas y digitales 

[[Indice arqui de compu]] ir al indice

- Análogas: Adquieren valores en una escala numérica continua osea que existen una cantidad infinita de posibles valores 
- Digitales: Adquieren valores discretos (no se admiten valores intermedios) osea que existe una cantidad finita de valores 

## Proceso para pasar de análogo a digital

### Sample and hold 

Se toman muestras de la señal análoga siguiendo un periodo de tiempo, a este periodo se le conoce como sample rate y luego se almacenan todas las muestras tomadas.

Existe un teorema que dice que para recrear una función análoga en una digital sin que se pierda información el sample rate debe ser mayor a 2 veces la frecuencia máxima en la señal análoga.

Los humanos escuchan hasta el máximo de  20 kHz así que usamos este como el máximo para el teorema.

El cd tiene una sample rate de 44,1 kHz y el DVD tiene uno de 96 kHz

### Quantization  

Se asocia un valor discreto a todas las muestras tomadas, existen varios niveles de discretización que se pueden aplicar para representar el valor de esto niveles se usa la variable de resolution, esta variable se especifica en términos de bits por ejemplo con 2 bits se puede tener 4 valores distintos que son :
- 00
- 01
- 10
- 11

podemos convertir esos valores a:

- 0
- 1
- 2
- 3

Las muestras se asocian al nivel del cual estén mas cerca 

### Encoding 

Asociar un valor binario a cada una de las muestras 

## Señal binaria 

Es una señal que solo tiene dos posibles valores, normalmente se representan estos valores usando "1" y "0". Las señales binarias se pueden representar usando voltajes por ejemplo teniendo una escala de 0 voltios o 5 voltios podríamos asociar los valores entre 0 voltios  y 1.5 voltios con el  valor "0" y se conocen logic LOW, luego entre 1.5 voltios y 3.5 voltios lo tomamos como indefinido y entre 3.5 voltios y 5 voltios lo tomamos como el valor "1" y se conoce como logic HIGH 

## Señal binaria periódica 

Es una señal binaria que repite sus valores en un periodo especifico, esta señal se forma de un tren de pulsos continuos durante un intervalo de tiempo que sigue un patrón repetitivo 

Flanco de subida: Cuando la señal pasa de 0 a 1 

Flanco de bajada: Cuando la señal pasa de 1 a 0

$\large{T_H}$ = El tiempo que la señal permanece en el valor 1

$\large{T_L}$ = El tiempo que la señal permanece en el valor 0

T = $\large{T_H + T_L}$

Duty cycle (DC) = $\large{T_H / T}$

## Representación de datos 

Un dato es una representación simbólica  de una variable cualitativa o cuantitativa que se asocia al mundo real. Los datos se pueden puede tomar, procesar, almacenar, transmitir y visualizar 

Un conjunto de datos nos puede representar algo útil cuando se examina bajo un esquema bien definido 

Aunque el origen de los datos puede ser diverso estos se pueden representar con señales binarias, al utilizar esta forma de representar los datos resulta mas sencillo implementarlo en hardware electrónico utilizando un transistor como un interruptor que es controlado electricamente 

Un transistor es un dispositivo electrónico que permite tener dos estados, de conducción y no conducción, tiene tres terminal las cuales son la fuente o source, el drenaje o drain y la puerta o gate, gracias a la puerta se puede cambiar entre el estado de conducción de corriente o no conducción de corriente 

## Sistemas numéricos posicionales 

Los números se representan usando una cadena de dígitos que tienen un peso dependiendo de su posición y el valor de un numero dado es equivalente a la suma ponderada de sus dígitos 

### Forma general de un número 

$\large{d_{m-1} d_{m-2} \dots d_1 d_0 . d_{-1} d_{-2} \dots d_{-n}}$

Donde $\large{d_{m-1}}$ es el dígitos más significativo (MSD) el "." es el punto fraccionario n y m representan la cantidad de dígitos antes o después del "." y $d_{-n}$ es el dígito menos significativo (LSD)


### Obtener el valor de un numero (en decimal)

Usamos la siguiente formula 

$\Large{D = \sum_{i=-n}^{m-1} d_i r^i}$ 

Donde r es la base 

veamos un ejemplo pasando a la base r = 16, tenemos el siguiente numero $\Large{{187_{16}}}$
al aplicar la formula obtenemos lo siguiente

$\Large{D = 1*16^2 + 8*16^1 + 7*16^0}$

### Números decimales 
 
 r = 10

Dígitos: 0,1,2,3,4,5,6,7,8,9

### Números binarios 
 
 r = 2

Dígitos: 0,1

### Números octales 
 
 r = 8

Dígitos: 0,1,2,3,4,5,6,7

### Números hexadecimales 
 
 r = 16

Dígitos: 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F

## Conversión de decimal a otra base 

### Números enteros 

#### Divisiones sucesivas

Se puede usar el método de divisiones sucesivas por la otra base usando el residuo, esto se refiere a que si tenemos un numero D que esta en la base decimal  y una r a la que queremos pasar a r vamos a realizar lo siguiente 

vamos a dividir a D por r, al hacer eso vamos a obtener un cociente Q y un residuo R, este residuo va a ser el LSD del numero D transformado a la base r, ahora solo debemos repetir la división pero en lugar de D vamos a usar Q, repetimos esto hasta que el cociente sea 0 y los residuos que vaymos obteniendo van a ir formando a D en la base r y los vamos ir colocando de izquierda a derecha según los obtengamos ya que le primero que obtenemos es el LSD por lo que el ultimo será el MSD

Observemos un ejemplo 

Convertir 187 a binario 

Aquí D sería 187 y r sería 2

187/2 nos da un Q de 93 y un R de 1 que será el LSD

Ahora seguimos la división pero con el Q que obtuvimos 

93/2 nos da un Q de 46 y un R de 1

Seguimos con el ultimo Q obtenido 

46/2 nos da un Q de 23 y un R de 0

Seguimos con el ultimo Q obtenido 

23/2 nos da un Q de 11 y un R de 1

Seguimos con el ultimo Q obtenido 

11/2 nos da un Q de 5 y un R de 1

Seguimos on el ultimo Q obtenido 

5/2 nos da un Q de 2 y un R de 1

Seguimos con el ultimo Q obtenido

2/2 nos da un Q de 1 y un R de 0

al usar este ultimo Q nos daría un Q de 0 y dejamos a este Q como el ultimo residuo osea el MSD entonces nos detenmos, ahora podemos formar a D en la base R juntando los residuos obtenidos desde el primero hasta el ultimo de izquierda a derecha, lo que nos daría lo siguiente 

$\Large{{10111011}_2}$

#### Restas sucesivas de potencias de la otra base

Para este método vamos a usar las potencias de la base para ir restando el numero D que deseamos transformar hasta obtener 0, veamos un ejemplo 

convertir 210 a binario

para este caso nuestro D será 210 y r será 2

primero debemos observar cual es la mayor potencia de 2 que no es mayor que 210, en este caso es 2⁷ que es igual a 128 ya que 2⁸ es mayor que 210

al aplicar la resta nos queda 82, entonces nuevamente buscamos la mayor potencia de 2 que no sea mayor a 82, en este caso es 2⁶ que es 64

luego de restar nos queda 18, nuevamente buscamos la base y en este caso es 2⁴

luego de restar nos queda 2, buscamos la base que es 2¹ y al restar nos va a quedar 0

Ahora para formar el numero en binario lo que vamos a hacer es marcar cada base que usamos al restar desde la primera que usamos que en este caso fue 2⁷ hasta la base 2⁰ con 1 y las que no usamos las marcamos con 0, lo que nos daría el siguiente numero 

$\large{{11010010}_2}$

Una forma sencilla de  crear el numero es crear una tabla e ir marcando las potencias que se han utilizado 

| 2⁷ = 128 | 2⁶ = 64 | 2⁵ = 32 | 2⁴ = 16 | 2³ = 8 | 2² = 4 | 2¹ = 2 | 2⁰ = 1 |
| -------- | ------- | ------- | ------- | ------ | ------ | ------ | ------ |
| 1        | 1       | 0       | 1       | 0      | 0      | 1      | 0      |

#### Conversión de binario a hexadecimal 

Primero vamos a tomar el numero binario D a transformar y vamos a juntar sus dígitos de 4, luego con esos 4 dígitos vamos a calcular cual sería su valor en hexadecimal usando su posición para aplicar el valor de una potencia de 2 donde las potencias inician de derecha a izquierda de 2⁰ hasta 2³, luego sumamos los valores de las potencias y ahí obtenemos su equivalente en hexadecimal

veamos un ejemplo 

convertir $\large{{1001101000100101100}_2}$ a hexadecimal 

empezamos a crear los grupos iniciando de derecha a izquierda

100 1101 0001 0010 1100

el ultimo grupo nos queda solo con 3 dígitos entonces agregamos un 0 a la izquierda

0100 | 1101 | 0001 | 0010 | 1100

ahora calculamos los valores con las potencias de 2 

2² | 2³ + 2² + 2⁰ | 2⁰ | 2¹ | 2³ + 2² 

Ahora realizamos la suma e asignamos los valores correspondientes de la base hexadecimal

4 | D | 1 | 2 | C

Ya podemos quitar los separadores y dejar el numero, el cual podemos representar de dos formas 

Primera forma: $\large{{4D12C}_{16}}$

Segunda forma: $\large{ox4D12C}$

#### Conversión de binario a octal

Sería igual a lo anterior pero en lugar de formar grupos de 4 dígitos se forman  grupos de 3

## Suma de números binarios 

Para realizar la suma nos podemos ayudar de una tabla de verdad que tienen en cuenta los 8 casos posibles para las 3 variables(2 sumandos y el posible acarreo)

En la siguiente tabla:

- X y Y son los sumandos
- $\large{C_{in}}$ es el acarreo que hay para ese suma
- $\large{C_{out}}$ es el acarreo que resulta de la suma
- S es el resultado de la suma

| X   | Y   | $\large{C_{in}}$ | $\large{C_{out}}$ | S   |
| --- | --- | ---------------- | ----------------- | --- |
| 0   | 0   | 0                | 0                 | 0   |
| 0   | 0   | 1                | 0                 | 1   |
| 0   | 1   | 0                | 0                 | 1   |
| 0   | 1   | 1                | 1                 | 0   |
| 1   | 0   | 0                | 0                 | 1   |
| 1   | 0   | 1                | 1                 | 0   |
| 1   | 1   | 0                | 1                 | 0   |
| 1   | 1   | 1                | 1                 | 1   |

Ahora realicemos un ejemplo

Realizar la suma 

1 0 1 1 1 0 1 0 0 1 +
0 1 1 0 0 1 1 0 1 0

Vamos a ir realizando la suma de derecha a izquierda e ir colocando el acarreo 
Acarreo
1 1 1 1 1 1 0 0 0 

1 0 1 1 1 0 1 0 0 1 +
0 1 1 0 0 1 1 0 1 0

Resultado
1 0 0 1 0 0 0 0 0 1 1

El resultado tiene un dígito más 

## Sustracción de números binarios 

Para realizar la sustracción podemos hacer uso de la siguiente tabla de verdad que tiene en cuenta los 8 casos para las 3 variables(minuendo, sustraendo y préstamo)

- X y Y son el minuendo y sustraendo respectivamente 
- $\large{b_{in}}$ es el préstamo de entrada entregado por el siguiente dígito 
- $\large{b_{out}}$ es el préstamo de salida  que resulta de la resta anterior 
- d es el resultado de la resta

| X   | Y   | $\large{b_{in}}$ | $\large{b_{out}}$ | S   |
| --- | --- | ---------------- | ----------------- | --- |
| 0   | 0   | 0                | 0                 | 0   |
| 0   | 0   | 1                | 1                 | 1   |
| 0   | 1   | 0                | 1                 | 1   |
| 0   | 1   | 1                | 1                 | 0   |
| 1   | 0   | 0                | 0                 | 1   |
| 1   | 0   | 1                | 0                 | 0   |
| 1   | 1   | 0                | 0                 | 0   |
| 1   | 1   | 1                | 1                 | 1   |

Realicemos un ejemplo 

Restar 

1 0 1 0 1 0 0 0 0 1
0 1 1 1 0 0 0 0 0 0

| Préstamo  | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |     |
| --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| X         | 1   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 1   |
| y         | 0   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |
| Resultado | 0   | 0   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 1   |

[[Representación de datos pt-2]] para ir al proximo
## variables 

Para crear una variable primero colocamos el tipo, luego el nombre de la variable, después `=` y el valor que deseamos asignarle 

```
int number = 0;
```

### var

podemos usar la palabra reservada `var` para hacer que el compilador decida el tipo de nuestra variable dependiendo del valor que le pasemos 

```
var message = "Hello world!";
var path = Path.of("debug.log");
var stream = Files.newInputStream(path);
```

`var` solo puede ser usada para variables locales, adentro de métodos o constructores, el valor que le pasemos debe ser diferente de null 

## Arrays

Para crear arrays ponemos el tipo de los datos los cuales se almacenaran en el array y luego `[]` esto para declarar la variable, luego cuando le asignemos un valor vamos a usar new y lo mismo de la 
declaración solo que ahora entre los corchetes debemos de colocar el tamaño del array

```
int[] myarray;
myarray = new int[10];
```

para acceder o definir los valores en alguna posición del array usamos la sintaxis de poner el nombre del array, luego corchetes y entre estos la posición del item que deseamos

```
myarray[0];
```

si usamos llaves podemos definir de otras maneras los valores de un array 

```
myarray = {
  100, 200, 300,
  200, 200, 200,
  102, 103, 104, 45
};
```

### Arrays de multiples dimensiones

Las dimensiones de un array están definidas por el numero de pares de corchetes que tenga, osea que por ejemplo con 2 pares podríamos hacer una matriz
```
String[][] names;
```

podemos usar la misma sintaxis de llaves con arrays de varías dimensiones 

```
String[][] names = {
  {"Mr. ", "Mrs. ", "Ms. "},
  {"Smith", "Jones"}
};
```

### Tamaño de un array 

Para obtener el tamaño de un array podemos usar una propiedad de los arrays llamada length, para acceder a ella usamos un punto y luego escribimos length

```
myarray.legth
```

## Copiar un array

para copiar un array podemos usar una método que nos provee la clase `System` llamada `arraycopy` para acceder a ella haremos esto `System.arraycopy()`, esta método toma 4 parámetros primero 
el array del cual vamos a hacer la copia, segundo la posición del primer array desde la cual deseamos empezar la copia, luego el array que va a almacenar la copia y por ultimo el tamaño del segundo 
array

```
class ArrayCopyDemo {
    public static void main(String[] args) {
        String[] copyFrom = {
            "Affogato", "Americano", "Cappuccino", "Corretto", "Cortado",
            "Doppio", "Espresso", "Frappucino", "Freddo", "Lungo", "Macchiato",
            "Marocchino", "Ristretto" };

        String[] copyTo = new String[7];
        System.arraycopy(copyFrom, 2, copyTo, 0, 7);
        for (String coffee : copyTo) {
            System.out.print(coffee + " ");
        }
    }
}
```

también podríamos hacer la misma tarea de copiar un array usando un método de la clase `java.util.arrays` llamado `copyOnRange` este método recibe tres parámetros, el primero es el array que 
deseamos copiar, el segundo es la posición de este array desde la cual empezaremos a copiar y el tercero es la posición del array hasta la cual va a llegar la copia sin incluir esa posición 

```
class ArrayCopyOfDemo {
    public static void main(String[] args) {
        String[] copyFrom = {
            "Affogato", "Americano", "Cappuccino", "Corretto", "Cortado",
            "Doppio", "Espresso", "Frappucino", "Freddo", "Lungo", "Macchiato",
            "Marocchino", "Ristretto" };

        String[] copyTo = java.util.Arrays.copyOfRange(copyFrom, 2, 9);
        for (String coffee : copyTo) {
            System.out.print(coffee + " ");
        }
    }
}
```

### Métodos tesos de java.util.arrays

#### binarysearch:

nos permite buscar un elemento en un array y nos regresa la posición en la que este esta 

#### equals:

nos permite comparar si dos arrays son iguales o no

#### fill:

nos permite asignar un valor a todos los indices de un array

#### sort:

nos permite ordenar un array de forma ascendente 

#### parallelSort:

nos permite ordenar un array de forma ascendente de manera paralela 

#### stream :

nos permite crear una corriente de datos usando como fuente un array

#### toString:

nos permite transformar un array a un string, para esto toma cada elemento los separa entre ellos usando comas y los encierra entre corchetes 


## Operadores:

### operaciones matematicas:

### +, -, $*$, /, % :

son iguales a los demás lenguajes

### ++, --:

añadir uno al valor o reducir 1 

### !:

Invertir el valor de un boolean 

### operaciones condicionales :

### $==$, !=, >, <, >=, <=:

son iguales que los demás lenguajes 

#### ^:

va comparando uno a uno los bits de ambos lados regresa 1 si ambos bits son iguales y 0 si son diferentes

#### & :

va comprobando uno a uno los bits de ambos lados, regresa 1 si ambos bits son 1 y 0 si alguno es 0 

#### | :

va comprobando uno a no los bits de ambos lados, regresa 1 si uno de los dos bits es 1 y 0 si ambos son 0 

#### &&:

Es el and de las comparaciones

#### ||:

Es el or de las comparaciones 


## Condicionales:

### if:

para hacer un if primero ponemos la palabra `if` luego entre paréntesis ponemos la condición a evaluar y luego abrimos llaves y ponemos entre ellas lo que deseamos que se ejecute si la condición es 
true

### else:

podemos agregar un `else` al final de un `if` para hacerlo justo después de la llave de cierre de el `if` ponemos `else` y abrimos otro par de llaves, dentro de ellas ponemos lo que queremos que se 
ejecute

## Bucles:

### while

para hacer este bucle empezamos colocando `while` luego la condición que se debe cumplir entre paréntesis y después abrimos un par de llaves adentro de ellas estará el código que deseamos que se
ejecute mientras la condición es true

### do while:

para este tipo de bucles comenzamos poniendo do luego abrimos un par de llaves y entre ellas ponemos el código a ejecutar en el bucle luego ponemos while después de la segunda llave `}` y entre 
paréntesis la condición a evaluar, la diferencia con el `while` es que este ejecutara el código como mínimo una vez

### for:

para este tipo de bucles primero ponemos `for` luego entre paréntesis empezamos primero con una declaración, luego separamos con un `;`  y seguimos con la condición a evaluar luego agregamos 
otro `;` y ponemos lo que se va a ejecutar cada vez que ocurra un bucle luego colocamos un par de llaves y entre ellas el código del bucle, los parámetros que el for recibe en los paréntesis son 
opcionales y se pueden dejar vacíos uno o todos.

### for each:

un `for each` es igual a un `for` en todo menos en como son los paréntesis ya que primero vamos a declarar una variable que va a ir almacenando los valores de lo que vamos a loopear luego 
separamos  con `:` y al otro lado ponemos lo que vamos a loopear 

### break:

esta palabra reservada nos permite terminar un bucle

### continue:

esta palabra reservada nos permite continuar con el siguiente ciclo 

### return:

esta palabra reservada termina el método actual y retorna la información especificada a donde fue llamado el método, un `return` también puede estar vacío lo que hacer que no retorne algo 


## switch

un `switch` nos permite tener varias condiciones para una variable dependiendo de su valor, para hacer un `switch` ponemos `switch` luego entre paréntesis la variable a evaluar, luego abrimos 
un par de llaves, dentro de estas vamos a poner los casos para hacer un caso ponemos `case` luego el valor que vamos a ver si tiene la variable después ponemos `:` y luego de estos ponemos lo que deseamos que se ejecute si se cumple el caso y luego al final del caso ponemos un `break`. Podemos colocar un caso por defecto por si ningún otro se cumple para eso en lugar de poner `case` 
ponemos `default` luego los `:` y lo que deseamos que se ejecute, este no necesita el `break`

Si no colocamos el `break` en la lógica de cada case el `switch` seguirá evaluando los demás casos aunque haya encontrado una coincidencia 

Si queremos que para varios casos se haga lo mismo podemos acoplarlos colocando cada uno después de los `:` y terminando con un ultimo `:` y luego la lógica 
```
case 1: case 3: case 5:
```

existe otra manera de escribir `switches` que tengan lógica corta que asignan el valor a una variable, para esto primero vamos declarar la variable con su tipo y nombre luego el `=`, después `switch`, 
luego entre paréntesis la variable a evaluar en el `switch` y abrimos un par de llaves, entre ella definimos cada caso para eso empezamos con `case` luego el valor o valores, si son varios lo debemos 
separar con coma luego ponemos `->` y el valor que se asignaría a la variable para ese caso
### yield:

es similar al return pero para switches y siempre debe tener una expresión que produzca un valor luego de invocarlo 
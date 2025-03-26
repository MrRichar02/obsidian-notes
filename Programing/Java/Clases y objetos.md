## Clases  

### crear una clase

para crear una clase empezamos definiendo si es public o private, luego colocamos `class`, después el nombre que le queremos dar, luego podemos añadir si esta clase hereda de otra o esta 
implementando  alguna interfaz o varias interfaces(en este caso las debemos separar con comas) y finalmente añadimos un par de llaves, dentro de estas llaves estará todo la lógica que utilizará la 
clase 

NOTA: el nombre de una clase siempre comienza con una mayúscula como buena practica 

### Fields

Los fields son variables declaradas dentro de una clase pero no en un método, normalmente antes de definir estas variables decidimos si son public o private y luego ya la declaramos como cualquier 
otra variable 

#### static blocks

para predefinir fields con lógica un poco compleja podemos usar un static block para eso primero declaramos el nombre y tipo del field static luego en otra linea ponemos `static` luego un par de 
llaves y adentro hacemos la lógica para definir el field static 

una alternativa a estos static blocks es utilizar métodos con los modificadores private y static, en este método iría la lógica para definir el filed y tiene la ventaja de que podemos reutilizar el método

### Modificadores

los modificadores se encargan de definir el acceso a variables, clases o métodos por parte de las demás clases

#### Public

lo que sea definido como public estará disponible para todas las clases en cualquier paquete

#### Private

lo que sea definido como private estará disponible solo en la clase donde se definio

#### Protected 

lo que sea definidos como private estará disponible en la clase donde es definido, en el paquete donde esta esa clase y para las sub clases que hereden de la clase donde fue definido

#### Static

static es un modificador especial, ya que se encarga de definir fields y métodos globales para todos los objetos de una clase, normalmente static es el segundo modificador que agregamos si es que
tenemos otro, para acceder a una field static usamos el nombre de la clase y `.`  luego el nombre del field, también podríamos usar el nombre de un objeto pero es buena practica usar el de la clase

```
className.atributeName
```

Los métodos con el modificador static son métodos que no requieren de una instancia de la clase para ser invocados, aunque también pueden ser invocados desde una instancia de la clase(lo que es 
una mala practica) suelen ser útiles para retornar el valor de un field con el modificador static 

#### final

este modificador indica que una variable no puede cambiar su valor, perfecto para combinar con el modificador static y crear constantes

#### No especificado

si no especificamos un modificador estará disponible para la clase donde se definió y el paquete donde esta esa clase

### Métodos

Para definir un método primero colocamos su modificador, luego el tipo que va a retornar el método o si queremos que no retorne nada podemos poner `void` luego el nombre del método, después entre
paréntesis y separador por comas ponemos el tipo y nombre de los parámetros, también podemos dejar vacíos los paréntesis , finalmente ponemos un par de llaves y adentro de ellas iría todo la lógica
del método 

NOTA: java puede distinguir dos métodos con nombres iguales si tienen diferentes parámetros

#### varargs

Si tenemos un método el cual no sabemos cuantos parámetros va a recibir pero sabemos que son varios del mismo tipo podemos usar un vararg, esto creara un array del tipo que le especifiquemos con 
los datos que vayan llegando, para crear un parámetro vararg primero ponemos el tipo luego `...` y después el nombre que le queremos dar al array

#### objetos como parámetros

Los cambios que hacemos a parámetros adentro de los métodos normalmente desaparecen en cuanto el método termina, pero cuando tenemos un método que tiene como parámetro un objeto y 
cambiamos los campos de este objeto estaremos modificando los campos del objeto que pasamos al método y luego de terminar el método estos cambios permanecerán 

#### retornando clases 

Para que un método pueda retornar una clase esta debe de ser una sub clase de la clase donde se define el método o debe ser la misma clase donde se define el método 

#### this.

podemos usar `this.nameOfTheField` para referirnos a los fields de una clase, por lo que cuando invoquemos el método en un objeto nos referiremos a los fields de ese objeto, es util para darle el mismo
nombre a los parámetros que los de los fields

### Constructores

Los constructores son similares a los métodos solo que el nombre debe ser igual al de la clase, no tienen definido el tipo que retornan, luego para crear un objeto solo debemos poner primero el tipo
que sería el nombre de la clase luego el nombre de la variable donde lo vamos a almacenar luego el `=` después usamos la palabra `new` y otra vez el nombre de la clase, normalmente ls parámetros del
constructor serán los field que definamos en la clase pero también podemos crear varios constructores con distintas cantidades de parámetros 

#### alternativa a iniciar fields en un constructor

Podemos iniciar variable en un constructor pero tenemos alternativas la primera initializer blocks que son básicamente un par de llaves y dentro de ellas ponemos la lógica para iniciar el field que 
deseamos, un dato curioso es que java copia el código en de estos initializer blocks en todos los constructores, por lo que es una alternativa para no definir muchos inicios de fields 

la otra manera es usando el modificador final al momento en que declaramos el field, la desventaja de este método es que luego no podremos cambiar el valor del field

## Objetos

### acceder a un atributo

para acceder a un atributo de algún objeto podemos usar el `.` y luego el nombre del atributo

```
objeto.nombreAtributo
```

### invocar un método del objeto

para invocar un método del objeto solo debemos usar el `.` luego el nombre del método y terminar con un par de paréntesis donde irán nuestros parámetros o si el método no recibe parámetros lo 
podemos dejar vacío 


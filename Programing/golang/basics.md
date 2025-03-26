### Variables 

para declarar una variable en go podemos utilizar la palabra reservada "var", como por ejemplo  var number int, var es la palabra reservada, number el nombre de la variable y int el tipo de la
variable. Otra manera de declarar una variable es utilizando :=, utilizando := podemos declarar variables de la siguiente manera empty := " " en este caso empty es el nombre de la variable 
y  " " es el valor que va a tomar la variable, el tipo de la variable es inferido del valor el cual le asignemos, en este caso el tipo de la variable sería un string

### formas de declarar variables 

podemos declarar variables de varias maneras, ya vimos las más básicas pero también podemos declarar varias variables de distintos tipos en una misma linea por ejemplo:

```
mileage, company := 34657, "tesla" 
```

es igual que 

```
mileage := 34657
company := "tesla"
```

### Tipos

en go existen varios tipos de los que puede tener una variable pero a continuación voy a presentar los tipos standard que regularmente se usaran en el día a día 

bool
string
int 
uint
byte
rune
float64
complex128

### Conversión de tipos

podemos trasformar el tipo de algún valor para que se cambie el tipo, por ejemplo 

```
temperatureInt := 88
temperatureFloat := float64(temperatureInt)
```

### Constantes

Para declarar constantes debemos de utilizar la palabra dedicada const, para declarar constantes no podemos utilizar :=, las constantes pueden tener el tipo character, string, boolen o 
numeric, al momento de declarar una constante podemos combinar el valor de varias variables o constantes

### Condicionales 

los condicionales no utilizan paréntesis para envolver las condiciones, los condicionales usan if, else if y else, veamos un ejemplo:

```
if height > 6 {
    fmt.Println("You are super tall!")
} else if height > 4 {
    fmt.Println("You are tall enough!")
} else {
    fmt.Println("You are not tall enough!")
}
```

en los condicionales podemos declarar variables que solo estarán disponibles para el scope del condicional, por ejemplo para lo siguiente:

```
length := getLength(email)
if length < 1 {
    fmt.Println("Email is invalid")
}
```

podríamos hacer lo siguiente para hacerlo mas compacto 

```
if length := getLength(email); length < 1 {
    fmt.Println("Email is invalid")
}
```

### Funciones

las funciones en go se dividen en varias partes, observemos una función para explicar sus partes 

```
func sub(x int, y int) int {
  return x-y
}
```

func es la palabra reservada para declarar funciones, sub es el nombre que se le dio a la función, lo que esta adentro de los paréntesis son lo que la función recibe en este caso la función
recibe dos valores x y y ambos valores tienen un tipo de int, el int que esta al lado de los paréntesis representa el tipo del valor que la función sub debe retornar, finalmente el return es una 
palabra reservada que representa lo que la función va a retornar 

si una función acepta varios parámetros que tienen el mismo tipo podemos separar los parametros que comparten tipos uno al lado del otro separandolos con comas y al final final ponemos
el tipo, como en el siguiente ejemplo:

```
func add(x, y int) int {
  return x + y
}
```

si la función que tenemos retorna mas de un valor para especificar el tipo de los valores que se van a retornar debemos de pone los tipos entre paréntesis y separados con comas por 
ejemplo:

```
func getPoint() (x int, y int) {
  return 3, 4
}
```

y si queremos ignorar alguno de los varios valores que retorna una función podemos utilizar $\_$ , por ejemplo para ignorar el segundo valor que retorna la función anterior debemos hacer lo 
siguiente x, _ := getPoint()

anteriormente hablamos de definir los tipos de los valores que retornan las funciones, ademas de definir el tipo podemos darle un nombre, esto nos ayudara a documentar la función y que 
sea más sencillo saber que retorna, esto también crea una variable en el scope de la función y luego en el return no debemos repetir los valores que retornara la función podemos solo 
colocar el return solo, con esto en mente comparemos dos funciones que retornan lo mismo 

```
func getCoords() (x, y int){
  // x and y are initialized with zero values

  return // automatically returns x and y
}

func getCoords() (int, int){
  var x int
  var y int
  return x, y
}
```

aunque definamos los nombres de lo que retorna la función también podemos especificar que se retorne otra cosa con el mismo tipo, por ejemplo :

```
func getCoords() (x, y int){
  return 5, 6 // this is explicit, x and y are NOT returned
}
```

### Structures

En go se utilizan los structures para representar data estructurada, ya que suele ser de utilidad el tener varias variables juntas, por ejemplo para representar un carro, para el caso del carro
podríamos hacer lo siguiente :

```
type car struct {
  Make string
  Model string
  Height int
  Width int
}
```

podemos anidar structures una adentro de otra, por ejemplo volviendo al ejemplo del carro, para representar las llantas podríamos crear otra structure, lo que nos dejaría el siguinte 
resultado :

```
type car struct {
  Make string
  Model string
  Height int
  Width int
  FrontWheel Wheel
  BackWheel Wheel
}

type Wheel struct {
  Radius int
  Material string
}
```

para acceder a los diferentes campos de una structure utilizaremos el operador "." ejm:

```
myCar := car{}
myCar.FrontWheel.Radius = 5
```

Ademas de las structures normales existen las structures anónimas, se les conoce como anónimas porque a pesar de que son un structure estas no se definen con un nombre por lo que 
no se les puede referenciar en otro lugar del código, para crear una structure anónima debemos colocar un par de llaves luego de colocar el tipo, veamos dos ejemplos de esto 

```
myCar := struct {
  Make string
  Model string
} {
  Make: "tesla",
  Model: "model 3"
}
```

en este primer ejemplo el tipo de la structure anónima sería la structure myCar que definimos

```
type car struct {
  Make string
  Model string
  Height int
  Width int
  // Wheel is a field containing an anonymous struct
  Wheel struct {
    Radius int
    Material string
  }
}
```

en este segundo ejemplo el tipo de la structure anónima sería Wheel y ya luego colocamos las llaves

Go no es un lenguaje orientado a objetos pero respecto a las structures podemos hacer algo similar a la herencia, por ejemplo si queremos definir una structure para un camión podríamos 
reutilizar ciertos campos de nuestra previamente definida structure para un carro para hacer eso debemos hacer lo que siguiente 

```
type car struct {
  make string
  model string
}

type truck struct {
  // "car" is embedded, so the definition of a
  // "truck" now also additionally contains all
  // of the fields of the car struct
  car
  bedSize int
}
```

en este caso se le conoce a la structure truck como una embedded structure

la ventaja que nos ofrecen las embedded structures frente a las anidadas es que los campos que agregan a la structure pueden ser accedidos usando el operador . desde el primer nivel  a 
diferencia de las anidadas 

aunque go no sea un lenguaje orientado a objetos, podemos definir funciones para un tipo de structures específicos, para hacer esto debemos de agregar un parámetro especial a la 
función, este parámetro va antes del nombre de la función y entre paréntesis en este definimos primero el nombre que tendrá la structure adentro de la función y luego el tipo de 
structure, veamos un ejemplo para que sea mas claro 

```
type rect struct {
  width int
  height int
}

// area has a receiver of (r rect)
func (r rect) area() int {
  return r.width * r.height
}

r := rect{
  width: 5,
  height: 10,
}

fmt.Println(r.area())
// prints 50
```

### Interfaces

Las interfaces son colecciones de firmas de métodos, esto significa que una interfaz contiene varios métodos pero de estos solo tiene el nombre y el tipo que deben retornar, la 
implementación del método no se incluye. Se dice que un tipo implementa una interfaz si este tipo tiene la lógica definida para todos los métodos listados en la interfaz, estos métodos
deben tener el mismo nombre y retornar un valor con el tipo que se especifica en la interfaz, veamos un ejemplo 

```
type shape interface {
  area() float64
  perimeter() float64
}

type rect struct {
    width, height float64
}
func (r rect) area() float64 {
    return r.width * r.height
}
func (r rect) perimeter() float64 {
    return 2*r.width + 2*r.height
}

type circle struct {
    radius float64
}
func (c circle) area() float64 {
    return math.Pi * c.radius * c.radius
}
func (c circle) perimeter() float64 {
    return 2 * math.Pi * c.radius
}
```

un tipo puede implementar cualquier numero de interfaces, por ejemplo la interfaz vacía es implementada por todos los tipos

a la hora de definir la interfaz debemos de especificar los tipos de los valores que reciben los métodos y los tipos de los valores que retorna, opccionalmente podemos darle un valor a 
estos valores, aunque sea opcional es lo recomendado hacerlo 

### Type assertions 

los type assertions nos ayudan a comprobar el tipo de un valor definido con el tipo de una interfaz, con esto podemos verificar si nuestro valor pertenece a alguno de los tipos que 
implementan la interfaz, si es así podemos extraer el valor a otra variable veamos el siguiente ejemplo donde s es del tipo interfaz shape y vamos a verificar si es de tipo circle

```
type shape interface {
    area() float64
}

type circle struct {
    radius float64
}

// "c" is a new circle cast from "s"
// which is an instance of a shape.
// "ok" is a bool that is true if s was a circle
// or false if s isn't a circle
c, ok := s.(circle)
if !ok {
    // s wasn't a circle
    log.Fatal("s is not a circle")
}

radius := c.radius
```

para que ok sea true s debe de estar definido de una forma similar a la siguiente 

```
var s shape = circle{radius: 5}
```

### Type switches 

Los type switches nos permiten realizar varias verificaciones de assertions al mismo tiempo, se parecen mucho a los switch tradicionales solo que los cases tienen los tipos, veamos un
ejemplo

```
func printNumericValue(num interface{}) {
    switch v := num.(type) {
    case int:
        fmt.Printf("%T\n", v)
    case string:
        fmt.Printf("%T\n", v)
    default:
        fmt.Printf("%T\n", v)
    }
}

func main() {
    printNumericValue(1)
    // prints "int"

    printNumericValue("1")
    // prints "string"

    printNumericValue(struct{}{})
    // prints "struct {}"
}
```


### Errors

en go los errores se expresan con valores errors, estos valores errors serán cualquier tipo que implemente la siguiente interfaz 

```
type error interface {
    Error() string
}
```

las funciones que deben de tener un valor de retorno de tipo error, el cual debe ser verificado siempre que se llama a la función, esta verificación sería si el valor error es nil o no, si es nil
significa que no hubo problemas y si no lo es significa que si hubo problemas 

como error es una interfaz, podemos crear nuestras propias implementaciones de esta interfaz como la siguiente 

```
type userError struct {
    name string
}

func (e userError) Error() string {
    return fmt.Sprintf("%v has a problem with their account", e.name)
}
```

las librerías estándar de go nos proveen un paquete llamado errors con el que podemos manejar los errores, veamos un simple ejemplo usandolo 

```
var err error = errors.New("something went wrong")
```

### Loops

los loops en go se componen de varias partes 

```
for INITIAL; CONDITION; AFTER{
  // do something
}
```


Initial se corre al inicio del loop y puede ser utilizado para crear variables 
Condition es la condición que se verifica antes de cada iteración 
After se corre luego de cada iteración 

veamos un ejemplo de un loop



```
for i := 0; i < 10; i++ {
  fmt.Println(i)
}
// Prints 0 through 9
```

Los loops pueden omitir tener Alguno de los elementos que definimos anteriormente(INITIAL, CONDITION, AFTER) por ejemplo si quitamos CONDITION

```
for INITIAL; ; AFTER {
  // do something forever
}
```

En go no existe el concepto de while loop ya que go este es un loop for con solo la parte de CONDITION 

```
for CONDITION {
  // do some stuff while CONDITION is true
}
```


#### Continue 

Continue es una palabra reservada que nos permite terminar la interación actual y continuar con la siguiente, por ejemplo 

```
for i := 0; i < 10; i++ {
  if i % 2 == 0 {
    continue
  }
  fmt.Println(i)
}
// 1
// 3
// 5
// 7
// 9
```

#### Break 

break es una palabra reservada que nos permite terminar el loop actual osea deteniendo todas las iteraciones, por ejemplo 

```
for i := 0; i < 10; i++ {
  if i == 5 {
    break
  }
  fmt.Println(i)
}
// 0
// 1
// 2
// 3
// 4
```

### Arrays

Los arrays en go tienen un tamaño establecido desde que se crean por lo que no pueden superar ese tamaño, veamos un ejemplo de como declarar un array

```
var myInts [10]int
```

myInts es el nombre del array, [10] ser refiere al tamaño del array y int el tipo para los elementos del array 

si queremos ademas de declara el array inicializar sus valores podemos hacer algo como lo siguiente 

```
primes := [6]int{2, 3, 5, 7, 11, 13}
```

### Slices 

Los slices son como los array pero estos no tienen un tamaño fijo, por lo que se van extendiendo en tamaño dependiendo de los elementos que agreguemos al slice, los slices siempre 
tiene un array detrás pero este no esta especificado, pero podemos hacerlo para crear un slice a base de un array por ejemplo 

```
primes := [6]int{2, 3, 5, 7, 11, 13}
mySlice := primes[1:4]
// mySlice = {3, 5, 7}
```

en este caso usamos primes[1:4] para extraer una parte del array desde ciertas coordenadas, la coordenada de la izquierda es para especificar desde que posición empieza el trozo 
que vamos a sacar del array, esta primera coordenada incluye también al elemento en la coordenada, la segunda coordenada es la coordenada hasta la cual va a llegar el trozo
que vamos a sacar, esta segunda coordenada no incluye al elemento de la coordenada, podemos excluir alguna de las coordenadas y en entonces en el caso de la primera el trozo a sacar
empezara desde el inicio del array y en el caso del segundo el trozo ira hasta el final del array. Si excluimos ambas coordenadas se tomara todo el array 

para crear un slice sin tener que depender de un array podemos hacer algo similar a lo siguiente apoyándonos en la función make 

```
// func make([]T, len, cap) []T
mySlice := make([]int, 5, 10)

// the capacity argument is usually omitted and defaults to the length
mySlice := make([]int, 5)
```

en el primer ejemplo le pasamos tres argumentos a la función make, el primero es el tipo, el segundo el tamaño inicial y el tercero es la capacidad máxima, en el segundo ejemplo hacemos 
casi lo mismo solo que omitimos el tercer parámetro lo que hace que el slice no tenga limite de capacidad, al crear la función de esta manera el slice se llenara con el 0 del tipo del slice

si queremos crear un slice con unos valores definidos podemos hacer algo similar a lo siguiente 

```
mySlice := []string{"I", "love", "go"}
```

la diferencia aquí con un array es que no ponemos un numero adentro de los corchetes 

para obtener el tamaño de un slice podemos usar la función len(), por ejemplo para el slice anterior sería 

```
fmt.Println(len(mySlice)) // 3
```

la capacidad de un slice es la capacidad del array que tiene el slice detrás para acceder a este valor podemos usar la función cap() por ejemplo para el slice anterior sería 

```
fmt.Println(cap(mySlice)) // 3
```

#### Variadic functions 

Las funciones variadic son aquellas funciones que pueden recibir un numero arbitrario de parámetros. para hacer esto utilizamos la sintaxis "..." como en el siguiente ejemplo 

```
func concat(strs ...string) string {
    final := ""
    // strs is just a slice of strings
    for str := range strs {
        final += str
    }
    return final
}

func main() {
    final := concat("Hello ", "there ", "friend!")
    fmt.Println(total)
    // Output: Hello there friend!
}
```

en este caso se reciben los parámetros en el slice strs

#### Operador spreed 

el operador spreed nos permite pasar un slice a una función variadic, para eso debemos colocar el slice en los parametros de la función cuando la llamamos y añadirle ..., como en el 
siguiente ejemplo 

```
func printStrings(strings ...string) {
    for i := 0; i < len(strings); i++ {
        fmt.Println(strings[i])
    }
}

func main() {
    names := []string{"bob", "sue", "alice"}
    printStrings(names...)
}
```

#### Append para un slice 

Si queremos añadir elementos a un slice podemos utilizar la función append(), esta función recibe como parámetros los elementos que se quiere añadir al slice, esta función es variadic, 
por lo que podemos pasarle un elemento, varios separados con comas o un slice utilizando el operador spreed 

#### Loops con slices

Si queremos recorrer un slice utilizando un loop podemos usar la siguiente sintaxis 

```
for INDEX, ELEMENT := range SLICE {
}
```

donde el index guarda el indice del elemento y element el valor de ese elemento, veamos un ejemplo 

```
fruits := []string{"apple", "banana", "grape"}
for i, fruit := range fruits {
    fmt.Println(i, fruit)
}
// 0 apple
// 1 banana
// 2 grape
```

### Maps

Los maps de go son similares a los diccionarios de python, nos permiten crear una estructura que almacena llaves y valores, para crear un map podemos usar la función make(), veamos un
ejemplo: 

```
ages := make(map[string]int)
ages["John"] = 37
ages["Mary"] = 24
ages["Mary"] = 21 // overwrites 24
```

en el ejemplo para crear el map ponemos entre corchetes el tipo de la llave y luego ponemos el tipo de el valor en el ejemplo es la llave como string y el valor como int 

otra manera de crear un map sin utilizar la función make() es hacer algo similar a lo siguiente 

```
ages = map[string]int{
  "John": 37,
  "Mary": 21,
}
```

la función len() también funciona con los maps, y nos regresa la cantidad de pares llave valor que hay en el map

a los maps les podemos insertar un valor a una llave especifica de la siguiente manera 

```
m[key] = elem
```

podemos obtener el valor de una llave especifica 

```
elem = m[key]
```

podemos eliminar un elemento usando la llave y la función delete()

```
delete(m, key)
```

podemos verificar si la llave que estamos usando esta en el map de formas similares a la siguiente 

```
elem, ok := m[key]
```

todos los tipos pueden ser valores del map, pero no todos pueden ser llaves, estos que no pueden ser llaves son slices, maps y funciones 

podemos anidar maps uno adentro de otro creando estructuras un poco complicada

### Funciones avanzadas 

Go permite que una función reciba como parámetro otra función o que una función retorne otra función, veamos con un ejemplo como una función puede recibir y retornar una función
```
func add(x, y int) int {
  return x + y
}

func mul(x, y int) int {
  return x * y
}

// aggregate applies the given math function to the first 3 inputs
func aggregate(a, b, c int, arithmetic func(int, int) int) int {
  return arithmetic(arithmetic(a, b), c)
}

func main(){
  fmt.Println(aggregate(2,3,4, add))
  // prints 9
  fmt.Println(aggregate(2,3,4, mul))
  // prints 24
}
```


primero para recibir una función vemos que en los paréntesis colocamos primero el nombre de la función luego la palabra reserva func, luego ponemos los tipos de los parámetros que 
recibe entre paréntesis y finalmente colocamos el tipo del valor que retorna la función, luego al momento de realizar el retorno vemos que se llama a la función del parámetro pasandole
sus parámetros 

#### Function currying 

function currying se refiere a cuando una función toma como parámetro una o varias funciones y retorna una función nueva, veamos un ejemplo 

```
func main() {
  squareFunc := selfMath(multiply)
  doubleFunc := selfMath(add)

  fmt.Println(squareFunc(5))
  // prints 25

  fmt.Println(doubleFunc(5))
  // prints 10
}

func multiply(x, y int) int {
  return x * y
}

func add(x, y int) int {
  return x + y
}

func selfMath(mathFunc func(int, int) int) func (int) int {
  return func(x int) int {
    return mathFunc(x, x)
  }
}
```

la función selfMath recibe como parámetro una función que en el scope de la función selfMath se va a llamar mathFunc, luego al final vemos que se define el tipo de lo que va a retornar
la función y en este caso el tipo es una función que recibe un int y retorna un int, luego más abajo en la función selfMath se define el return con la función que llama a la función que 
pasamos a selfMath y si nos fijamos la función que retorna selfMath cumple con que recibe un int y retorna un int 

#### Defer

defer es una palabra reservada de go que nos permite realizar una acción dentro de una función pero esta acción solo se realizara luego de que la función retorne  veamos un ejemplo 

```
// CopyFile copies a file from srcName to dstName on the local filesystem.
func CopyFile(dstName, srcName string) (written int64, err error) {

  // Open the source file
  src, err := os.Open(srcName)
  if err != nil {
    return
  }
  // Close the source file when the CopyFile function returns
  defer src.Close()

  // Create the destination file
  dst, err := os.Create(dstName)
  if err != nil {
    return
  }
  // Close the destination file when the CopyFile function returns
  defer dst.Close()

  return io.Copy(dst, src)
}
```

#### Closures

las funciones closures son aquellas funciones que mutan variables que están fuera del scope de la función, como en el siguiente ejemplo que la función concatter retorna una función que en cada llamada modifica la variable doc
que esta fuera de su scope 

```
func concatter() func(string) string {
    doc := ""
    return func(word string) string {
        doc += word + " "
        return doc
    }
}

func main() {
    harryPotterAggregator := concatter()
    harryPotterAggregator("Mr.")
    harryPotterAggregator("and")
    harryPotterAggregator("Mrs.")
    harryPotterAggregator("Dursley")
    harryPotterAggregator("of")
    harryPotterAggregator("number")
    harryPotterAggregator("four,")
    harryPotterAggregator("Privet")

    fmt.Println(harryPotterAggregator("Drive"))
    // Mr. and Mrs. Dursley of number four, Privet Drive
}
```

#### Funciones anónimas

las funciones anónimas son como las funciones normales solo que no tienen nombre, veamos un ejemplo donde se usan una función anónima 

```
// doMath accepts a function that converts one int into another
// and a slice of ints. It returns a slice of ints that have been
// converted by the passed in function.
func doMath(f func(int) int, nums []int) []int {
    var results []int
```    for _, n := range nums {
        results = append(results, f(n))
    }
    return results
}

func main() {
    nums := []int{1, 2, 3, 4, 5}

    // Here we define an anonymous function that doubles an int
    // and pass it to doMath
    allNumsDoubled := doMath(func(x int) int {
        return x + x
    }, nums)

    fmt.Println(allNumsDoubled)
    // prints:
    // [2 4 6 8 10]
}
```

en el ejemplo tenemos la función doMath que recibe una función y un slice de tipo int, cuando llamamos la función doMath en main en vez de definir una función para luego pasarsela a doMath definimos la función en los 
paréntesis de los parámetros

### Pointers

un pointer es una variable que almacena la dirección en memoria de otra variable, para definir un pointer usamos la sintaxis $*$ como en el siguiente ejemplo 

```
var p *int
```

también podemos usar el operador & para asignar la dirección en memoria de una variable a otra variable, por ejemplo 

```
myString := "hello"
myStringPtr = &myString
```

#### Pointer receivers

Cuando una función recibe pointers nos permite modificar el valor al cual apunta el pointer, mientras que si no usamos el pointer los cambios se realizarían a una copia de lo que le pasemos al metodo, veamos un ejemplo

```
type car struct {
    color string
}

func (c *car) setColor(color string) {
    c.color = color
}

func main() {
    c := car{
        color: "white",
    }
    c.setColor("blue")
    fmt.Println(c.color)
    // prints "blue"
}
```

en este ejemplo creamos un struct car y luego definimos una función en la que especificamos que es para la struct car, ademas de car vemos que se pone un $*$ esto es para representar que se va a usar pointers, lo que nos 
permite modificar directamente el valor del struct al cual le llamamos la función. Si no usamos el $*$ entonces los cambios que haría la función setColor se aplicarían a el car que definimos en la función main

Si usamos una función que recibe pointers no es necesario que en los parámetros le pasemos el pointer en si ya que si le pasamos el valor go sacara el pointer el solo 

### Packages

En go cada programa esta hecho de packages, el paquete se define al inicio del código, existe un nombre especial el cual es main, que nos permite crear una función main, el paquete main es especial porque nos permite 
compilar el código a un programa ejecutable, el resto de paquetes con nombres diferentes se les conoce como paquetes librerías 

#### Convenciones 

la convención de nombres para paquetes es utilizar el ultimo elemento del path de importación por ejemplo si tenemos math/rand entonces el nombre del paquete sería rand, pero no es necesario que esto se cumpla siempre 

### 1 paquete por directorio

todo el código que esta en un directorio debe pertenecer al mismo paquete, si esto no sucede obtendremos un error 

### Módulos 

Un módulo de go es una colección de paquetes de go, un repositorio normalmente contiene 1 o más módulos de go 

para definir un módulo debemos de crear un archivo go.mod en la raíz del proyecto, en este archivo se define:

- el path al modulo
- la versión de go que requiere el programa
- opcionalmente las distintas dependencias 

veamos un ejemplo de un archivo go.mod 

```
module github.com/bootdotdev/exampleproject

go 1.20

require github.com/google/examplepackage v1.3.0
```

para iniciar el go.mod debemos ir al directorio donde tenemos el proyecto y poner el siguiente comando 

```
go mod init {REMOTE}/{USERNAME}/{NAME-DIRECTORY}
```

donde REMOTE es el proveedor para git que usemos, USERNAME pos nuestro nombre de usuario y el NAME-DIRECTORY es el nombre del directorio donde tenemos nuestro código 

para ejecutar un código de go podemos usar tres commandos el primero es go run que compila y ejecuta el código, pero no deja binarios, el segundo comando es go build, este comando solo nos genera binarios que luego 
podemos correr, finalmente tenemos el comando go install que crea binarios del código en un el directorio $GOBIN

### Channels 

en go existen dos maneras de ejecutar el código, la primera es sincrónica que es que se corren las tareas una después de otra, la segunda es asincrónica que es donde se realizan varias tareas al mismo tiempo, dependiendo
de cuantos núcleos tenga nuestro procesador

para que nuestro código se ejecute de manera asincrónica solo debemos de colocar go antes de la llamada de la función, por ejemplo 

```
go doSomething()
```
aquí la palabra reservada go lo que hace es que crea un nuevo goroutine, un goroutine es un hilo liviano de ejecución 

si solo usamos la palabra reservada go solo vamos a crear diferentes go routines que no se van a comunicar entre ellos ni coordinar, ahí es donde entran los channels que son un tipo de cola segura de hilos, que permite que 
varios hilos se comuniquen entre ellos, si queremos crear un channel podemos usar la función make(), por ejemplo:

```
ch := make(chan int)
```
#### Operadores -> y <-

para enviarle datos a una channel podemos usar el operador <- por ejemplo para el channel que definimos anteriormente 

```
ch <- 69
```
 para recibir datos de un channel podemos usar el operador -> por ejemplo

```
v := <-ch
```

lo que hace el comando de arriba es remover un dato del channel ch y guardarlo en la variable v, ademas si no hay datos en el channel la tarea se bloqueara hasta que un dato llegue al channel 

#### Tokens

Normalmente se usan structs vacíos como una especie de tokens, la utilidad del token es para que llegue un dato al channel, el contenido no importa solo el hecho de que llega algo al channel, para tener un channel bloqueado
hasta que le llegue un dato podemos hacer algo como lo siguiente 

```
<-ch
```

#### Buffers 

Podemos añadirle un buffer a un channel para que el channel puede recibir cierto numero de datos sin que el channel tenga que procesarlo, para añadirle un buffer a un channel podemos pasarle el segundo parámetro a la 
función make() como en el siguiente ejemplo 

```
ch := make(chan int, 100)
```
el segundo parámetro es el tamaño del buffer

cuando un channel tiene un buffer este solo se bloqueara cuando 

#### Close channels

podemos cerrar explicitamente channels usando la función close(), como por ejemplo 

```
ch := make(chan int)

// do some stuff with the channel

close(ch)
```

para verificar si un channel esta cerrado podemos hacer algo similar a con los maps

```
v, ok := <-ch
```
 si ok es false el channel esta cerrado y si es true no esta cerrado 

#### Iterate over a channel

podemos iterar a través de un channel de una forma similar a la siguiente 

```
for item := range ch {
    // item is the next value received from the channel
}
```

el ejemplo anterior solo se detendrá cuando el channel sea cerrado 

### Select 

Podemos tener a un solo goroutine escuchando a varios channels, si queremos procesar la data que llega de todos los canales en el orden que llega a ellos podemos hacer algo similar a un switch pero que se llama select
veamos un ejemplo 

```
select {
  case i, ok := <- chInts:
    fmt.Println(i)
  case s, ok := <- chStrings:
    fmt.Println(s)
}
```
en este caso tenemos dos canales y ademas mediante el ok podríamos verificar si el channel esta cerrado o no, el primer channel que envíe información sera para el cual se cumpla la acción de su case y si varios envían 
información al mismo tiempo, se escogerá a uno al azar 

podemos agregar un case especial al select, el cual es el case default que se ejecutara en el caso de que ningún channel envíe data, veamos un ejemplo

```
select {
  case v := <-ch:
    // use v
  default:
    // receiving from ch would block
    // so do something else
}
```

### Mutexes 

Los mutexes nos permiten bloquear el acceso a diferente data para los goroutines, lo que nos permite que solo ciertas goroutines accedan a cierta información a un tiempo especifico, la librería estándar nos da una 
implementación de los mutexes con los tipos sync.Mutex gracias a las funciones .Lock() y .Unblock

podemos bloquear un bloque de codigo usando la función mux.Lock() y luego desbloquearlo usando la función mux.Unblock, veamos un ejemplo 

```
func protected(){
    mux.Lock()
    defer mux.Unlock()
    // the rest of the function is protected
    // any other calls to `mux.Lock()` will block
}
```

en este caso se usa defer para desbloquear la función cuando retorne 

si tenemos varios goroutines accediendo a un map y alguno esta escribiendo el map, debemos bloquearlo

el principal uso de mutex es para prevenir que dos o más goroutines o channels escriban y lean algo, ya que esto causaría un error 

veamos otro ejemplo mas insano donde se usan mutexes

```
package main

import (
    "fmt"
)

func main() {
    m := map[int]int{}
    go writeLoop(m)
    go readLoop(m)

    // stop program from exiting, must be killed
    block := make(chan struct{})
    <-block
}

func writeLoop(m map[int]int) {
    for {
        for i := 0; i < 100; i++ {
            m[i] = i
        }
    }
}

func readLoop(m map[int]int) {
    for {
        for k, v := range m {
            fmt.Println(k, "-", v)
        }
    }
}
```

si corremos el código del ejemplo anterior en una pc con multiples cores, obtendríamos un error, ya que estamos intentando leer y escribir el map m al mismo tiempo

ahora usemos un mutex para resolver el error 

```
package main

import (
    "fmt"
    "sync"
)

func main() {
    m := map[int]int{}

    mux := &sync.Mutex{}

    go writeLoop(m, mux)
    go readLoop(m, mux)

    // stop program from exiting, must be killed
    block := make(chan struct{})
    <-block
}

func writeLoop(m map[int]int, mux *sync.Mutex) {
    for {
        for i := 0; i < 100; i++ {
            mux.Lock()
            m[i] = i
            mux.Unlock()
        }
    }
}

func readLoop(m map[int]int, mux *sync.Mutex) {
    for {
        mux.Lock()
        for k, v := range m {
            fmt.Println(k, "-", v)
        }
        mux.Unlock()
    }
}
```

 primero importamos sync.Mutex(), y en la función main lo llamamos mux y lo vamos pasando a las funciones de escritura y lectura, luego para cada ciclo en el que escribimos bloqueamos y desbloqueamos, y cuando leemos 
 bloqueamos cuando empezamos a leer y desbloqueamos cuando acabamos de leer todo el map

ademas de este mutex tenemos otra librería estándar llamada sync.RWMutex que añade dos métodos nuevo RLock() y RUnlock, estos métodos nos permiten que varias goroutines leen un map al mismo tiempo

### Generics

los generics son variables que nos permiten usar variables para referirnos a tipos específicos, lo que nos permite crear funciones abstractas, como el siguiente ejemplo 

```
func splitAnySlice[T any](s []T) ([]T, []T) {
    mid := len(s)/2
    return s[:mid], s[mid:]
}
```

en este ejemplo se construyo una función que nos permite partir en dos cualquier tipo de slice,  para que esto funcione así definimos entre corchetes antes de donde se definen los parámetros que recibe la función a T como
un tipo any, luego en la parte donde definimos los parámetros de la función ponemos que se reciben slices de tipo T osea que se reciben slices de tipo any, esto nos ahorra el tener que hacer una función para cada
tipo de slice

#### Constraints

Los constraints son interfaces que nos permiten crear generics, por ejemplo any es la interfaz vacía en los constraints, veamos un ejemplo definiendo un constraints

```
type stringer interface {
    String() string
}

func concat[T stringer](vals []T) string {
    result := ""
    for _, val := range vals {
        // this is where the .String() method
        // is used. That's why we need a more specific
        // constraint instead of the any constraint
        result += val.String()
    }
    return result
}
```

aquí definimos a stringer como el constraints, le ponemos que debe tener un método llamado String que regrese un string, esto sería como para que los tipos que no son string tengan una función que regrese un string 
con eso ya definimos en la función a T como stringer y luego los parámetros que recibe la función ponemos que deben ser slices de tipo T osea de tipo stringer 

existe otra manera de crear constraints la cual es la siguiente:

```
// Ordered is a type constraint that matches any ordered type.
// An ordered type is one that supports the <, <=, >, and >= operators.
type Ordered interface {
    ~int | ~int8 | ~int16 | ~int32 | ~int64 |
        ~uint | ~uint8 | ~uint16 | ~uint32 | ~uint64 | ~uintptr |
        ~float32 | ~float64 |
        ~string
}
```

aquí lo que hacemos es listar por familia de tipos los cuales va a incluir el constraints, osea que por fila ponemos una familia diferente, para decir que incluye el tipo especifico le ponemos antes el ~ y para separarlos usamos |



### Open

para leer un archivo en python podemos usar la función open que recibe como parámetro el path al archivo que queremos leer, y nos retorna un objeto que con diferentes métodos nos permite obtener 
información del archivo 

#### .read() 

nos permite obtener la información del archivo por ejemplo el texto de un archivo 


#### Open mode

la función open también recibe un parámetro mode el cual define en que modo abrimos el archivo, los modos que existen son r para reading que es el default, w para writing, a para append que nos deja
solamente añadir información al final del archivo y x para el 2 exclusive creation, el cual nos deja escribir un archivo y nos da un error si el archivo ya existe 

si añadimos b al final de los modos por ejemplo rb estaremos leyendo el archivo en binario si no agregamos esto python lo tomara como si fuera un archivo de texto

#### Checking permissions

Podemos verificar con el objeto que retorna la función Open si esta puede ser escrita o leída usando los métodos writable() y readable()

#### Encoding 

La función Open() recibe un parámetro encoding el cual nos permite definir el encoding con el que deseamos abrir el archivo, los encoding varían dependiendo de si es binario o texto, por ejemplo para 
el texto tenemos el `utf-8`

#### Pointers 

para python realizar las operaciones en los archivos utiliza algo llamado pointers que se encargan de marcar algún lugar del contenidos del archivo que se paso a Open(), cuando estamos en modos 
como w y r el pointer se colocara al inicio del contenido del archivo pero en en el modo a el pointer estará al final, cuando en el modo r usamos el método .read, al ir leyendo el archivo python moverá el 
pointer por lo que luego no podríamos volver a leer el contenido a menos que creemos otro objeto con Open()

los pointers se mueven por los archivos de carácter en carácter 
#### .tell()

podemos obtener la posición de pointer en el array de caracteres usando la función .tell()

#### .seek() 

podemos definir la posición del pointer en el array de caracteres usando la función seek y pasando como int la posición que deseamos definir para el pointer 
#### .readline()

podemos usar la función readline para ir leyendo una linea a la vez el archivo, cada vez que ejecutamos moverá el pointer al inicio de la siguiente linea 

#### Iterar sobre lineas 

podemos iterar por las lineas de un archivo de una forma similar a un for each, para esto haremos algo similar a lo siguiete 
```
for line in files:
  print(line)
```

### Close

Es importante cerrar un archivo luego de que no lo estemos utilizando, para reducir el consumo de recursos del programa, para esto podemos usar el método close(), también podemos verificar 
con otro método llamado closed si un archivo esta cerrado, closed, retorna true si el archivo esta cerrado o false de lo contrarío 

### With

Como se menciono anteriormente es importante cerrar los archivos cuando no los usemos, pero el método close() puede ser insuficiente en situaciones donde el programa obtenga un error y no llegue
al punto donde se ejecuta el método close(), para esto existe una solución la cual es with, el cual nos permite crear un bloque de código indented donde podremos realizar las tareas que tengamos con 
nuestro archivo, luego del bloque de código el archivo se cerrara automáticamente o si ocurre un error durante la ejecución del código veamos un ejemplo de abrir un archivo usando with

```
with open("path/to/file", "r") as file:
  line = file.readline()
  line.remove()
```

en el ejemplo anterior obtendríamos un error pero aún así se cerraría el archivo 

### Writing a file

para escribir un archivo debemos de abrirlo con el modo w, algo importante a tener en cuenta es que al abrir un archivo de esta manera, se eliminara el contenido previo del archivo, para escribir algo en 
el archivo podemos usar el método write() al cual le pasamos como parámetro el contenido a escribir, si queremos un salto de linea debemos de especificarlo con la combinación de caracteres 
especiales `\n` 

#### flush() 

Este método nos permite enviar la información que tenemos del archivo al cual estamos escribiendo del buffer al disco, es importante llamar a este método antes de cerrar un archivo al cual estabamos escribiendo 

### Appending content to a file

Para agregar contenido al final de un archivo usamos la función Open() con el modo a, luego podemos usar el método write() para escribir al final del archivo como lo hicimos en Writing a file, la 
diferencia es que en el modo a no eliminamos el contenido previo del archivo, nuevamente el método write() no añade un salto de linea antes de agregar el contenido eso lo debemos de hacer usando 
`\n`


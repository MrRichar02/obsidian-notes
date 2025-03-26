Los servidores http en go se componen principalmente de dos partes, un servidor que escucha por las request y uno o más handlers que se encargan de procesar las requests

### handlers:

las funciones handlers tienen algo en común respecto a los parámetros que reciben y esto es que siempre reciben un parámetro de tipo ResponseWriter y otro de tipo $*$Request, el parámetro de tipo ResponseWtriter es usado 
para formular la respuesta al request, por el ejemplo el body de la respuesta o el código de estado, el parámetro de tipo $*$Request es usado para obtener la información del request o del usuario que hizo la request

#### Asignar un handler a una ruta especifica:

Para asignar una función handler a una ruta especifica podemos utilizar la función HandleFunc(), esta función recibe dos parámetros, el primero es la ruta especifica a la que queremos asignar la función handler, esta ruta se debe
de escribir como un string, el segundo parámetro que recibe es el nombre de la función a utilizar para la ruta especifica 

### Listen in a specific port

para que nuestro servidor HTTP escuche en un puerto especifico podemos utilizar la función ListenAndServe, esta función toma dos argumentos el primero es el puerto donde debe escuchar, debe ser escrito en forma de string
y se formatea de una forma similar a la siguiente, "dirección_ip:puerto", ademas de esto podemos solo poner los dos puntos y luego el puerto, lo que hará que el servidor escuche a cada dirección ip asociada con tu computadora 
y escuchara en el puerto que especifiques, el segundo parámetro que recibe es de tipo Handler, este sera el servidor que utilizará, le podemos pasar alguno si lo tenemos definido o nil para que use el servidor default, la función
bloqueara al programa hasta que esta se deje de ejecutar

Un ejemplo de un tipo Handler que le podríamos pasar a la función ListenAndServe es el de struct de tipo ServerMux

### Request

podemos acceder a los params de un request utilizando el tipo $*$Request que recibimos en el handler, de una forma similar a la siguiente:

```
r.URL.Query().Get("param")
```

en este caso r representa el tipo $*$Request, la función Get() obtiene el valor del param especificado entre las comillas 

```
r.URL.Query().Has("param")
```

en este caso r representa el tipo $*$Request, en el ejemplo anterior usamos la función Has() para asegurarnos que el param fue enviado en el request, entre comillas escribimos el nombre del param 

También podemos acceder al body del request 
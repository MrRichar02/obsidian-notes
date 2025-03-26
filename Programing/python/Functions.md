## Characteristics

- Las funciones en python son objetos de primer nivel, esto significa que podemos asignar una función a una variable, no tiene que ser una función lambda sino cualquier función, esto nos permite hacer cosas como almacenar funciones en listas y cosas por el estilo

## Args and kwargs 

Podemos especificar en la definición de una función que esta va a recibir una cantidad incierta de argumentos, para hacer eso al antes del nombre del parámetro vamos a colocar un $*$,  luego el 
parámetro guardara todos los valores en una tuple, también podemos añadir antes de un parámetro dos $*$ lo que recibirá valores que estén nombrados por ejemplo `hello=world` y creara un diccionario 
que se almacenara en el parámetro 


## Lambda functions

Podemos definir funciones pequeñas en una línea usando las funciones lambda para hacerlo primero vamos a poner el nombre de la variable donde vamos a guardar la función, luego ponemos `=`, 
seguido de la palabra reservada `lambda` luego definimos separados por comas los parámetros de la función, luego colocamos un `:` luego de esto vamos a especificar lo que va a retornar la función
veamos un ejemplo 
```
add = lambda a, b: a + b
```
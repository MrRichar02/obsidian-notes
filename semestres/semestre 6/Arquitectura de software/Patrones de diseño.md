[[Indice arquitectura de software]]

## Facade:

Este patrón es enfocado en la programación orientada a objetos, el objetivo de este patrón es simplificar la interacción del usuario con el programa, para esto hace que varias interacciones entre clases 
que serían necesarias para obtener ciertos resultados se realicen mediante otra clase, entonces tendríamos clases que nos simplifican lógica compleja para que el usuario no tenga dificultad 

## Builder:

Este patrón se enfoca en crear una clase constructor gigante con parámetros suficientes para crear cualquier tipo de objeto, esto con el objetivo de no tener muchas subclases para distintos tipos de 
objetos con el coste de tener una clase que al crearse no usara todos sus parámetros  

## Bridge:

Este patrón tiene el objetivo de separar la abstracción de la implementación para reducir la creación de subclases para objetos muy similares pero con pequeñas diferencias vamos a optar por 
usar una interfaz para definir la parte abstracta de la clase y luego podemos implementar la interfaz a la hora de la implementación

## MVC:

Este patrón divide la lógica de la aplicación en tres partes, la primera es el modelo esta se encarga de la lógica del negocio, cosas como consultas a bases de datos y procesamiento de información,  la
segunda sería la vista que se encarga de la interfaz que el usuario ve y con la cual interactua, finalmente tenemos el controlador que se encarga de gestionar la comunicación entre el modelo y la vista

## Observer:

Este patrón promueve un sistema de suscripciones entre objetos, osea que varios objetos se pueden suscribir a otro objeto y cuando ocurra un cambio con ese objeto los objetos suscritos recibirán una 
notificación, es importante que se puedan cancelar las suscripciones 

## Decorator:

Este patrón propone usar objetos de ayuda para aumentar las características de un objeto, para esto crearemos una interfaz para nuestras clases y cuando necesitemos una nueva funcionalidad para
nuestro objeto podremos crear una nueva clase con esta funcionalidad y asociarlo a nuestro objeto actual

## Factory:

Este método propone crear una clase que se encarga de crear varios objetos que son similares pero no iguales, esto le ahorra al usuario el conocer como crear cada tipo diferente de los objetos que son
similares, para esto primero debemos crear una interfaz para los objetos que son similares, luego vamos a crear una implementación de esta interfaz para cada tipo diferente, luego vamos a crear
la clase fabrica que se va a  encargar de recibir los parámetros para crear los objetos y entender que tipo se va a crear

## Proxy:

Este método nos permite controlar el acceso a un objeto mediante otro objeto, para que esto sea posible debemos tener una interfaz que tanto el objeto al cual controlamos el acceso como el cual
nos ayuda a controlar el acceso implementen, el objeto que nos ayuda a controlar el objeto tendrá una referencia al objeto al que controlamos el acceso esto para cuando se necesiten algunos métodos
del objeto al cual controlamos el acceso. Podemos añadir lógica adicional al objeto que nos ayuda a controlar el acceso al otro

## Adapter:

Este patrón nos da una manera de comunicar dos interfaces que son incompatibles, para esto debemos de crear una interfaz intermediaria que obtiene la información de la primera interfaz y la traduce
para que lo otro interfaz previamente incompatible la pueda comprender 

## Strategy:

Este patrón propone una manera de lidiar con un objeto que tiene muchas funcionalidad, para hacer esto en lugar de tener toda la lógica en una clase, vamos a crear subclases llamadas estrategias, en 
estas sub clases es donde vamos a implementar la lógica para ciertas operaciones, luego en la clase principal vamos a tener un campo donde podemos referenciar una de las subclases, y cuando 
necesitamos realizar alguna operación se la podemos delegar a la sub clase que tenemos referenciada 

## DAO:

Este patrón propone aislar los accesos a la base de datos de el resto de la aplicación, lo que hace que la base de datos sea independiente de la lógica de negocio y viceversa, también hace muy fácil el 
cambiar la base de datos o su esquema 

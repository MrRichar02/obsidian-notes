Los enums son un tipo de classes que nos permiten definir varias constantes de una manera simple, para crear un enum solo debemos poner enum luego el nombre que le queramos dar, abrimos luego 
unas llaves y dentro de ella y separados por comas definimos las distintas constantes, para acceder a la constante de un enum debemos crear una instancia del enum poniendo como tipo el nombre del
enum, y como valor el nombre del enum y luego usando el `.` detallamos cual de las constantes le queremos asignar

también le podemos usar un enum en un switch para definir respuestas para las constantes del enum, donde lo que le pasamos al switch es una instancia del enum y los casos son las constantes 

Un enum puede tener fields y métodos que se añaden luego de la lista de constantes, algo interesante que podemos hacer con el constructor es añadir mas información a las constantes 

## Métodos de los enums

### .name()

Retorna el nombre de la instancia del enum

### .ordinal()

Retorna la posición de la instancia del enum respecto a como la declaramos en el enum

### .values()

Retorna un array con todas las constantes

### .valueOf("nameOfEnum")

Retorna una constante usando el nombre de la constante como referencia 

## .compareTo(instancia de un enum)

Retorna el resultado de restar la posición de la instancia del enum que le pasamos a la instancia del enum desde el que lo estamos invocando 

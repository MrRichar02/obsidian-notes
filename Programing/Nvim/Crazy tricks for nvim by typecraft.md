- Si seleccionamos un trozo de texto en visual mod y apretamos `g + ?` todo el texto sera encriptado usando la tecnica que cambia cada letra por la siguiente numero 13 en alfabeto

- Si en command mode usamos el comando `e` que normalmente se usa para abrir archivos o para tener una vista de árbol de un directorio , y le pasamos la dirección de un archivo de la web, puede mediante el uso de curl, nos descargue el contenido XML de la dirección y nos coloque en un nuevo buffer con el contenido 

- Si en un archivo estando en commando mode ejecutamos el commando `TOhtml` se nos generara un nuevo archivo html el cual va a replicar el contenido del archivo con todos los colores que tenga para un archivo html

- Podemos editar archivos en modo binario, para esto primero abrimos el archivo agregando la flag `-b` luego de entrar al archivo vamos a ejecutar en command mode el siguiente comando `%!xxd` esto convertirá el contenido del archivo a binario, para revertir esto debemos ejecutar el siguiente comando `%!xxd -r` NOTE(no me funciono en NIXOS :( seguro me falta instalar xxd))

- En normal mode si apretamos `Q` vamos a entrar a un modo antiguo del antecesor de vim, para salir de el solo debemos de escribir el comando visual NOTE(no me funciono en nixvim xd)

- Si seleccionamos el texto de un archivo en visual mode  y luego entramos en command mode podemos utilizar `!` para ejecutar un comando de la shell sobre el texto seleccionado 

- Si estamos en insert mode y presionamos la combinación de teclas `ctrl + r + =` podremos escribir una operación matemática y luego al apretar `enter` el resultado se pondrá donde teníamos el cursor (no me funciono, creo que por mi distribución de teclado xd)

- En command mode podemos usar el comando `r` para leer el output de un commando de la terminal, y escribirlo en el buffer actual, pero debemos colocar el carácter `!` antes del comando de la terminal, por ejemplo `r!whoami` 

- Si en commando mode escribimos el comando `help 42` veremos un ester-egg  


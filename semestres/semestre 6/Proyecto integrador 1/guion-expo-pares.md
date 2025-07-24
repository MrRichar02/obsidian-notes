## diapo 1
Cordial saludo mi nombre es Ricardo Medina mis compañeros de equipo son Jorge Luis Rodríguez y Santiago Jiménez. El proyecto que realizamos en la materia fue un sistema de gestión de alquiler de productos para el area de la construcción que llamamos vulkano

## diapo 2
En esta exposición trataremos lo siguiente:
- la problemática que identificamos
- la solución que propusimos
- las metodologías que seguimos
-  la arquitectura del aplicativo
-  los módulos del aplicativo
-  los resultados obtenidos y finalmente daremos nuestras conclusiones


## diapo 3

El problema que identificamos es que en muchas empresas dedicadas al alquiler se lleva la trazabilidad de una manera deficiente que afecta negativamente a la empresa
## diapo 4

La solución que proponemos es una plataforma multiproposito que permita realizar los alquileres y otras funciones utiles para las empresas de alquiler, mas adelante hablaremos sobre todas las funciones 

gracias a esta plataforma se puede tener una mejor trazabilidad y experiencia de trabajo

## Módulos

### Administración

se tienen dos entidades principales que serían los clientes del aplicativo tenemos las empresas y las sucursales que pertenecen a estas empresas, tenemos un CRUD para ambas, y al momenot de crear una sucrusal la vinculamos a una empresa, algo adicional es que podemos importar el listado de empresas en distintos formatos 

### Productos

para la parte de productos tenemos un crud para los productos, para los provedores y las categorias, ademas podemos asignar editar o eliminar los precios de los producots registrados, y podemos observar el inventario por sucursales

### Autenticación

aqui es donde registramos los usuarios que van a utilizar la plataforma, al momento de crear un usuario elegimos la empresa a la que va a pertenecer y el usuario solo podra ver contenido relacionado a su empresa 

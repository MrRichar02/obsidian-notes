## diapo 1
Cordial saludo mi nombre es Ricardo Medina mis compañeros de equipo son Jorge Luis Rodríguez y Santiago Jiménez y el proyecto que realizamos en la materia fue un sistema de gestión de alquiler de productos para el area de la construcción

problemática 
## diapo 2
En esa exposición trataremos la problemática que identificamos, la solución que propusimos, las metodologías que seguimos, la arquitectura del aplicativo, los módulos del aplicativo, los resultados obtenidos y finalmente daremos nuestras conclusiones

## diapo 3
el problema que identificamos consiste en 3 partes y puede ser aplicado para los negocios dedicados al alquiler de productos en general pero decidimos enfocarnos en el area de construcción

respecto a las partes del problema tenemos 

Gestión manual se refiere a que muchas empresas dedicadas al alquiler de productos llevan su trazabilidad de forma manual esto puede ser en el peor de los casos a lápiz y papel o utilizando herramientas como Excel, el problema aquí es que se debe repetir una misma acción varias veces lo que hace probable cometer errores, ademas para obtener estadísticas sobre los alquileres se necesitaría realizar un trabajo extra 

falta de visibilidad se refiera a que gracias a una trazabilidad deficiente se vuelve complicado llevar la cuenta de la cantidad de productos disponibles y en el caso de que mas de un persona se encargue de los registros pueden ocurrir inconsistencias o duplicados 

Finalmente Ausencia de un historial esto se refiere a que sería un reto llevar cuenta de la condición en que se encuentran todos los productos, lo que puede hacer que se cuente en el inventario con productos que necesitan mantenimiento o que se alquilen productos con daños

## diapo 4

Ahora pasemos a la solución planteada, de una forma general es una plataforma en la que se pueden realizar diversas tareas relacionadas al alquiler osea que en esta plataforma se permiten registrar alquileres y ademas realizar tareas extra

### Respecto a las características del aplicativo tenemos

Multiempresa, esto se refiere a que el mismo aplicativo puede ser utilizada por clientes de distintas empresas y los clientes solo podrán acceder a la información referente a su empresa 

Gestión centralizada porque en una misma plataforma se pueden realizar tareas varias tareas útiles para una empresa de alquiler, como registrar alquileres, reservas o consultar el inventario

Alta disponibilidad, esta es una característica centrada principalmente en el hosteo de la aplicación porque el aplicativo debe de estar disponible constantemente para que las empresas puedan realizar su trabajo 

Interfaz intuitiva, se creo una interfaz coherente que le indica a los usuarios con una simple vista el funcionamiento de esta 

Automatización de tareas repetitivas, esto se refiere a la automatización de tareas de realización de informes que si se realizan de forma manual requieren de una persona para juntar los datos y organizarlos pero que gracias a la automatización podrían ocurrir en segundos solo realizando la petición al aplicativo 

### Respecto a las ventajas 

tenemos un diseño modular que hace mas sencillo escalar las funcionalidades de los módulos 

mejores experiencia de trabajo y ahorro de tiempo porque se reduce la carga de trabajo y la probabilidad de cometer errores

Mayor trazabilidad, esto ocurre naturalmente debido a que todos los registros se almacenan en un mismo lugar, lo que previene inconsistencias y genera un único sitio de verdad para obtener información como el inventario 



## Modulos

### Empresa

se pueden crear empresas con sus campos
se puede listar las empresas registradas y realizar diferentes filtrados
se puede exportar la lista de usuarios en varios formatos 
se pueden editar las empresas existentes
se pueden observar las sucursales de una empresa 

### Productos

ver catalogo de productos
agregar producto al catalogo 
editar productos del catalogo

crear y editar categorias 

asignar, listar, editar y eliminar precios para los productos del catalogo 

observar el stock 

### Autenticación

crear usuarios

editar usuarios

listar y filtrar
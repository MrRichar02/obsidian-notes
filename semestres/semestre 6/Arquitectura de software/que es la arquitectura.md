[[Indice arquitectura de software]] para ir al indice

la arquitectura se encarga de razonar y organizar diferentes estructuras para pasar de una definición abstracta a algo concreto, las estructuras son conjuntos de elementos y se pueden organizar en 
categorías, las cuales son : component-and-connector, Module y Allocation, existen muchos tipos de estructuras pero no todos son estructuras arquitectónicas,  ya que deben de cumplir que 
aporten al razonamiento del sistema y sus propiedades, el razonamiento se refiere a que la estructura tenga un atributo que sea importante para los interesados en el producto, estos atributos 
dependerán del sistema que se este desarrollando 

La arquitectura es una abstracción ya que no toma todo el contenido de las estructuras que considera importantes, solo toma lo que afecta al sistema, con el objetivo de hacer mas simple la compresión
del sistema, no es tan importante conocer cada detalle del sistema sino que la arquitectura sea fácil de comprender 

un sistema siempre tendrá una arquitectura, por el contrario no todos los sistemas tendrán una documentación de esta arquitectura 

## Arquitectura del sistema

Se encarga de todo lo relacionado con hardware, software y humanos del sistema, esta describe como se realizan las conexiones, la estructura de las funcionalidades y como se relacionan los procesos
esta arquitectura nos puede dar detalles del sistema como su consumo energético y su peso 

## Arquitectura de la empresa

Se encarga de definir como se comunicarán los sistemas de la empresa tanto entre esos mismo sistemas, como a sistemas externos, también se preocupan por como se van a utilizar los sistemas y los
estándares que estos tendrán 

## Tipos de estructuras 

### Component-and-connector

Se refiere a todos los elementos que afectan al sistema en la ejecución del sistema, los components son aquellos elementos que afectan al sistema gracias a su comportamiento en la ejecución, estos 
son por ejemplo servicios o servidores, mientras que los connectors se encargan de proveer una manera en que los components se puedan comunicar, estos son llamados de retorno y procesos de 
sincronización de operadores.

Estas estructuras se encargan de proveernos información acerca del sistema al momento de su ejecución, con esta información podemos concluir cosas como el rendimiento o la seguridad del sistema 

### Module

Este tipo de estructuras divide en varias módulos un sistema estos módulos son en si unidades de implementación del código, este tipo de estructuras trata a cada elemento como un modulo, cada
modulo tiene su responsabilidad y funcionamiento dentro del sistema, podemos relacionar módulos mediante generalización o especialización. Estas estructuras nos ayudan a conocer las 
responsabilidades de los módulos, como se relacionan entre si, en que dependen y el efecto que tendría modificar la responsabilidad de algún modulo 

### Allocation

Se encargan de definir relaciones entre estructuras relacionadas al software y las que no, esto nos ayuda a definir cosas como los directorios donde se organizan los archivos en etapas del desarrollo, o 
los test que se realizan al  software

## Estructuras de tipo module útiles

### Decomposition 

Esta estructura almacena la información de como se relacionan los modulos entre si, donde la relación que se usa es "es un submodulo de", estos módulos permiten a los arquitecto realizar 
modificaciones a la arquitectura para probar diferentes módulos y como se pueden relacionar 

### Uses 

Esta estructura nos ayuda a crear relaciones entre los módulos, en este caso la relación que vamos a utilizar es si el modulo usa otro, con esto podemos verificar cosas como que si un modulo necesita
de otro para trabajar correctamente, lo que nos ayuda a diseñar sistemas escalables y a confirmar que partes del sistema pueden ser expandidos para añadir funcionalidades 

### Layer 

En esta estructura se conoce a los módulos como layers, los layers son maquinas virtuales abstractas, que nos ofrecen funcionalidades a través de una interfaz administrada, los layers pueden utilizar
otros layers de manera administrada, aunque en algunos sistemas mas estrictos a cada layer se le define el único layer que puede usar

### Class o generalization

En esta estructura a los módulos se les llama clases, esta estructura busca formar relaciones entre estas clases, las relaciones que vamos a usar son, hereda de y es una implementación de, estas 
estructuras son útiles para ver cuando podemos reutilizar código y para incrementar las funcionalidades 

### Data model

Esta estructura describe la información de estructuras de data estáticas, para hacerlo utiliza entidades de data y sus relaciones, las entidades de data son como tablas con diferentes columnas para
su información y esas columnas podrían ser otras entidades de data y de ahí es donde podrían salir las relaciones

## Estructuras C&C

Estás estructuras aparecen cuando el código ha sido compilado y esta siendo ejecutados y nos ayudan a observar distintos aspectos del código cuando esta siendo ejecutado,

### Service

Las unidades en esta estructura son servicios que están operando entre ellos gracias a un mecanismo de coordinación de servicios, esta estructura es importante para diseñar sistemas compuestos de 
componentes que no se desarrollaron conjuntamente 

### Concurrency

Esta estructura nos permite observar si podemos y donde utilizar paralelismo, ademas de determinar donde se producen contenciones de recursos, las unidades en esta estructura son componentes y 
la forma en que se conectan entre si es usando conectores, los componentes se organizan en hilos lógicos con la idea de luego poder pasarlos a hilos físicos 

## Estructuras allocation 

Estas estructuras definen como los otros tipos de estructuras se complementan con el software 

### Deployment 

Esta estructura esta encargada de mostrarnos el software es asociado a los procesos de hardware y la comunicación entre elementos, los elementos son los elementos de software que generalmente 
son procesos de alguna estructura C&C, las entidades de hardware osea los procesos y los caminos de comunicación. Las relaciones en esta estructura son esta almacenado en y migra a, esto nos 
permite conocer donde reside nuestro software incluso si este tiene un lugar de almacenamiento dinámico osea que cambia. Esta estructura nos habla acerca de el rendimiento, seguridad, integridad y
disponibilidad de programa

### Implementation

Esta estructura muestra como elementos de software son almacenados en archivos durante las diferentes épocas de desarrollo, por ejemplo en la fase de testing o deployment, lo cual es útil al 
momento de la construcción del programa o el deployment


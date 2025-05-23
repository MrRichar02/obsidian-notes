## Modelamiento General de la arquitectura

Una arquitectura debería estar basada en capas lógicas (Layer Pattern), donde una de estas capas es la capa de modelo del dominio (Domain Model Layer), y ésta es la capa que buscamos que tenga el menor acoplamiento posible

Alta COHESION BAJO ACOPLAMIENTO

➢ Si la aplicación tuviera diferentes tipos de clientes de presentación y si ellos albergaran la lógica de aplicación, ésta estaría distribuida en cada capa cliente, dificultando bastante su mantención.

➢ Por todo esto se justifica el uso una capa de servicio sobre el modelo de negocio, que juega el papel de fachada (Facade Pattern).

➢ Es decir la capa de servicio se encarga de exponer los servicios necesarios en la aplicación hacia la capa de presentación.

➢ Modelo de dominio, modela el dominio en general, posee las reglas inherentes a este dominio y pueda ser reutilizado en distintas aplicaciones. Cada aplicación puede tener sus propias transacciones de negocio que hacen uso del dominio de una manera particular.

➢ La capa de Persistencia busca que el modelo del dominio no conozca la manera en que sus datos son persistidos o almacenados, en la capa de datos

## Guías de diseño en la arquitectura

- Establecer convenciones para poner nombres
- Utilice notación de interfaces siempre que pueda, dibújelas en el lazo izquierdo de los diagramas y solo las que sean relevantes
- Nombre las interfaces al inicio con la leta I (mayúscula) seguido del nombre.
- En lo posible utilice herramientas CASE lo más completas posibles.
- Modele las dependencias de izquierda a derecha y la herencia de abajo (clase derivada) hacia arriba (clase base)
- Lea la documentación relacionada a UML 2.0

## Descripción con UML diagramas de modelado estructural

• Los diagramas de modelado estructural definen la arquitectura estática de un modelo, es decir aquellos elementos independientes del tiempo.

• Representan conceptos significativos de una aplicación, pueden incluir conceptos abstractos, del mundo real, o bien de la implementación, como: clases, objetos, interfaces, componentes físicos y relaciones y dependencias entre elementos

• Diagramas de paquetes: se usan para dividir el modelo en contenedores lógicos o paquetes que describen las interacciones entre ellos a alto nivel.

## Paquetes

Es una colección de elementos de un modelo

En un paquete podemos empaquetar clases, subsistemas, Componentes

Son contenedores de clases utilizados para mantener el espacio de nombres de clases dividido en compartimentos.

Cada paquete se une con otros a través de dependencias, que se representan con flechas de líneas discontinuas que van del componente dependiente al componente del cual depende

## Diagrama de paquetes y componentes

Cada paquete puede tener un diagrama de componentes para representar las clases que contiene internamente, similar a hacer un acercamiento o "zoom" al interior de cada uno de los paquetes

## Arquitectura con UML - Diagramas de modelado estructural

### Diagrama de componentes

usados para modelar estructuras complejas de alto nivel, usualmente construidas a partir de varias clases y proporcionan una interfaz bien definida.

Un diagrama de componentes tiene un nivel de abstracción más elevado que un diagrama de clase - usualmente un componente se implementa por una o más clases (u objetos) en tiempo de ejecución

### Diagramas de deployment

muestran la composición física de los artefactos en el mundo real.

### Diagramas de componentes

- Un componente representa una parte modular de un sistema que encapsula su contenido y cuya manifestación es reemplazable en su entorno.

- Los componentes son agregaciones de alto nivel de piezas más pequeñas de software, y proporcionan un bloque de construcción de caja negra a la construcción de software.

- Los componentes son considerados unidades autónomas y encapsuladas en un sistema o subsistema que proporcionan varias interfaces.

- Utilización de los diagramas de componentes

- Los diagramas de componentes pueden ser utilizados para modelar sistemas de software de cualquier tamaño y complejidad.

- La herramienta nos permite especificar un componente como unidad modular con interfaces bien definidos.

## Tipos de componentes

a.- Componentes de distribución
Son los componentes que conforman un sistema, como los programas ejecutables, los DLL, controles ActiveX, Java Beans, etc.

b.- Componentes de trabajo
Son los componentes con los que se crean los componentes de distribución, como los programas fuente, las bases de datos, etc.

c.- Componentes de ejecución
Son los componentes que, en el transcurso de la ejecución de un sistema, se crean en forma dinámica, como los índices que crean los motores de búsqueda, como resultado de alguna consulta.

## Clases de interfaces en los diagramas de componentes

- Un componente proporciona y requiere interfaces, que forman la base para cablear los componentes juntos, usando sus dependencias, o por medio de sus conectores.

- Una interfaz proporcionada es aquella que es implementada directamente por el componente.

- Una interfaz requerida es aquella diseñada por una dependencia del componente.

## Diagrama de Componentes

• Los componentes se diseñan de tal forma que puedan ser tratados tan independientemente como sea posible,

• Esos componentes y los subsistemas que ellos conforman, podrán ser reutilizados y sustituidos en forma flexible, conectándolos a través de sus interfaces.

• Así mismo, una vez instalados, esos componentes pueden ser reimplementados independientemente, cuando sea necesario actualizar las funciones de un sistema en producción.

• Notación: un componente se representa mediante un rectángulo con la palabra <\<component>>. Opcionalmente, en la esquina superior derecha hay un icono de componente:

[[Indice arquitectura de software]]

[[temario clase 1]]
## arquitectura:

puede partir de algo como esto

![[Pasted image 20250318160251.png]]
varias capas con cosas que las unen

una arquitectura es un modelo que contiene componentes y sus relaciones entre ellos

define un marco para el diseño y desarrollo de software, como un esqueleto lleno de patrones de diseño que llenamos con nuestro código

un plano regulador del sistema en conjunto

nos da guías de diseño, que son basados en diseños que han funcionado antes

nos permite enfocar esfuerzos para la implementación 

se concentra en los requerimientos no funcionales, por ejemplo la seguridad, rendimiento y usabilidad 

los requisitos funcionales se satisfacen mediante el modelado y diseño de la aplicación

## no arquitectura

Una normativa madura(aún esta evolucionando)

igual en la academia que en la industria (son diferentes)

diseño de software con UML (UML no es todo)

ocurre en algún punto la elicitación de requerimientos y la especificación de casos de uso, o entre éstos y el diseño (el proceso de la arquitectura cubre todas las fases)

Naturalmente vinculada a una metodología (RUP) (se puede adaptar a todas las metodologías de desarrollo por ejemplo AGILE)

NOTA: una solución de software puede contar con mas de una arquitectura

Naturalmente relacionada con modelado orientado a objetos (existen otros paradigmas como web services, microservicios, SOA, etc)

Las herramientas arquitectónicas generan el código de la aplicación (las herramientas CASE solo son un soporte)

Herramientas CASE: son las herramientas que usamos para crear los planos del sistema CASE significa herramientas asistidas por computadora 


## IEEE std 1471

una arquitectura se compone de componentes, sus relaciones entre si, el ambiente y los principios que guían el diseño y la evolución

## Libro guía

es la estructura de las estructuras de un sistema que están interrelacionados con los componentes del sistema

### Sub-sistema

es un conjunto de componentes colaborativos que buscan alcanzar una tarea clara

### Componente

Es una parte encapsulada del sistema de software, se comunican entre si por puntos de comunicación usando protocolos, también tenemos interfaces que exponen los métodos del componente

### Descomposición y refinamiento 

los componentes se pueden descomponer en sub-componentes, esto ocurre si deseo conocer mas detalles de mi componente, los componentes suelen conocerse como caja negra y los sub-componentes como caja blanca 

### Interfaces

Application programming interface(API) frontera compartidas entre dos unidades funcionales compartidas

un contrato al que se deben atener los componentes

service provider interface (SPI) son el conjunto de protocolos, contratos e interfaces dentro de una biblioteca, nos permite ampliar funcionalidad o reemplazarlas sin tener que modificar los componentes principales


Las API se suelen usar entre componentes internos y los SPI con servicios externos

## Otra definición de Arquitectura de SW

una arquitectura es el conjunto de decisiones significativas acerca de la organización de un sistema de SW, la selección de los elementos estructurales y sus interfaces con las que el sistema se componen, junto con el comportamiento como lo especifica la colaboración de estos elementos, la composición de estos elementos estructurales y comportamiento en sub-sistemas progresivamente más grandes y el estilo arquitectónico que guía a esta organización

## Bloques estructurales:

![[Pasted image 20250318164106.png]]

estos elementos son las capas que va a soportar otras capas dentro del sistema, de estos elementos vienen los stacks tecnológicos

![[Pasted image 20250318164226.png]]

![[Pasted image 20250318164340.png]]

un ejemplo de un stack sería LAMP

![[Pasted image 20250318164400.png]]


## Cosas comunes en las definiciones de Arquitecturas de SW

Casi todas tienen en común la inclusión de componentes

## otra definición

la arquitectura trasciende los algoritmos y estructuras de datos, son factores estructurales que incluyen:

- organización general y estructural global de control
- protocolos de comunicación, sincronización y acceso de datos
- asignación de responsabilidades a elementos de diseño
- distribución física
- composición de elementos de diseño
- escalamiento y rendimiento
- la selección entre alternativas de diseño

## Conectores

![[Pasted image 20250318165418.png]]

los componentes se enlazan con pipes que son canales de comunicación

existen varios conectores de bajo nivel

podemos tener comunicaciones sincrónica, asíncrona, peer-to-peer y event broadcast

sincrónica: hacemos una petición a un proceso y el nos regresa una respuesta, pero solo podemos hacer una petición cuando el proceso mande la respuesta

asíncrona: hay una serie de eventos desde el servidor, cuando se hace el evento se enviar la respuesta al usuario sin que el deba enviar una petición. También un proceso puede recibir varia peticiones y el proceso podrá responder y procesar las peticiones sin que halla un bloqueo, un ejemplo de esto sería AJAX, SSE(server send event), Async, web sockets, message brokers. Esto se usa en aplicaciones que necesitan una actualización en tiempo real

Peer-to-Peer:  un sistema de nodos conectados entre si por una red similar al internet, podemos descargar cosas de varias fuentes de la red si este esta en varios peers, un peer puede tener el rol de servidor y cliente a la vez. Estos tipos de sistemas son descentralizados 

Broadcast de eventos: es similar a la asíncrona, hay varios clientes subscritos a un servicio y cuando hay un evento envió un broadcast a todos los subscriptores a la vez 

los conectores pueden codificarse en lenguajes diferentes a los que usan los componentes 

## Filosofía de shaw 

componentes: unidades previamente compilada, (modulo, estructura de datos, filtros) que son identificador por interfaces

contectores: RPC(remote procedure call), eventos, tuberias. Se encargan de mediar la comunicación entre componentes y especificados protocolos 

![[Pasted image 20250321160826.png]]

## Elementos conectores

cada sistema tiene elementos conectores, que se encargan de comunicar las capas entre si sin importar la cantidad de capas que tengamos 

![[Pasted image 20250321160923.png]]

las librerías de terceros nos dan servicios compartidos que proveen sercivios core como estructuras de datos, logging, debugging y otros servicios 

## Otra definición de arqui SW de Boehm

una AS comprende: una colección de componentes de SW y de sistema, conexiones, restricciones 


## Elementos a emplear con las A.S 

### Requisitos no funcionales ISO 25010

![[Pasted image 20250321161254.png]]

## Principios de una buena Arquitectura

### Útil

cumple con los requisitos de calidad y funcionalidad

### Estable

Fiable, maduro, mantenible

### Agraciado

Diseño bien estructurado, gran experiencia de usuario


## Beneficios de una A.S

### Manifiesta las decisiones de diseño tempranas
- Define restricciones de implementación
- inhibe o activa los atributos de calidad del sistema
- Facilita razonar acerca del manejo del cambio
- Ayuda a la evolución del prototipado
- Alcanza más exactitud en estimación de costos y agenda de proyectos de software

### Las arquitecturas se usan como un modelos reusable y transferible
Se puede reutilizar o adaptar arquitecturas que funcionaron bien anteriormente en otros proyectos 
- Las líneas de productos de software comparten una arquitectura en común
- Los sistemas se pueden construir usando grandes y extensos elementos de desarrollo
- Menos es más: vocabulario restringido de alternativas de diseño
- Una arquitectura permite el desarrollo basado en plantillas (templates)
- Una arquitectura puede ser la base para el entrenamiento de nuevos miembros del equipo de desarrollo 

## Problemas de falta de Arquitectura

- Rendimiento inadecuado de las apps
- Mantenimiento costoso
- Diseño inadecuado para evolucionar
- Reutilización limitado( el arquitecto  particiona el trbajo de tal manera que cada ingeniero :( hasta ahi llegue))
- Proyectos ineficientes
- Afecta la calidad de los sistemas de software
- No hay interoperabilidad

Partes de una arqui

![[Pasted image 20250321171637.png]]

RIA -> Rich internet application, es como una app de escritorio pero en el navegador 

## Métodos de autenticación 

![[Pasted image 20250321171200.png]]

## Catching

información que no se va a modificar y se puede almacenar durante la sesión de un usuario para hacer interacciones más rápidas 
## Patrón de diseño

Un patrón es una solución probada que se puede aplicar con éxito a un determinado tipo de problemas que aparece ocn frecuencia en un contexto especifico.

Esqueleto de la aplicación básica que el diseñador ha de adaptar a sus necesidades

Un patrón en software es una colección de objetos que incluye:
- Relaciones entre estos objetos
- Desarrollados para resolver un problema concreto
- Se ha comprobado que funcionan bien (han sido testeados)

Los patrones de software permiten establecer un lenguaje común para expresar y comunicar experiencias, diseños y buenas prácticas

## Qué es un patrón de software?

Un patrón describe un problema de diseño recurrente, que surge en contextos específicos de diseño, y presenta un esquema genérico probado para la solución de este. El esquema de la solución describe un conjunto de componentes, responsabilidades y relaciones entre de éstos, y formas en que dichos componentes colaboran entre si.

## Catalogo de patrones

### POSA

#### Nombre 

Pattern Oriented Software Architecture

#### USO

Definición de la arquitectura

#### Referencia

Buschmarnn, 1996

### PEEA

#### Nombre 

Pattern of Enterprise Application Architecture

#### USO

Definición de la arquitectura

#### Referencia

Fowler, 2003

### GRASP

#### Nombre 

General Responsibility Assignment Software Patterns

#### USO

Paso del análisis al diseño

#### Referencia

Larman, 2004

### GoF

#### Nombre 

Design Patterns (Gang of Four)

#### USO

Diseño

#### Referencia

Gamma, 1995

### J2EE

#### Nombre 

J2EE Patterns 2° Edition

#### USO

Diseño

#### Referencia

Alur, 2003

### Idioms

#### Nombre 

Patrones de código

#### USO

Codificación

#### Referencia

Buschmann, 1996

## Pattern-Oriented Software Architecture: A system of Patterns

• También conocido como The POSA Book
•  Fue el primer libro en hacer una clasificación de patrones
•  Patrones arquitectónicos Diseño
•  Patrones de diseño Diseño
•  Idioms Implementación

### Patrones arquitectónicos

•  Aconsejan la arquitectura global que debe seguir una aplicación
•  Ej.: El patrón Model-View-Controller (MVC) aconseja la arquitectura global que debe tener una aplicación interactiva

### Patrones de diseño

• Explican cómo resolver un problema concreto de diseño
• El patrón “Data Access Object” (DAO) permite abstraer y encapsular los accesos a un repositorio de datos (ej.: BD relacional, BD orientada a objetos, ficheros planos, etc.)

### Idiomas

• Explican cómo resolver un problema particular de implementación con una
tecnología concreta
• Ej.: ¿Cómo comparar objetos correctamente en Java?
• Correcta redefinición de equals() y hashCode()

## Architectural styles

•Refer to the overall design and organization of a software system, and the principles and patterns that are used to guide the design.

•These styles provide a general framework for the design of a system, and can be used to ensure that the system is well-structured, maintainable, and scalable.

### Microservices

where the system is built as a collection of small, independent, and loosely-coupled services

### Event-Driven

where the system reacts to specific events that occur. Async Communication

### Layered

where the system is divided into a set of layers, each of which has a specific responsibility and communicates with the other layers through well-defined interfaces.

### Service-Oriented

where the system is built as a collection of services that can be accessed over a network

### Data-Centric

where the system is focused on the storage, retrieval and manipulation of data, rather than the processing of data.

### Component-Based

where the system is composed of reusable and independent software components

### Domain-Driven

where the system is organized around the core business domain and business entities.

## Estilos Arquitectónicos vs Patrones de diseño

• Muchos estilos arquitectónicos son muy conocidos desde hacer tiempo por la comunidad de Ing. De Software.

• Ampliamente usados en aplicaciones compleja o de misión critica.


| Estilo Arquitectónico                   | Patrón de diseño                                        |
| --------------------------------------- | ------------------------------------------------------- |
| Pocos                                   | Muchos                                                  |
| Organización de sistemas de gran escala | Soluciones de diseño de escala pequeña. Son localizados |

## Architectural patterns

• Architectural patterns are a set of solutions that have proven their reliability in specific types of software systems.

• They provide a common vocabulary and set of best practices for designing and building software systems, and can help developers make better design decisions.

## POSA (Pattern-Oriented Software Architecture)

### Dataflow Based

- piplines and filters
- Batch

### Data-centric Systems (repositories)

- Blackboard
- Databases

### Invocación Implicita (eventos)

### Layered

- Client / Service
- Layers
- 3 or N layers

### Object Oriented (components)

### Microkernel

### MVC Pattern (MVP, MVVM, etc)

### Message Queues and Streams

### Distributed Systems (Brokers)

- Corba, DCOM, COM+, RPC, Protocol Buffers, .NET Remoting, Sockets, WebSockets, etc

### Service Oriented (SOA, Microservices, Serverless, WebServices)

## Arquitectura Filtro-Tubería (Pipes & Filters)

• Incorporada como elemento base en Unix (McIlroy)

• Hoy con un significado mucho más amplio

• Es apropiada para sistemas que implementan transformaciones de datos en pasos sucesivos.

### Filtros y Tuberías (Pipes & Filters)

#### Descripción

• Cada componente tiene un conjunto de entradas y un conjunto de salidas.
• Un componente lee entradas y las transforma en salidas

#### Restricciones:

• Los filtros deben ser independientes.
• No deben compartir estado con otros filtros.

Ventajas

• Permite entender el sistema global en términos de la combinación de
componentes
• Soporta de buena manera la reutilización.
• Los filtros son independientes de sus vecinos
• Facilidad de Mantenimiento y mejora
• Soportan la ejecución concurrente
• Facil para reemplazar filtros;
• Interaciones entre componentes faciles de analizar.

Desventajas

- No aconsejable para cuando se necesita interactividad
-  Problemas de rendimiento ya que los datos se transmiten en forma completa entre filtros
- El patrón puede resultar demasiado simplista, especialmente para orquestación de servicios que podrían ramificar la ejecución de la lógica de negocios de formas complicadas.
- No maneja con demasiada eficiencia construcciones condicionales, bucles y otras lógicas de control de flujo. Agregar un paso suplementario afecta la performance de cada ejecución de la tubería.
- Eventualmente pueden llegar a requerirse buffers de tamaño indefinido,
- La independencia de los filtros implica que es muy posible la duplicación de funciones de preparación que son efectuadas por otros filtros

## Sistemas basados en repositorios

### Descripción

• Existen dos tipos de componentes
• Una estructura central de datos (representa el estado del proceso)
• Componentes independientes (operan en función del depósito de datos)
• Las interacciones entre el repositorio y los demás componentes es variable:
	• La entrada de los datos es seleccionada por los componentes
	• El estado de los datos del repositorio selecciona el proceso a ejecutar la pizarra)

• Ejemplos: Reconocimiento de patrones y de la voz (blackboard); editores de
sintaxis y compiladores

### Ventajas

- Solo un conector (blackboard) para cualquier usuario.

- Posibilita la integración de agentes.

- Adecuado para la resolución de problemas no deterministas.

- Se puede resumir el estado de conocimiento en cada momento del proceso

### Desventajas 

- Estructura de datos común a todos los agentes

- Si existen muchos agentes puede formarse un cuello de botella.

- Problemas de carga a la hora de chequear y vigilar el estado de la pizarra.

## Patrón POSA. Layers

Layers ayuda a estructurar las aplicaciones que se pueden descomponer en grupos de subtareas en la que cada grupo de subtareas se encuentra en un nivel particular de abstracción. Buschmana, et al 1996

• Las 4 capas más comúnmente encontradas de un sistema de información general son las siguientes.

• Capa de presentación (también conocida como capa UI )

• Capa de aplicación (también conocida como capa de servicio )

• Capa de lógica de negocios

• Capa de acceso a datos (también conocida como capa de persistencia )

## Patrones POSA. Broker

Broker puede ser usado para estructurar sistemas de software distribuidos con componentes desacoplados que interactúan por invocaciones de servicios remotos. Un componente corredor es responsable de coordinar la comunicación, tales como solicitudes de expedición, así como para la transmisión de resultados y excepciones

### Tecnologías y modelos

#### Tecnologías

Cómo se realiza la programación

- Paso de mensajes
	- Berkeley sockets
	- Java sockets
- Llamadas a procedimientos remotos
	- Sun RPC
- Objetos distribuidos
	- Java RMI
	- General inter-ORB protocol (GIOP)
	- RMI - IIOP
	- SSL interORB Protocol (SLLIOP)
	- HyperText InterORB Protocol (HTIOP)
	- CORBA
	- Protocol Buffers / Proto3 / gRCP (Google)
	- Apache Thrift (Facebook)
	- Microsoft Bond Protocols
	- RDA -> Remote Data Access
	- ODATA (Open Data Protocol - Microsoft OASIS)
	- PartiQL (Amazon)
	- COM / COM+ / DCOM
	- .NET Remoting
	- tRPC (2021)
- WebSockets
- Servicios Web
	- SOAP
	- RESTFul
	- GraphQL(Facebook)
- Microservicios:
	- API Gateway
	- AQM

### Modelos

Cómo se diseña el servicio

- Modelo Cliente/Servidor
- Modelos con intermediario
	- Modelo proxy/cache
	- Modelo multinivel
- Peer-to-peer

## Patrones POSA. PAC (Presentation-Abstraction-Control)

PAC define una estructura para los sistemas interactivos en forma de una jerarquia de agentes cooperantes. Cada agentes es responsable de un aspecto especifico de la funcionalidad de las aplicaciones y consta de presentación, abstracción y control. Esta subdivisión separa los aspectos de la interacción humano-computadora del agente de su núcleo funcional y su comunicación con otros agentes. Buschmann, et al. 1996

## Patrones POSA. MicroKernel

MicroKernel se aplica a los sistemas de software que debe ser capaz de adaptarse a los cambio en los requisistos del sistema. Separa un núcleo funcional mínimo de la funcionalidad extendida y partes especificas del cliente. El miconúcleo también sirve como un socket para conectar estas extensiones y coordinar su colaboración. Buschmann, et al. 1996

## Evolución C/S

Se fue pasando de
- Monolítica
- C/S
- C/S 3 capas
- C/S N Capas
- SOA
- MS / Serverless

## Evolución de la tecnología

### Arquitecturas monoliticas

➢ Mainframes de gran tamaño: En 1946 ENIAC.
➢ Superficie de 160 m2
	➢ Peso 30 toneladas
	➢ Procesamiento de 30.000 instruciones / seg
	➢ Sistemas Operativos Propietarios
➢ Solo Texto
➢ Terminales Brutas con solo teclado y monitor.

## Evolución de la arquitectura

- Monolitico
- Estructurado
- Client / Server
- 3-Tier, N-Tier
- Objetos distribuidos
- Componentes
- Web Services
- Servicios
- Microservicios

### Servicios

• Relación entre procesos que corren en máquinas diferentes.
	• Proceso SERVIDOR: Proveedor de servicios.
	• Proceso CLIENTE: Consumidor de servicios.
	• Hay una separación funcional clara basada en la idea de servicio.

### Recursos compartidos

• Un servidor puede servir a varios clientes al mismo tiempo, regulando el
acceso de éstos a recursos compartidos. Concurrencias

## Cont

### • Protocolos asimétricos
	• Relación 1:m entre servidor y cliente.
	• Los clientes siempre inician el diálogo.
### • Transparencia de localidad
	• El servidor es un proceso que puede residir en la misma máquina que el cliente o en otra máquina en una red.
	• Un programa puede ser servidor, cliente o jugar ambos papeles.
### • Independencia de Plataforma
	• El software cliente/servidor deberá ser independiente de la plataforma.

### • Intercambio basado en mensajes
	• Clientes y servidores interactúan con base en un mecanismo de paso de mensajes.
	• Generalmente un mensaje es una solicitud o una respuesta.
### • Encapsulamiento de Servicios
	• Servidor especializado.
	• Las peticiones enviadas por los clientes indican el servicio requerido, y el servidor determina cómo se responderá a la solicitud.
	• Los servidores pueden actualizarse, sin afectar a los clientes siempre y cuando la interfaz de mensajes no cambie.

### • Crecimiento
	• Los sistemas cliente/servidor crecen horizontal y verticalmente.
	• Crecimiento horizontal: Adicionar o eliminar estaciones de trabajo clientes con un impacto pequeño en el desempeño del sistema completo.
	• Crecimiento vertical: cambio a servidores más rápidos y de mayor capacidad.
### • Seguridad
	• El código y los datos del servidor tienen un mantenimiento centralizado, lo cual es más económico y seguro.

## Modelo Cliente / Servidor 3 capas

### Nueva capa: Dominio

• Aparece una nueva capa: la de Dominio
•Debería obviar tanto la estructura de los datos como su ubicación
	• Permite describir las aplicaciones basándose únicamente en el dominio a modelar
	• También posibilita cambiar la estructura física de la base de datos y su ubicación sin afectar a las aplicaciones existentes

• La Tecnología de Objetos representa el mejor modo de
implementar (modelar) dicha capa

## Arquitectura de n capas

• A la hora de la verdad (en el diseño detallado), las arquitecturas en tres capas suelen separarse aún más
• Así, es posible diferenciar entre lógica de presentación y de aplicación
	• De un lado, estrictamente la interfaz de usuario
	• De otro, los servicios utilizados tanto por la capa de presentación como por el dominio

+ Bajo costo de administración de clientes.
+ Alta accesibilidad.
+ Alta flexibilidad.
+ Alta disponibilidad y tolerancia a fallos.
+ Alta escalabilidad.
+ Independencia de DB

### Ventajas de N-Capas

• Reutilización
	• La aplicación está formada por una serie de módulos que se comunican a través de interfaces, y que cooperan entre sí para dar lugar al comportamiento deseado
	• Idealmente, se trataría de objetos independientes que podrían ser empleados en otras aplicaciones

• Facilidad de mantenimiento
• Eficiencia en el acceso a los datos y en el uso de la red
• Posibilita la especialización de los desarrolladores

## Ambientes

- Uniprocesador
- Multiprocesador simétrico
- Cluster
- Procesamiento Masivo paralelo

## Middleware

• Es la herramienta o conjunto de herramientas que nos permitirán gestionar y coordinar los mecanismos de comunicación.

• Actuan como intermediarios con otros componentes de SW

• Ejemplo si se hace la petición de una página web desde un browser en el cliente, el middleware determina la ubicación y envía una petición para dicha página.

• El servidor Web, interpreta la petición y envía la página al software intermedio, quien la dirige al navegador de la máquina cliente que la solicitó.

• Independiza el servicio y su implementación, del S.O. y protocolos de comunicaciones

• Permite la convivencia de distintos servicios en una misma máquina
- Implementa Modelo OO: CORBA

### Generalidades

#### Comunican 2 sistemas:

• Drivers a DBMSs.
• Acceso a DBMS desde un programa u otro DBMS.
• Remote Procedure Call (RPC, RMI, Remoting).
• Invocación a procedimientos remotos como si fueran locales al programa.
• Web Services.
• Invocación a procedimientos a través de HTTP.

#### Comunican múltiples sistemas:

• Message Oriented Middleware (MOM). Puede emplearse
	• Advanced Message Queuing Protocol (AMQP)
	• OMG - Data Distribution Service (DDS)
	• Streaming Text Oriented Messaging Protocol (STOMP)
	• JMS
	• Extensible Messaging and Presence Protocol (XMPP) – Facebook, Whatsapp, etc.

• Envío de mensajes entre aplicaciones.
• Object Request Brokers (ORB).
• Invocación a procedimientos y propiedades de objetos.

### Midleware como infraestructura

• Java (EJB, RMI, CORBA, etc.), .NET, son infraestructuras middleware.
• Capa software ejecutable que me permite abstraernos de aspectos cotidianos en la programación de sistemas distribuidos
	• Primitivas de comunicación basada en RPC, RMI, ...
	• Soporte a transacciones
	• Gestión del ciclo de vida de los objetos/Procesos
	• Nos facilitan la definición de la lógica de negoció
	• ...
• ¡Son plataformas ejecutables con un modelo de programación concreto!

### Existen dos tipos:

#### Software intermedio general.

•Servicios generales que requieren todos los clientes y servidores, por ejemplo:

	➢software para las comunicaciones usando el TCP/IP
	➢ software parte del sistema operativo que, por ejemplo, almacena los archivos distribuidos,
	➢software de autenticación,
	➢el software intermedio de mensajes de clientes a servidores y viceversa.

#### Software intermedio de servicios

• Software asociado a un servicio en particular, por ejemplo:
	➢software que permite a dos BD conectarse a una red cliente/servidor (ODBC: Conectividad abierta de BD),
	➢software de objetos distribuidos, por ejemplo la tecnología CORBA permite que objetos distribuidos creados en distintos lenguajes coexistan en una misma red (intercambien mensajes),
	➢software intermedio para software de grupo,
	➢software intermedio asociado a productos de seguridad específicas (Conexiones Seguras: Sockets), etc.

### Clasificación por niveles

Se distinguen 2 niveles:

• Middleware de Bajo Nivel (Servicios Tecnológicos) Se encargan del transito de servicios básicos hacia el cliente.

• Middleware de Alto Nivel(Servicios de Aplicación) Se encargan del manejo de servicios de infraestructura y de aplicación

## Clasificación de Middleware

### Middleware bajo nivel

### Middleware de base

Estándares y servicios asociados, que sirven de soporte para la construcción del resto del middleware

- CORBA
- COM / COM+ / DCOM
- EJB / J2EE
- .NET

### Middleware de comunicaciones

Proporciona el medio de comunicación para que las aplicaciones puedan conversar entre si

- HTTP
- RMI-IIOP
- SOAP
- RPC

### Middleware de base de datos

Enmascara la complejidad de acceso a la base de datos escondiendo los detalles de implementación de cada uno

- ODBC
- JDBC
- OCI

### Middleware de aplicación

Permite el arranque, extensión, e integración de otras aplicaciones

- CGI
- Servlets/JSP
- PHP
- ASP
- ISAPI/NSAPI

### Middleware de alto nivel

### Servidores web

Servicios de publicación de contenidos

- Apache
- Netscape Server
- IIS
- OmmiHTTPD
- Sun Server
- Sambar Server
- Xitami
- iPlanet Server

### Servidores de transacciones 

Garantiza transacciones ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad) en el procesamiento distribuido

- BEA's Tuxedo
- IBM - CICS
- Transarc0s Encima
- MTS

### Servidores de componentes

Contenedores de objetos que prestas servicios a través de una interface definida

- Tomcat
- Microsoft
- Servidor de componentes COM
- NET Remoting

### Servidores de aplicaciones

Servicios de infraestructura y aplicación. Responden a una arquitectura lógica definida, por genreal J2EE

- OAS(IAS)
- Websphere
- Jboss
- BEA-Weblogic
- Jonas
- Iplanet

### ¿Cuáles son los servicios de infraestructura?

• Los servicios de infraestructura típicos incluyen:
• Messaging (Mensajería y Notificaciones).
• Pooling.
• Caching.
• Clustering.
• Naming.
• Logging.
• etc.

### Servicios de un servidor de aplicaciones

Gestión de transacciones.
Modelo de interoperabilidad para componentes.
Intercambio de datos.
Colas de mensajes.
Servidor HTTP para clientes Web y clientes móviles.
Almacenamiento temporal de base de datos y web.
Herramientas de administración.

### Los servidores de App permiten

• Creación de páginas Web dinámicas
	• (ASP en Microsoft o JSP en Java)
• Componentes que pueden encapsular la lógica del negocio
	• (COM en Microsoft o EJB en Java)
• Soporte de transacciones
• Acceso a la aplicación desde clientes HTTP
• Soporte para invocar métodos remotos
• Manejo de seguridad
• Uso de SSL y conexión con Bases de Datos
	• (ODBC en Microsoft o JDBC en Java)

### Servidor de aplicaciones

• Todos los servicios simplifican el desarrollo de SW.
• Se ubica siempre entre los clientes o usuarios finales y el servidor de BD

### Características servidor de aplicaciones

La mayoría de servidores de aplicaciones te permiten hacer algunas de las siguientes tareas.

• Presentar Contenido Dinámico
• Administrar un Sitio Web
• Construir un Sistema de Manejo de Contenidos
• Seguridad y Manejo Correcto
• Brindar Servicios de red
• Integración de diversos sistemas
• Proveen Escalabilidad
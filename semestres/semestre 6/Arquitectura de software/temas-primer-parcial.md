# Primera presentación 
## Patrones

- Patrones de diseño(GoF - GRASP)
- Patrones arquitectónicos(POSA)
- Patrones organizacionales(Coplien)

## Métodos heterodoxos

XP, extreme programming, Scrum, Kanban, LEAN, Evo, DSDM Dynamic Systems Development Models, RUP, AM, Crystal, LD, ASD

## Otros

- refactoring
- functional programming, AOP, SOA, Cloud computing, Mobile apps, software products lines/software factory, chatgpt/GH Copilot, LLM, DevOps, Semantic Web, Web3, Blockchain

## SOA(arquitectura orientada a servicios)

## Cloud

### Capas

- infrastructure as a service(IaaS)
- platform as a Service(PaaS) 
- backend as a service(BaaS)
- software as a service(SaaS)

### Modelos

- Publicas
- Privada
- Hibridas
- Cloud Native
- plataformas multinube
- XaaS

## Design

### Architectural Design

- Physical Architecture
- Logical Architecture
- Data Module

### Detailed design

- Detailed module design
- System navigation model
- User interfaces
- Data dictionary
- Algorithm design

### El proceso de diseño 

#### Salidas de diseño

- Diseño de datos: Transforma el dominio de la información creado durante el análisis en estructuras de datos.
- Diseño de Arquitectura: Define las relaciones entre los principales componentes estructurales del software.
- Diseño de procedimientos: Transforma los componentes estructurales en descripción de procedimientos de software.
- Diseño de Interfaces: Establece las bases y mecanismos de interacción entre persona y máquina.

### Design Process

- The design is where software quality is generated.
- Without design you run the risk of building an unstable system that will “fail” or “crash” if changes are made.

## Software Architecture

• What is an architecture?
• “We're not sure, but we know it when we see one.” IEEE-1471

• There is no single definition.
• SEI – Carnegie Mellon University Software Architecture Definitions
• https://insights.sei.cmu.edu/documents/2544/2010_010_001_513810.pdf

• Many professionals compare the Architecture with "abstraction of structures".
• " Architecture is all you need to know about a system that is not contained in
the code. " (G. Booch)

## Qué es una Arquitectura?

- Modelo que contiene un conjunto de Componentes y sus relaciones.
- Define el marco para el diseño y desarrollo de Software
- Plano Regulador.
- Da Guías de Diseño.
- Permite enfocar esfuerzos para la implementación.
- Se concentra en requerimientos no funcionales
- Los requerimientos funcionales se satisfacen mediante modelado y diseño de la aplicación

## Qué no es una Arquitectura?

• Una normativa madura (Aún se encuentra en evolución)
• Igual en la academia y en la industria (Diferentes)
• Diseño de software con UML (No lo es todo)
• Ocurre en algún punto entre la elicitación de requerimientos y la especificación de casos de uso, o entre éstos y el diseño (El proceso de la Arquitectura cubre todas las fases)
• Naturalmente vinculada a metodología(RUP) (Se puede adaptar a todas las metodologías de desarrollo por ejemplo AGILE).
• Naturalmente relacionada con modelado Orientado a Objetos (Existen otros paradigmas como web services, microservicios, SOA, etc).
• Las herramientas arquitectónicas generan el código de la aplicación (Las herramientas CASE solo son un soporte).

## Definición Arquitectura

•Definition: (IEEE Std 1471): Software Architecture is the fundamental organization of a system represented by its components, the relationships between them and the environment and the principles that guide its design and evolution.

### Subsystem

•  A subsystem is a set of collaborating components performing a given task
• A subsystem is considered a separate entity within a software architecture
•  It performs its designated task by interacting with other subsystems and components...

### Components

• A component is an encapsulated part of a software system
• A component has an interface
• Components serve as the building blocks for the structure of a system
• At a programming-language level, components may be represented as modules, classes, objects or as a set of related functions

### (DES) Composición y refinamiento

• Los componentes pueden descomponerse, a su vez, en sub-componentes según, por ejemplo:
• ‣ Tipos de datos importantes.
• ‣ Capas.

• ‣ Pieza más pequeña de funcionalidad auto- contenida.

... El refinamiento debe estar libre de redundancia

‣ Componentes de caja negra con fuertes dependencias→ agregados en un componente de caja blanca común.

### Interfaz/API (Application Programming Interface)

Interfaz ISO/IEC 2382:2015 "frontera compartida entre dos unidades funcionales, definida por varias características relativas a funciones, intercambios de señales físicas y otras características".

"Contrato" al que deben atenerse los componentes. Punto de acceso bien definido a un componente (o sistema). Aportar una descripción precisa y completa de las interfaces: ‣ Sintaxis, estructuras de datos, comportamiento frente a errores, características de calidad, tecnologías, protocolos, restricciones, semántica, ...

### SPI (Service Provider Interface)

• A diferencia de las API que se centran en definir las interacciones entre componentes, SPI es un conjunto de protocolos, contratos e interfaces dentro de una biblioteca o marco de software.

• SPI permite a los desarrolladores ampliar o reemplazar ciertas funcionalidades dentro de un sistema sin modificar sus componentes principales.

## Definición de Arquitectura de SW

- Booch, Rumbaugh, Jacobson 1999
•Una arquitectura es el conjunto de decisiones significativas acerca de la organización de un sistema de SW, la selección de los elementos estructurales y sus interfaces con las que el sistema se compone, junto con el comportamiento como lo especifica la colaboración de estos elementos, la composición de estos elementos estructurales y de comportamiento en subsistemas progresivamente más grandes y el estilo arquitectónico que guía esta organización (UML User Guide, Addison-Wesley 1999).


### Elementos Estructurales

- Librerías de terceros
- Librerías estándar del lenguaje de programación 
- Funcionalidad del sistema operativo 
- El propio código


## Definición de Arquitectura de software

Según Neal Ford, Mark Richards & Raju Gandhi: la arquitectura de software tiene 4 dimensiones en la que se define la forma física general y la estructura de un sistema de software

## Definición de Arquitectura de software

• Garlan & Shaw 1993
• Sugieren que es un nivel de diseño que trasciende algoritmos y estructuras de datos...
• Factores estructurales incluyen:

❑organización general y estructura global de control
❑ protocolos de comunicación, sincronización y acceso a datos
❑asignación de funcionalidades a elementos de diseño
❑distribución física
❑composición de elementos de diseño
❑escalamiento y rendimiento
❑selección entre alternativas de diseño”

## Conectores

•Diferentes formas de conexión de bajo nivel (synchronous, asynchronous, peer-to-peer, event broadcast) son diferentes aun representados como llamadas a procedimientos en el lenguaje de programación. Los conectores pueden codificarse en diferentes lenguajes al los que se usan en los componentes.

## Filosofía de Shaw

Componentes — unidades compiladas (modulo, estructura de datos, filtros)
• — son identificados por interfaces.
• Conectores — (RPC (Remote Procedure Call), eventos, tuberias) — media las
comunicaciones entre components y es especificados por protocolos.

## Elementos conectores 

• Cada Sistema de software tiene elementos conectores que se comunican a través de diferentes capas.

• Las librerías de terceros dan servicios compartidos que proveen servicios core como estructuras de datos (XML, JSON, etc.), logging, debugging, y otros servicios.

## Definición de arquitectura de software

• Boehm, et al 1995
• Una AS comprende: una colección de componentes de SW y de sistema, conexiones, restricciones.


## Requisitos no funcionales

- Adecuación funcional
- Eficiencia de desempeño
- Compatibilidad
- Usabiliad
- Fiabilidad
- Seguridad
- Mantenibilidad
- Portabilidad

## Principios de una buena arquitectura

- Útil 
- Estable
- Agraciado

## Beneficios de una arquitectura de software

### Manifesta las decisiones de diseño Tempranas

• Define restricciones de implementación
• Inhibe o activa los atributos de calidad del sistema
• Facilita razonar acerca del manejo del cambio
• Ayuda a la evolución del prototipado
• Alcanza más exactitud en estimación de costos y agenda de proyectos de Software

### Las arquitecturas como un modelo reusable y transferible
• Las líneas de productos de software comparten una arquitectura en común.
• Los sistemas se pueden construir usando grandes y extensos elementos de desarrollo
• Menos es más: vocabulario restringido de alternativas de diseño
• Una arquitectura permite el desarrollo basado en plantillas (templates)
• Una arquitectura puede ser la base para el entrenamiento de nuevos miembros del equipo de desarrollo.

### Problemas por la falta de Arquitectura 

Problemas por la falta de Arquitectura
- Rendimiento inadecuado de las apps.
- Mantenimiento costoso
- Diseño inadecuado para evolucionar
- Reutilización limitado
- Proyectos ineficientes (el arquitecto particiona el trabajo de tal manera que cada ingeniero debe comunicarse con todos los demás para hacer su trabajo)
- Afecta la calidad de los sistemas de software.
- No hay interoperabilidad


## App Types

- Mobile
- RIAs
- Rich Clients
- Service
- Web
- Office based applications (OBA)
- Sharedpoints LOBs


## App Arch Frame

- Authentication and Authorization
- Caching/ State
- Communication
- Concurrency and Transactions
- Configuration Management
- Coupling and Cohesion 
- Data Access
- Exception Management
- Logging and instrumentation
- User Experience
- Validation
- Workflow

## Trends

- Dynamic Languages
- Functional Programming
- Green IT
- Parallel Computing
- User Empowerment
- User Experience

## Arch Styles

- Client/server
- Component Based Architecture
- Distributed Architecture
- Layered
- Object Oriented
- P2P/Grid
- S+S
- SOA

## Layers

- Presentation Layer
- Business Layer
- Data Layer
- Service Layer

## Quality Attributes

 - Manageability
 - Performance
 - Reliability
 - Security
 - Testability

## Deployment

- Patterns
- Qualities
- Scenarios

## Patterns

- App types
- Qualities
- Layers
- Arch Frame

## Transaccionalidad

### BD relacional

- Commit/Rollback
- Pruebas ACID
- Entidad relación

### NoSQL

- JSON
- Documentales
- clave-valor
- grafos
- series de tiempo
- teorema CAP
- teorema de brewer

### In-memory

### New SQL

### BD vectoriales

## Oauth 2.0

## Single Sing On


# Segunda Presentación

## Historia de la arquitectura de software

### 1968 Edsger Dijkstra

•Structure before programming.
•It defines Abstraction Levels.
•Conceptual Design

### 1969 P.I Sharp formula

•Software Architecture.
•Specifications: Functionality + Design + Shape

### 1970 Structured design

•Software development models.
•Cascading , Evolutionary and Cyclic models.

### 1972 - 1976 David Parnas

•Modules and Hidden Information.
•Software Structures and Program Families.
•Seeking of Software Quality .
•Early Design Decisions.

### 1975 Brooks

•Architecture as the full UI specification.
•Architecture (What?) vs. Implementation (How?)

### 1980 OOP

•1960 (Simula) TADs y Clases, Smalltalk
•Theory: Model the Domain of the problem and implement it in a OOP language.

### 1992 Perry & Wolf

•Software architecture that is analogous to building
construction. Foundations of the S.A (Elements, Shape).
•CASE Tools.

### 1990s Apogeo de la AS

•1996 - Paul Clements: Components.
•1995 – Design Patterns..
•Architectural Styles(ADLs)
•Architectural Views. Proposed models:
•4+1.
•TOGAF.
•RM/ODP Reference Model of Open Distributed
Processing .
•IEEE 1461.

### 2000 Roy Fielding

•REST Model: Web Technologies and Oriented
Service Model.
•IEEE Std 1471.

### 2000s

SW Product Lines and SW Methods driven to Architecture.

### 2008 - 2022

Frameworks Frontend / Backend –SOA, Microservices, ORMs, Microfrontends. NoSQL, BigData, GraphQL, etc.

## Corrientes principales 

### Arquitectura estructural SEI Carnegie Mellon

Garlan, Shaw, Clemnts
Variantes con modelos de datos(Medividovic), radicales, formales (Moriconi-SRI), etc

### Arquitectura como etapa de la ingeniería de software orientada a objetos

James Rumbaugh, Grady Booch, Ivar Jacobson ("Los 3..."), Craig Larman ...

### Arquitectura basada en patrones - SEI

Redefinición de estilos como patrones POSA
Microsoft Patterns & Practices

### Arquitectura procesual y metodologías

Kazman, Bass (SEI)
Variantes de arquitectura basada en escenarios

## The evolution of software architecture

### 1990's

Spaghetti-oriented architecture (aka copy & paste)

### 2000's

Lasagna-oriented architecture (aka layered monolith)

### 2010's

Ravioli-oriented architecture (aka microservices)

## Software Architecture evolution

- Assembly
- Compiled Languages: Procedural, OO, Functional
- Distributed: Client-server, nTier, RPC, ESB, messaging
- Runtimes: Java - .NET, Dynacmic Languages, Application server, Virtualisation-containers
- Internet: SoAP-SOA, Javascript AJAX, Rest, Microservices, reactive
- NoSQL: Document, GRAPH, HADOOP
- CLOUD: IAAS, SAAS, PAAS, Serverless
- APPS: iOS, ANDROID, Precompued
- DEVOPS: Automation, Continnous Delivery, Infraestructure As code

## Dominios Arquitectónicos

Los "dominios" arquitectónicos son espacios de problema con un alcance distinto, primero se define en que partes de puede dividir la arquitectura de software, luego las define y a cada una le define reglas y estructura ademas se describen los diferentes aspectos del sistema TI

## Otros dominios arquiectónicos más allá de la arquitectura de software

La pirámide de arquitectura de Dern establece una relación jerárquica entre los diferentes dominios arquitectónicos de una empresa.

Las capas de esta pirámide son estrategia, arquitectura del negocio, arquitectura de la información, arquitectura de la aplicación y arquitectura de la infraestructura. La arquitectura de software va en la parte de arquitectura de la aplicación

Otros dominios arquitectónicos:
• ‣ Arquitectura TI corporativa.
• ‣ Arquitectura de procesos de negocio.
• ‣ Arquitectura de hardware.
• ‣ Arquitectura de procesador.

### Arquitectura funcional frente a arquitectura técnica

¿Qué hace el sistema informático desde la perspectiva del dominio de la aplicación?
¿Cómo funciona desde la perspectiva de quien implement u opera el sistema?

### Arquitectura abstracta frente a arquitectura concreta

¿Qué reglas ayudan a estructurar y restringir los componentes funcionales y técnicos?
¿Qué componentes funcionales y técnicos concretos se pueden identificar?

# Tercera presentación

## Arquitecto de software

• El arquitecto de software tiene la responsabilidad global de dirigir las principales decisiones técnicas, expresadas como la arquitectura de software.

• Esto habitualmente incluye la identificación y la documentación de los aspectos arquitectónicamente significativos del sistema, que incluye las "vistas" de requisitos, diseño, implementación y despliegue del sistema.

## Que es un Arquitecto de software?

### Rational Unified Process

Arquitecto es un rol en un proyecto de desarrollo de software el cual es responsable de:

– Liderar el proceso de arquitectura.

– Producir los artefactos necesarios: Documento de descripción de arquitectura

– Modelos y prototipos de arquitectura.

### Oracle SL-425

El arquitecto:

– Visualiza el comportamiento del sistema.

– Crea los planos del sistema.

– Define la forma en la cual los elementos del sistema trabajan en conjunto.

– Responsable de integrar los requerimientos no-funcionales (NRFs) en el sistema.

## Influencias hacia y desde la arquitectura

Se ve influenciado por los stakeholders, por la development organization, por el technical environment y por la architect's experience

## Influencias de los participantes sobre el proyecto

Se ve influenciado por el líder de mercadeo, el gerente del proyecto, el usuario final, el soporte aplicativo y el cliente

## Relaciones del arquitecto

• VENTAJAS:

• ‣ Mayor comprensión de los asuntos de interés adicionales.

• DESVENTAJAS:

• ‣ Conflictos de intereses.

• ‣ Descuido de la documentación.

• ¡Se debe procurar una clara distribución de responsabilidades y vías de comunicación bien definidas entre todos los roles!

## Factores de influencia

### Relativos al producto

- Prestaciones funcionales
- Requisitos de calidad

### Relativos a la organización

- Organización y Estructura
- Recursos
- Estándares
- Legislación

### Tecnológicos

- Infraestructura
- Hardware

## Factores de influencia de la organización y estructura

• Estructura organizativa de la organización.
• Estructura organizativa del equipo de proyecto.
• Responsables de la toma de decisiones.
• Asociaciones / Cooperación.
• Desarrollo interno o externo (por ejemplo, subcontratado).
• Producto comercial o uso interno.

## Ley de Conway

"Las organizaciones que diseñan sistemas... se ven obligadas a producir diseños que son copias de las estructuras de comunicación de estas organizaciones".

## Factores de influencia tecnológicos

- Infraestructura de software
- Infraestructura de hardware
- Normas de programación
- Estructuras de datos
- Entorno de operación
- Arquitectura de referencia
- Librerías, marcos de trabajo y componentes
- Disponibilidad de entorno de ejecución
- Interfaces de programación
- Interfaz gráfica de usuario
- Protocolos de comunicación
- Lenguaje de programación

## Responsabilidades del arquitecto de software

El Arq de SW tiene la responsabilidad para tomar las decisiones técnicas. Esto incluye identificar y documentar aspectos importantes del sistema incluyendo requerimientos, diseño , Implementación y despliegue de las vistas del sistema.

- Arquitectura: Definición de arquitectura de los sistemas, vista física, vista lógica, principios de arquitectura, seguridad, etc.

- Selección de Infraestructura: Sistemas Operativos, hardware, redes, sistemas de recuperación, etc. 

- Selección de Software: Pilas de aplicaciones, bases de datos, librerías, frameworks, estándares tecnológicos, etc.

- Metodología de Proyectos: Estructura de Proyectos, Metodologías (Waterfall, Scrum, RUP, XP...).

- Coaching y Mentoring: Ayuda sobre problemas técnicos, ayuda en la evolución profesional, etc.

- Liderazgo: Liderazgo Técnico, responsabilidad y autoridad, dirección de equipos, etc.

- Requisitos no Funcionales: Rendimiento, escalabilidad, seguridad, etc.

- Procesos de Desarrollo: Control de versiones de código fuente, procesos de construcción, integración continua, automatización de pruebas y otros procesos y herramientas de desarrollo.

- Prácticas y Estándares: Estándares de codificación y libros blancos, selección de herramientas, etc.

- Experiencia: Conocimiento sobre tecnologías y arquitecturas.

- Diseño, Desarrollo y Pruebas: Diagramas UML, codificación, pruebas unitarias, etc.

- Estar al día en cuanto a tendencias tecnológicas: Agile, Web 2.0, SOA, Java EE, etc.

## Tipos de arquitectos

### Enterprise Architect

Realiza estrategias de IT, estrategias de integración. Su misión es soportar la estrategia de negocios de la organización con soluciones de IT e información.

Competencia: Conocimiento profundo de tanto el negocio como de IT, liderazgo y capacidades de negociación. Experiencia en gobernanza, manejo de proyectos y economía. No interactúa con el Código. Se enfoca en componentes del negocio.

### Business Architect

Posee un conocimiento profundo del negocio, modela procesos de negocio, análisis de requerimientos y tiene capacidad de liderar grupos de trabajo.

Competencia: Conocimiento profundo del negocio, modelado de procesos de negocio, capacidad de liderazgo y análisis de requerimientos.

### Solution Architect

Trabaja con el diseño de soluciones de IT basadas en los requerimientos del negocio, haciendo uso de capacidades de IT existentes dentro de la organización.

Competencia: conocimiento técnico amplio y conocimiento en infraestructura, modelo de datos, orientación al servicio y buena comprensión de la arquitectura empresarial. Crea conexiones entre múltiples sistemas

### Software Architect

Trabaja con la estructura y el diseño de sistemas de software. Frameworks, patterns, modelos de clase, etc. Trabaja con requerimientos funcionales y no funcionales como las QoS quality of service: flexibilidad, performance, usabilidad, etc.

Competencia: conocimiento profundo en programación frameworks, estándares y modelado técnico

## Otros tipos de arquitectos

### Arquitecto de aplicación

Se enfoca en una o más aplicaciones especificas 
Ejemplos:
Arquitecto del sistema contable
Arquitecto de la aplicación XYZ

### Arquitecto por lenguaje

Muy común en empresas de desarrollo a la medida
Ejemplos:
Arquitecto .NET
Arquitecto JAVA
Arquitecto NodeJS

# Cuarta Presentación

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

# Quinta presentación

## UML deployment diagrams

- Modelan el hardware usado en la implementación de un sistema y la asociación entre los componentes de hardware, se usan para documentar la arquitectura física de un sistema.

- Los componentes también se pueden mostrar en el diagrama de deployment para indicar su ubicación

- Los elementos usados en los diagramas de deployment son componentes, nodos que representan los recursos de procesamiento físicos en el sistema, y las asociaciones

### Component

Representa una entidad de software en un sistema, incluye código fuente, programas, documentos y recursos

### Node

Representa una pieza de hardware en el sistema

### Asociation 

Una línea entre los nodos

### Usos

• Sistemas empotrados: Un sistema empotrado es una colección de hardware con una gran cantidad de software que interactúa con el mundo físico.

• Sistemas cliente-servidor: Los sistemas Cliente-Servidor son un extremo del espectro de los sistemas distribuidos y requieren tomar decisiones sobre la conectividad de red de los clientes a los servidores y sobre la distribución física de los componentes software del sistema a través de nodos.

• Sistemas completamente distribuidos: En el otro extremo se encuentra aquellos sistemas que son ampliamente o totalmente distribuidos y que normalmente incluyen varios niveles de servidores

### Pros

- Muestra un conjunto de nodos y sus relaciones

- Se utiliza para describir la vista de despliegue estática de un sistema

- Se relacionan con los diagramas de componentes, ya que un nodo normalmente incluye uno o más componentes

### Cons

- La posible falla en la modelación de un hardware

- Tales sistemas contienen a menudo varias versiones de componentes software, alguno de los cuales pueden incluso migrar de un nodo a otro. El diseño de tales sistemas requiere tomar decisiones que permitan un cambio continuo de la topología del sistema 

### \<<Device\>> 

- Un dispositivo es un nodo del cual representa un recurso físico de computo en el cual un artefacto puede ser desplegado para su ejecución

- UML da estereotipos no estándares para los devices.
	- \<<application server\>>
	- \<<client workstation\>>
	- \<<mobile device\>>
	- \<<embedded device\>>


### Deployment

- Un despliegue es una relación de dependencia en el cual describe una ubicación de un artefacto

- El componente de despliegue puede ser asociado a uno o múltiples artefactos, opcionalmente parametrizado por una especificación de despliegue

### Artifacts

- Es un clasificador que representa una entidad fisica

- Es un pieza de información que es usada o es producida por el proceso de despliegue del sw o por el despliegue y operación del sistema

- El artefacto es una fuente de despliegue al nodo

- Los artefactos pueden tener propiedades que representan caracteristicas y operaciones que puede hacerse con sus instancias.
- El Profile estándar UML define estos estereotipos que aplican a los artefactos: Ejemplos:
- «source» fichero Fuente que puede compilarse en un ejecutable
- «library» fichero de librería
- «executable» Un fichero que puede ser ejecutado por un sistema SW
- «script» Fichero de script que puede ser interpretado por un sistema SW.
- \<<web archive\>> para WARs

### Jerarquia de nodos

La jerarquía de los nodos pueden ser modelados utilizando composición o por la definición de una estructura interna.

### Execution enviroment

- Es usualmente parte de un nodo general o un \<<device\>> que representa un JW físico en el cual este entorno de ejecución reside 

- Los ambientes de ejecución pueden ser anidados (Por ejemplo un ambiente de ejecución de una BD puede ser anidado a un ambiente de ejecución de un S.O)

### Manifests

- Manifestación es una relación de abstracción el cual representa una renderización física completa (implementación) de uno o mas elementos del modelo por artefactos o utilización de elementos del modelo en la construcción o generación de artefactos

- Un artefacto manifiesta uno o mas elementos del modelo

- Desde la versión UML 2.0 los artefactos pueden manifestar cualquier elemento empaquetado, no solo componentes como en las versiones previas de UML

- Una manifestación denotada como una abstracción por ejemplo la línea punteada se dirige desde el artefacto a el elemento empaquetado (un paquete o un componente) y se nombra con la palabra \<<manifest\>> 

### Modelo de referencia técnico

- El Modelo de Referencia Técnica (TRM) proporciona una referencia de servicios de plataforma genéricos y elementos de tecnología y actúa como un soporte sobre el que se pueden construir arquitecturas tecnológicas.

- El TRM ofrece un conjunto de bloques de construcción de arquitectura y soluciones que, en última instancia, proporcionará la plataforma para las aplicaciones de negocios e infraestructura.

- El Modelo de Referencia Técnica garantiza que las arquitecturas se creen de forma coherente y repetida sobre la base de un conjunto estándar de elementos.

- El modelo debe crearse como parte de la configuración de los programas de arquitectura, pero normalmente requerirá una ampliación a medida que se introduzcan y retiren los estándares tecnológicos.

# Sexta presentación


## Arquitectura vs Complejidad

➢En la medida que la complejidad de los sistemas crece, los algoritmos y las estructuras de datos dejan de convertirse en el mayor problema.

➢El diseño y especificación de la estructura general del sistema emerge como un nuevo tipo de problema: el diseño a nivel de arquitectura.

➢En aplicaciones OO las clases representan unidades de granularidad muy fina; en sistemas grandes se requiere hablar de unidades que represente una funcionalidad mayor (módulos / subsistemas / componentes de negocio)

➢Emplear alta abstracción en cada nivel.

## Pasos para la definición de un arquitectura de software

- Creación del caso de negocio para el sistema
- Entendimiento de los requisitos
- Creación y Selección de la arquitectura
- Documentación y comunicación de la arquitectura
- Análisis o evaluación de la Arq
- Implementación del sistema basado en la Arq
- Aseguramiento de que la implementación esté acorde con la arquitectura.

## Pasos básicos para definir arquitecturas

- Definir los módulos principales
- Definir las responsabilidades que tendrá cada uno de estos módulos
- Definir la interacción que existirá entre dichos módulos:
	- Control y flujo de datos
	- Secuenciación de la información
	- Protocolos de interacción y comunicación
	- Ubicación en el hardwarei


## Arquitectura vs Diseño

### Nivel de abstracción

- Arquitectura: Alto nivel, el problema en su contexto
- Diseño: Bajo nivel, pone foco en los detalles

### Entregables

- Arquitectura: Planear susbsistemas, interfaces con sistemas externos, servicios horizontales, frameworks, componentes reutilizables, prototipo arquitectónico
- Diseño: Diseño detallado
- Diseño: Especificación de codificación

### Áreas de enfoque

- Arquitectura: Selección de tecnologías, requirimientos no funcionales (QoS), manejo de riesgos
- Diseño: Requerimientos funcionales

Architecture is concerned with the selection of architectural elements, their interactions, and the constraints on those elements and their interactions necessary to provide a framework in which to satisfy the requirements and serve as a basis for the design

Design is concerned with the modularization and detailed interfaces of the design elements, theis algorithms and procedures, and the data types needed to support the architecture and to satisfy the requirements
(Perry & Wolf g2)

La arquitectura envuelve un conjunto de decisiones estratégicas de diseño, lineamientos, reglas y patrones que restringen el diseño y la implementación de un software.

## Niveles de diseño

- Diseño Arquitectónico: Diseño de las estructuras que permiten a los drivers ser satisfechos

- Diseño de interacción de elementos: Identificar elementos adicionales y sus interfaces

- Diseño de elementos internos: Implementación de interfaces


# Estructura del documento de definición de arquitectura

### 1. Introducción
• Propósito: Explicar el objetivo del documento y su audiencia.

• Alcance: Describir qué partes del sistema cubre el documento.

• Definiciones, Acrónimos y Abreviaturas: Proporcionar definiciones de términos importantes utilizados en el documento.

• Referencias: Listar documentos, estándares, o referencias externas relevantes para la arquitectura.

• Resumen del Documento: Breve descripción de la organización del documento.

### 2. Visión General de la Arquitectura

• Descripción General: Proporcionar un resumen de la arquitectura del sistema, incluyendo los principales objetivos de diseño.

• Metas y Restricciones: Describir los objetivos principales de la arquitectura, así como las restricciones impuestas (técnicas, de negocio, legales, etc.).

• Contexto del Sistema: Describir cómo el sistema se sitúa dentro de un entorno mayor (contexto empresarial, interacción con otros sistemas, etc.).

### 3. Vista de Casos de Uso

• Diagrama de Casos de Uso: Mostrar los principales casos de uso del sistema.

• Descripción de Casos de Uso: Proporcionar descripciones de alto nivel de los principales casos de uso y sus actores.

### 4. Vista Lógica

• Diagrama de Componentes: Mostrar la estructura lógica del sistema (módulos, capas, paquetes).

• Descripción de Componentes: Describir los principales componentes y sus responsabilidades.

• Relaciones entre Componentes: Explicar las relaciones y dependencias entre los componentes.

• Patrones Arquitectónicos: Mencionar cualquier patrón arquitectónico utilizado (por ejemplo, MVC, microservicios, etc.).

### 5. Vista de Desarrollo

• Estructura de Paquetes y Módulos: Describir la estructura del código fuente, incluyendo paquetes, módulos y submódulos.

• Convenciones de Desarrollo: Detallar las convenciones de codificación y otros estándares de desarrollo utilizados.

• Entorno de Desarrollo: Describir las herramientas y entornos utilizados en el desarrollo.

### 6. Vista de Procesos

• Diagrama de Procesos: Mostrar cómo los procesos interactúan dentro del sistema.

• Descripción de Procesos: Describir los principales procesos del sistema y cómo interactúan entre sí.

• Gestión de Concurrencia: Explicar cómo se maneja la concurrencia y la sincronización de procesos.

### 7. Vista Física (Despliegue)

• Diagrama de Despliegue: Mostrar cómo se distribuyen los componentes del sistema en la infraestructura física.

• Descripción de Nodos: Describir los nodos físicos y sus responsabilidades.

• Mapeo de Componentes a Nodos: Explicar cómo los componentes lógicos se despliegan en los nodos físicos.

### 8. Vista de Datos

• Modelo de Datos: Proporcionar un modelo conceptual de los datos utilizados por el sistema.

• Gestión de Datos: Describir cómo se manejan los datos en el sistema, incluyendo la persistencia, la caché, la replicación, etc.

• Integridad y Consistencia de Datos: Explicar las políticas de integridad y consistencia de datos.

### 9. Vista de Seguridad

• Requisitos de Seguridad: Detallar los requisitos de seguridad relevantes para la arquitectura.

• Modelo de Seguridad: Describir el modelo de seguridad del sistema, incluyendo autenticación, autorización, cifrado, etc.

• Políticas de Seguridad: Explicar las políticas de seguridad y cómo se implementan.

### 10. Vista de Escenarios

• Escenarios de Calidad: Describir escenarios específicos que prueben los atributos de calidad de la arquitectura (escalabilidad, rendimiento, disponibilidad, etc.).

• Análisis de Riesgos: Identificar riesgos potenciales en la arquitectura y cómo se gestionan.

### 11. Vista de Implementación y Migración

• Plan de Implementación: Describir el plan de implementación del sistema.

• Migración de Datos y Sistemas: Explicar cómo se migrarán los datos y sistemas existentes al nuevo sistema.

• Compatibilidad con Versiones Anteriores: Describir cómo se manejará la compatibilidad con versiones anteriores.

### 12. Aspectos No Funcionales

• Requisitos de Rendimiento: Especificar los requisitos de rendimiento del sistema.

• Requisitos de Disponibilidad y Fiabilidad: Describir los requisitos de disponibilidad y fiabilidad del sistema.

• Requisitos de Mantenibilidad y Extensibilidad: Explicar cómo la arquitectura soporta la mantenibilidad y extensibilidad.

### 13. Conclusión

• Resumen de Decisiones Clave: Resumir las decisiones arquitectónicas clave y sus justificaciones.

• Lecciones Aprendidas: Describir cualquier lección aprendida durante el proceso de diseño arquitectónico.

### 14. Apéndices

• Glosario: Definir términos técnicos y acrónimos utilizados en el documento.

• Diagramas Adicionales: Incluir diagramas adicionales que puedan ayudar a comprender la arquitectura.

• Referencias: Listar cualquier referencia adicional no cubierta en la introducción.

### 15. Índice de Figuras y Tablas

• Proporcionar un índice para todas las figuras y tablas incluidas en el documento.

### 16. Historial de Revisión

• Mantener un registro de todas las revisiones del documento, con detalles de los cambios realizados y quién los realizó.

## Esquema RUP

Fases, disciplinas, iteraciones, roles, actividades y artefactos

## Diseño de software y stack arquitectónico

### Enterprise patterns

DTO's, Domain-Models, Transacition Scripts, Repositories, Mappers, Value Objects

### Architectural Patterns

Model-View-Controller, Domain-Driven Design

### Architectural Styles

Layered, Client-Server, Monolithc, Component-based

### Architectural Principles

Policy vs. details, coupling & cohesion, dependencies, boundaries

### Design Patterns 

Observer, Strategy, Factory, etc

### Design Principles 

Composition Over Inheritance, Hollywood Principle, encapsulate what varies, SOLID, DRY, YAGNI

### Object-Oriented Programming

Inheritance, Polymorphism, Encapsulation, Abstraction

### Programming Paradigms

Structured, object-Oriented, Functional

### Clean Code

Name, Construct, structure, style, readability

## Principio KISS

• «Keep It Simple, Stupid», en español “Mantenlo simple y estúpido”, y nos quiere decir que las cosas sencillas funcionan mejor, a nivel de código, que lo mantengamos simple.

• Nuestra solución tanto en diseño como en implementación debe ser sencilla.

#### Ventajas:

• Mejora la legibilidad y comprensión del sistema.
• Facilita el mantenimiento y probablemente disminuya la deuda técnica.
• Podrás centrarte en resolver otros problemas.
• Produce código de mayor calidad.

#### ¿Cómo aplicar KISS?

• Divide el problema en muchos pequeños problemas. Cada problema debe poder resolverse en una o muy pocas clases.

• Mantener los métodos pequeños, donde cada método nunca debe tener más de 30-40 líneas.

• Cada método sólo debería resolver un pequeño problema, no muchos casos de uso.

• Si tiene muchas condiciones en su método, dividirlas en métodos más pequeños.

## Principio DRY

• Don’t Repeat Yourself, en español “No te repitas” llama a aplicar la práctica de no repetir el mismo código en el sistema.

• Básicamente una pieza de código en el sistema tiene que ser única, no ambigua, tener un objetivo único y no puede repetirse.

#### Ventajas

• Mejora la mantenibilidad:
• Permite crear un código más legible y fácil de entender para todo el equipo.
• Otra ventaja importante es la reusabilidad, esta es inherente a la aplicación de esta práctica, al fusionar varios bloques de código en una solo, con un objetivo definido, podremos reusarlo en el ámbito de la aplicación cada vez que lo necesitemos.
• Mejora el testeo del software (unitario, integración) al no tener duplicados.
• Mayor velocidad en el desarrollo como consecuencia de la reusabilidad.

## Principio YAGNI

• “You Aren’t Gonna Need It”, refiere a no codificar aquello que no vamos a necesitar

• Los programadores en ocasiones agregamos en las aplicaciones lógica “por si acaso”, pensando que en el futuro la vamos a necesitar, ignorando que estamos agregando complejidad adicional con algo que no aporta valor directo a la solución. Desventajas de aplicar este principio

• Incremento del tiempo de desarrollo.

• Mayor complejidad para testear o alcanzar un mayor coverage en las pruebas.

• Dificulta la legibilidad.

• Puede incrementar los costes generales sin generar ningún beneficio a cambio.

## Principios de diseño S.O.L.I.D

### Single responsibility Principle

• Cada clase tiene una única responsabilidad y propósito

### Open Closed Principle

•Una clase puede ser abierta para extenderse pero cerrada para modificarla.

• Por ejemplo podría adicionar mas funcionalidad pero no modificar las funciones actuales.

### Liskov substitution principle

•Usar la herencia de una manera que no rompa la lógica de la aplicación en ningún momento.

• Por lo tanto, si una clase hija llamada "XyClass" hereda de una clase padre "AbClass", la clase hija no deberá replicar la funcionalidad de la clase padre de una manera que cambie la clase padre su comportamiento. De este modo, puede utilizar fácilmente el objeto de XyClass en lugar del objeto de AbClass sin romper la lógica de la aplicación.

### Interface Segregation Principle

•Una clase puede implementar múltiples interfaces.

### Dependency Inversion Principle

• Como desacoplar su código.

• Si por ejemplo una Clase compra depende de la clase Usuario, entonces la instanciación del objeto usuario debería venir de afuera de la clase Compra.

## LSP

• LSP indica que los objetos de su subclase deben comportarse de la misma manera que los objetos de su superclase.

• En el ejemplo Car y Bicycle se extienden de la clase Vehicle. Esto hace fallar el principio LSP por el objeto Bicycle no puede reemplazar a Vehicle con el metodo starEngine()

## Principio de segregación de interfaces

• Esto implica que debes mantener tus interfaces tan pequeñas como sea posible. No llene sus interfaces con métodos que no son necesarios.

• En este caso, nuestra interfaz está contaminada con métodos como nadar y volar que no se aplican a la clase Dog.

• Podemos arreglar esto dividiendo nuestra interfaz en múltiples interfaces como AnimalsWhoSwim y AnimalsWhoFly. La interfaz Animals puede contener la función eat()

## Principio de inversión de dependencias 

Imaginemos que estamos haciendo un videojuego en cual tenemos un personaje que es un robot, este robot puede realizar acciones de diferentes maneras, por lo cual su cabeza puede ser conectada a infinidad de cuerpos distintos.

Las soluciones tradicionales desde el punto de vista de POO son diversas, ejemplo:

❑ Una clase base Robot con un atributo cuerpo, crear varias clases asignando un atributo Cuerpo diferente en el constructor

❑ Una clase Robot con un atributo enumeración que le permita cambiar de cuerpo

❑ Muchas clases cuerpo que heredan de una clase Robot

### Problema

La responsabilidad del cuerpo y de la cabeza sigue siendo confusa, además, hay que intentar respetar el principio SRP "Single Responsability" que señala: "Un objeto una responsabilidad"
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


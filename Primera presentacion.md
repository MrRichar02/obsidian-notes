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


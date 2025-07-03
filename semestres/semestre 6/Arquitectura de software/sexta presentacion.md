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

## Reglas estructurales para la arquitectura

- La arquitectura debería tener bien definidos los módulos.

- Cada módulo debería tener bien definido las interfaces que encapsula. Estas interfaces permitirán desarrollar de manera independiente cada módulo.

- La arquitectura nunca debe de depender de una versión de un producto o herramienta comercial.

- Los módulos que producen datos deberán estar separados de los módulos que consumen datos. Esto permitirá que cuando un dato sea añadido solo tenga que modificarse un módulo.

- Cada tarea o proceso deberá ser bien documentado, para que este pueda ser fácilmente modificado, quizás incluso en tiempo de ejecución.

- La arquitectura deberá caracterizarse como un conjunto de simples interacciones, esto es para incrementar la confiabilidad, la manteneabilidad, reducir el tiempo de desarrollo, etc.

## Aspectos importantes de la arquitectura

✓ Seleccione la vista arquitectonica. Use por ejemplo 4+1 vistas o Modelo C4 (Contexto, Contenedores, Componentes y Código) - https://c4model.com/.

✓ Seleccione el Estilo Arquitectonico (Monolitico, SOA- Microservicios, arquitectura en capas (Layer), etc)

✓ Seleccione entre una solución Cloud o servidores on-premise

✓ Considere Autenticación / Autorización y Privacidad.

✓ Defina reglas de seguridad y protocolos de comunicación

✓ Defina si se necesita balanceo de carga (Nginx), messaging (Apache Kafka, RabbitMQ, JMS, ActiveMQ), etc

✓ Hacer una revisión general de cualquier algoritmo crítico que controle el servicio.

✓ Considere cuellos de botella y determine soluciones

✓ Seleccione Tipos de almacenamiento (SQL o NoSQL , NewSQL, In-Memory)

✓ Comprender qué datos deben almacenarse en caché y cómo mejorar el rendimiento, la seguridad y la disponibilidad con el almacenamiento en caché (Elasticsearch / Apache Solr).

✓ Seleccione un Sistema de monitoreo (Graphite /Prometheus / Grafana) y logging (Kibana /Datadog /Logstash / Fluentd). Como Gestionar Excepciones y fallos (Netflix Turbine / Hystrix, Resilence4J).

✓ Defina la separación entre areas públicas y restringidas

## Architecture Design

### API Design Choices

- REST
- RPC
- GraphQL

### Forma de responder

- Synchronous
- Async Messaging
- Publish Subscribe

### Scalability

### Replication

### Partitioning

### Sharding

### Load Balancing

### Caching

## Vertical / Horizontal Partitioning

## Content Delivery Network (CDN)

A CDN is a network of geographically dispersed servers used to deliver static content. CDN servers cache static content like images, videos, CSS, JavaScript files, etc.

Dynamic content caching enables the caching of HTML pages that are based on request path, query strings, cookies, and request headers.

## geoDNS

In normal operation, users are geoDNS-routed, also known as geo-routed, to the closest data center, with a split traffic of x% in US-East and (100 – x)% in US-West. geoDNS is a DNS service that allows domain names to be resolved to IP addresses based on the location of a user

## Logging: 
Monitoring error logs is important because it helps to identify errors and problems in the system.

## Metrics:
Collecting different types of metrics help us to gain business insights and understand the health status of the system. Example

## Host level metrics:
CPU, Memory, disk I/O, etc.

## Aggregated level metrics:
for example, the performance of the entire database tier, cache tier, etc.

## Key business metrics:
daily active users, retention, revenue, etc.

## Automation:
When a system gets big and complex, we need to build or leverage automation tools to improve productivity.

C.I is a good practice, in which each code check-in is verified through automation, allowing teams to detect problems early. Besides, automating your build, test, deploy process, etc. could improve developer productivity significantly.

## Cohesión y acoplamiento

• La cohesión implica que un componente o clase encapsula solo atributos y operaciones que están altamente relacionados entre ellas y con la clase. Se busca la máxima cohesión en una clase

• Acoplamiento es la medida cualitativa del grado en que una clase está conectada con otra. Se busca el mínimo acoplamiento entre clases

## Característica fundamental de las arquitecturas

- Bajo acoplamiento y alta cohesion

## Pasos para diseño de componentes

1. Identifique todas las clases de diseño que correspondan al dominio del problema

2. Identifique todas las clases de diseño que correspondan al dominio de la infraestructura (GUI, sistemas operativos, administración de datos etc.)

3. Elabore todas las clases que no provienen de clases reusadas

	a) Especifique detalles de los mensajes entre clases que colaboran
	b) Identifique las interfaces de cada componente
	c) Elabore atributos y defina tipos de datos y estructuras de datos requeridas para implementarlas
	d) Describa el flujo de procesamiento de cada componente en detalles

4. Describa fuentes de datos persistentes (bases de datos y archivos) e identifique las clases requeridas para manipularlos

5. Desarrolle y elabore representaciones del comportamiento de una clase o componente (diagramas de estados)

6. Elabore diagramas de despliegue (deployment) para dar detalles adicionales de implementación

7. Revise cada representación de diseño de los componentes y siempre considere alternativas

## Descripción de una arquitectura

✓Representación o “plano” de una configuración real de recursos, reglas, y relaciones actuales o sugeridas.

✓Colección de productos para documentar una arquitectura.

## Vista arquitectónica

- Una vista arquitectónica de una sistema o plataforma de negocio que presenta primordialmente : Estructura, modularidad, componentes esenciales y flujos de control principales de un dominio ó perspectiva específica del problema de negocio que soporta la arquitectura.

- Es una ventana al interior del sistema desde una perspectiva especifica enfatizando una idea en particular

## Productos resultantes de la arquitectura de software

El objetivo principal de la Arquitectura del Software es aportar elementos que ayuden a la toma de decisiones y, al mismo tiempo, proporcionar conceptos y un lenguaje común que permitan la comunicación entre los equipos que participen en un proyecto. Para conseguirlo, la Arquitectura del Software construye abstracciones, materializándolas en forma de vistas.

✓ Vista lógica: describe el modelo de objetos.

✓ Vista de proceso: muestra la concurrencia y sincronía de los procesos.

✓ Vista física: muestra la ubicación del software en el hardware.

✓ Vista de implementación: describe la organización del entorno de desarrollo.

Existe una quinta vista que consiste en una selección de casos de uso o de escenarios que los arquitectos pueden elaborar a partir de las cuatro vistas anteriores.
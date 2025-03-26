[[Indice arquitectura de software]] para ir al indice

## Spring (MVC, Boot, Security, webflux, AI)

es la suit de herramientas que nos da pivotal, herramientas para el desarrollo de apps en java, kotlin, se divide en distintos tipos de proyectos internos, MVC nos deja desarrollar apps java con el modelo 
MVC, boot nos deja desarrollar apps empresariales, security nos ayuda con la seguridad de nuestras de nuestras apps, webflux, nos deja crear flujos reactivos, AI, nos ayuda a integrar APIs de 
herramientas LLM

## JAvaEE

Es la suit de herramientas de oracle para java empresarial existe una versión open source llamada JakartaEE

## JS

JavaScript 

## TS

TypeScript

## Pipelines (CI/CD).

Automatizar el proceso construir los binarios para un aplicativo y testearlo hasta desplegarlo

![[Pasted image 20250307162325.png]]

## DevOps

es una filosofía de trabajo empresarial, D esta por Development, O por Operations o Infraestructura, es una especie de unión entre los que desarrollan un aplicativo y quienes lo despliegan 

## IaC(Infraestructure as code)

Es una manera de automatizar la utilización de herramientas por parte de DevOps

## Web services

Es un servicio que se va a consumir a través de una red, para consumir el Servicio se utilizaran APIs, veamos los tipos de servicios

## IDL

es el lenguaje de definición de interfaces

### RESTFul

REST es un estilo arquitectónico que significa transición de estados, esta baso en la Hipermedia distribuida, REST esta basado en el protocolo HTTP 1.1, que es un estándar definido por el IETF 
REST esta basado en recursos, en un formato de representación del recurso y en los métodos para manipular esos recursos , todo en REST es un recurso basado en la URI (Identificador de recursos
uniformes) por ejemplo `http://miserver/persona` y `http://miserver/producto`

Formato de representación del recurso conocido como MME Types ejm  text/html, para REST se usa aplication/json o aplication/xml

Su IDL sería  Open API, Swagger

#### JSON

JavaScript Objetc Notation, formato ligero Human Read

#### XML

Lenguaje de marcado extensible, usa un formato basado en árbol, es mas complejo que JSON, permite conversiones, restricciones usando Schems XML, consume más almacenamiento para la misma
cantidad de datos que JSON

#### Métodos para manipular los recursos

Los más conocidos son GET, POST, PUT y DELETE

## SOAP

Las letras significan Simple Object Access Protocol, es un protocolo estandarizado por W3C, esta basado en XML, tiene un único end point conocido como /soap a diferencia de REST que puede tener 
multiples. Utiliza un lenguaje contrato llamado WSDL (Web Service Description Language) XML Schema, también tiene un directorio UDDI (Universal Discover Description and Integration), con este
directorio encontramos los diferentes servicios, para que esto funcione el productor del servicio web sube al directorio un contrato WSDL, para que luego un cliente use el servicio, debe de copiar el 
contrato WSDL luego el consumidor podrá realizar un SOAP REQUEST al productor del servicio web y el proveedor le responderá con un SOAP RESPONSE 

### SOAP message

es la respuesta que obtendría un consumidor, cuenta con un header que es opcional y un body, esta codificado utilizando SOAP ENVELOPE, SOAP aplica un QoS ( quality of service) que esta asociado 
en la fiabilidad de la entrega de mensajes y en la seguridad  

## GraphQL

Se esta convirtiendo en el reemplazo de REST, su nombre significa, lenguaje consulta de grafos, es muy útil para crear los servicios web modernos, tiene tres operaciones veamos las

### Mutaciones

sirve para insertar, actualizar y eliminar datos

### Queries

sirve para las consultas de datos

### Subscripions

sirve para comunicaciones asincronas usando un patrón Pub/Sub

Funciona mas del lado del front que de el back, nos permite traer desde un servicio solo los campos que necesitemos,  sus respuestas estan basadas en JSON, maneja su lenguaje de contrato llamado 
Schema, utiliza un único end point el cual es /graphql

## RPC

llamadas a procedimientos remotos 

## XML-RPM/JSON-RPC

Mecanismos de serelización de RPC

## SQL 

se utiliza el modelo de entidad relación

## NoSQL

no se usan relaciones, existen varios tipos de NoSQL como documentos, key-value, series de tiempo, grafos 

## Jboss, Glassfish, Payara, Weblogic, Tomcat / TomEE 

Servidores para aplicaciones JavaEE

## Docker  / Contenedores

Los contenedores nos salvan de it works in my machine 

### virtualization vs contenedores

en virtualization usamos un hyprvisor que extrae los recursos del sistema operativos host para crear la vm, los contenedores son diferentes porque usan el motor de docker que esta basado sobre el 
sistema operativo, en ese motor montas las aplicaciones mediante imágenes

docker nos permite tener varios contenedores y que se comuniquen entre si 

## Kubernetes

Es un orquestador, similar al de una banda musical, nos permite dirigir a los contenedores, para esto vamos a tener varios nodos y dentro de estos nodos tendremos pods y dentro de los pods 
tendremos contenedores, cada nodo tiene un motor de docker  

Angular

REACTJS

VUEJS

Microservicios

es un estilo arquitectónico en el que tenemos servicios pequeños, cada servicio es dueño de su propio proceso, cada proceso tiene una única memoria y es dueño de sus propios datos, 

Arquitectura Hexagonal

el centro es el modelo de dominio a base de este dominio hay servicios, sobre esto hay casos de uso y sobre uso tenemos los adaptadores y controladores finalmente tenemos los protocolos de comunicación o enlace con otros servicios 

Arquitectura Limpia

OWASP



SONAR

Analiza la calidad del código de una aplicación

GIT

SCRUM

framework que hace parte las metodologías ágiles 

JIRA

NodeJS

ORM

Mapeo objeto relacional 

Azure DevOps
## Arquitecturas empresariales

### TOGAF

### DODAF

### Matriz Zachmman

## LAMP

Stack de: Linux - Apache - MysQL - PHP o Perl

Principios de Diseño (SOLID, K.I.S.S (Keep It Simple Stupid) and D.R.Y design principles), 

## Patrón Pub / Sub

consiste de dos elementos, los publicadores de eventos y los subscriptores que van a recibir la información de esos eventos, la comunicación es asincornica y detonada por eventos, las peticiones suelen ir de publicadores a subscriptores, primero pasan por un input channel luego por el message broker y finalmente al output channel, en el message broker se crea una especie de tren con todos los mensaje en fila y luego envía los mensajes a los subscriptores, el broker permite controlar una gran cantidad de mensajes sin saturar el sistema 

## Rabbit MQ

Es un message broker que se puede usar en un sistema Pub/Sub

## Apache kafka

Es un message broker que se puede usar en un sistema Pub/Sub

## ActiveMQ

Es un message broker que se puede usar en un sistema Pub/Sub

## JMS

Es un message broker que se puede usar en un sistema Pub/Sub

PL/SQL

## JSF (Java server Faces)

## JSP (Java server Pages)

Hibernate, 

## EJB (Enterprise Java Beans)

Cloud 

On-Premise

[[arquitectura SW]]
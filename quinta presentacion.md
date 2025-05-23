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
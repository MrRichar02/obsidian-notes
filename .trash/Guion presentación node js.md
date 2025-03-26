<b>¿Qué es Node.js?</b>

Node.js es un entorno de ejecución de JavaScript basado en el motor V8 de Google, 
que es el mismo motor que utiliza Google Chrome para ejecutar JavaScript en el 
navegador. Node.js permite ejecutar JavaScript en el lado del servidor, fuera del 
navegador, lo que lo convierte en una herramienta poderosa para construir 
aplicaciones web escalables y eficientes.

<b>Historia node.js</b>

Node.js fue creado en 2009 por Ryan Dahl con el objetivo de revolucionar la forma en que los servidores web manejaban múltiples peticiones simultáneas. En esa época, la mayoría de los servidores web utilizaban modelos de hilos bloqueantes, donde cada petición se atendía en un hilo separado. Este enfoque generaba problemas de rendimiento y escalabilidad, especialmente cuando había muchas peticiones concurrentes.

Ryan Dahl observó que este modelo no era eficiente para las aplicaciones modernas y se inspiró en los sistemas de entrada/salida no bloqueantes que ya existían en los navegadores. Así nació Node.js, cuyo principal avance fue su enfoque de programación basado en un modelo non-blocking o no bloqueante, que permitía manejar miles de conexiones simultáneamente con un solo hilo utilizando un bucle de eventos. Este enfoque redujo la sobrecarga de recursos y mejoró significativamente el rendimiento en aplicaciones que requieren alta concurrencia, como los servidores de aplicaciones en tiempo real.

<b>Nodejs y js</b> 

Una de las mayores ventajas de Node.js es que utiliza JavaScript como su lenguaje principal. JavaScript ya era ampliamente utilizado en el desarrollo front-end, lo que permitió que los desarrolladores que ya estaban familiarizados con este lenguaje pudieran utilizarlo también para la parte del servidor. Esta unificación del stack tecnológico permite a los desarrolladores escribir tanto el frontend como el backend en un solo lenguaje, evitando la necesidad de aprender y manejar diferentes tecnologías para cada parte de la aplicación.

Además, este enfoque simplifica la comunicación y el mantenimiento del código, ya que un equipo de desarrollo puede trabajar de manera más eficiente con un único lenguaje en ambos lados de la aplicación. Esto también fomenta el crecimiento de un ecosistema de herramientas y librerías compartidas, lo que facilita la creación de aplicaciones modernas y escalables. En resumen, el uso de JavaScript en Node.js no solo optimiza la curva de aprendizaje, sino que también acelera el desarrollo full-stack.

<b>Non-blocking event loop</b>

A diferencia de los servidores tradicionales que crean un nuevo hilo para cada  solicitud, Node.js ejecuta todas las solicitudes en un solo proceso utilizando un 
modelo de concurrencia basado en eventos. Este modelo no bloqueante (non-
blocking) permite a Node.js manejar múltiples conexiones simultáneamente sin crear 
nuevos hilos para cada una. En lugar de detenerse y esperar una respuesta, Node.js 
continúa ejecutando otras tareas y gestiona las respuestas cuando están disponibles, 
lo que mejora la eficiencia y la escalabilidad.

<b>Node.js librerias default</b>

Los módulos en Node.js son bloques de código encapsulados que poseen su propio alcance y funcionalidad. Estos permiten estructurar el proyecto de manera modular, lo cual facilita la reutilización de código. 

Node.js viene con un conjunto de 15 librerías integradas que están disponibles desde el momento en que se instala, sin necesidad de importar dependencias externas. Estas librerías permiten manejar diferentes aspectos del sistema de manera eficiente. Tres de las más populares y utilizadas son:

http: Esta librería es fundamental para el desarrollo en Node.js, ya que permite crear un servidor HTTP. Con http, puedes manejar peticiones y respuestas del cliente de manera muy simple, lo que hace posible construir aplicaciones web y servicios de APIs RESTful. Su facilidad de uso y su integración directa con el modelo no bloqueante de Node.js lo hacen esencial para casi cualquier aplicación que trabaje con la web.

fs (File System): fs permite a Node.js interactuar directamente con el sistema de archivos. Esta librería te permite leer, escribir, crear y eliminar archivos y directorios, lo que es vital para muchas aplicaciones que requieren almacenamiento local, como servidores de archivos o sistemas de logs. Además, fs ofrece funciones sincrónicas y asincrónicas, lo que te permite trabajar de forma eficiente en operaciones de entrada/salida.

path: path facilita la manipulación de rutas de archivos y directorios. Es especialmente útil cuando desarrollas aplicaciones que deben funcionar en diferentes sistemas operativos (como Windows, macOS o Linux), ya que asegura que las rutas sean construidas de manera correcta según las convenciones del sistema operativo en el que se ejecuta la aplicación. Esto es esencial para evitar errores de ruta y garantizar la portabilidad del código.

<b>npm</b>

Npm (Node Package Manager) comenzó como una herramienta para descargar y gestionar dependencias en proyectos de Node.js, pero su crecimiento ha sido tan significativo que, en 2022, se reportó que tenía más de 2.1 millones de paquetes disponibles. Esta vasta colección de paquetes lo convierte en una pieza clave en el ecosistema de desarrollo JavaScript.

Para instalar todas las dependencias de un proyecto, simplemente puedes correr el comando

npm install ó npm i

Este comando lee el archivo package.json del proyecto y descarga todas las dependencias especificadas.

Instalación de paquetes específicos

Si necesitas instalar un paquete específico y agregarlo a las dependencias de tu proyecto, puedes usar:

npm install nombre-paquete

Este comando añade automáticamente el paquete al archivo package.json en la sección de dependencias. Si quieres añadir el paquete a las dependencias de desarrollo, puedes usar:

npm install nombre-paquete --save-dev

Para dependencias opcionales:

npm install nombre-paquete --save-optional

Actualización de paquetes y manejo de versiones

Npm también permite actualizar paquetes y manejar versiones específicas. Para actualizar un paquete a su última versión compatible, puedes usar:

npm update nombre-paquete

Si deseas instalar una versión específica de un paquete, puedes hacerlo así:

npm install nombre-paquete@1.2.3

Ejecución de scripts

El archivo package.json no solo contiene las dependencias, sino que también permite definir scripts que se pueden ejecutar con npm. Estos scripts se definen en una sección llamada "scripts", y puedes correrlos con:

npm run nombre-script


<b>Módulos</b>

Node.js incluye módulos integrados por defecto, pero también es posible utilizar módulos de terceros o crear módulos personalizados. 

Para utilizar un módulo, es necesario importarlo, y existen dos enfoques para hacerlo: CommonJS y ECMAScript Modules (ESM). 

En CommonJS, se emplea la sintaxis

const { modulo1, modulo2, ... } = require('ruta-modulo');, 

mientras que en ESM se utiliza

import { modulo1, modulo2, ... } from 'ruta-modulo';.

y se le debe colocar la extensión .mjs al archivo 

<b>Express.js</b> 

Express.js es el framework más popular para Node.js y es conocido por ser liviano y minimalista. A pesar de su simplicidad, Express ofrece una estructura sólida para crear aplicaciones web y APIs, permitiendo a los desarrolladores manejar fácilmente peticiones y respuestas HTTP. Una de sus características más poderosas es el manejo de middleware, que permite ejecutar código, modificar peticiones y respuestas, o finalizar el ciclo de respuesta en el servidor de manera modular y eficiente.

Gracias a su flexibilidad y su enfoque minimalista, Express.js es ideal para construir tanto APIs RESTful como aplicaciones web simples. Además, su popularidad ha dado lugar a una amplia comunidad y ecosistema de complementos, lo que facilita agregar funcionalidades avanzadas, como autenticación, manejo de sesiones y más, sin complicar el desarrollo.

Otro punto a destacar es que Express simplifica muchas de las tareas que, con Node.js puro, podrían ser más complejas o tediosas, como la definición de rutas, el manejo de diferentes tipos de contenido y la gestión de errores. Esto lo convierte en una excelente opción para desarrollar proyectos de cualquier tamaño, desde prototipos hasta aplicaciones web de producción.


<b>Node.js y el navegador</b>

Aunque tanto en el desarrollo frontend como en Node.js se utiliza el lenguaje de 
programación JavaScript, existen diferencias importantes entre ambos entornos. En 
el frontend, JavaScript interactúa con el DOM (Document Object Model) y tiene 
acceso a objetos específicos del navegador, como document y window. En Node.js, 
no se interactúa con el DOM ni se dispone de estos objetos, ya que Node.js se 
ejecuta en un entorno de servidor, donde esos elementos no son necesarios ni están 
disponibles.

Una ventaja de Node.js es que permite controlar la versión que se utiliza en tu 
proyecto. Esto significa que puedes escribir tu código utilizando las últimas 
características del estándar ECMAScript (ES2015+), siempre y cuando estén 
soportadas por la versión de Node.js que estás utilizando.

Otra diferencia clave es que Node.js soporta dos sistemas de módulos: CommonJS 
(el sistema de módulos original de Node.js) y ES Modules (un sistema más reciente 
que sigue el estándar ECMAScript). Esta flexibilidad en el manejo de módulos es una 
característica importante de Node.js.
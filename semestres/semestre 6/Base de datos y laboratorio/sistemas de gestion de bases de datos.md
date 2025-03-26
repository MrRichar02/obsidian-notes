[[Indice base de datos y laboratorio]] para ir al indice 

Los sistemas de gestión de base de datos se encargan de que podamos almacenar, consular y añadir información a nuestras bases de datos, son de gran utilidad para diferentes areas de una 
organización por lo que es valioso tenerlos protegidos, estos sistemas realizan operaciones con la propiedad de atomicidad, esto significa que si alguno de los pasos para completar una operación 
falla, se descartan todos los cambios sin aplicar y aplicados 

## Propiedades de las transacciones sobre base de datos

### Atomicidad

Esto asegura que si ocurre un error durante una transacción todo el proceso se va a cancelar, ya sea por un error del sistema operativo, la base de datos o si se llega a una condición que indica un error

### Consistencia 

Esto asegura que mientras se aún se esta realizando una transacción otras transacciones que consulten la misma información que se esta modificando no verán los cambios hasta que o se confirmen o 
se cancelen, en este caso verían lo mismo, la técnica que potencia esto se conoce como control de concurrencia 

### Durabilidad

Esto garantiza que el efecto de cualquier transacción se mantenga con el tiempo hasta que otra transacción cambie la información 

### abstracción de la información mediante modelos de datos 

Esta propiedad nos ayuda representar la información que almacenamos de una manera muy similar a la vida real, por lo que nos permite darle una estructura a los datos, definir reglas para los datos, 
cosas como que no sea null y finalmente nos provee operadores para manipular los datos 

### Control de acceso y seguridad de los datos

Esto asegura que las consultas, modificaciones e inserciones de información a la base de datos requiere una autenticación y tener la autorización necesaria, para esto se suele usar un protocolo llamado
LDAP que es una aplicación que corre por separado con la información de los usuarios para autenticar los, ademas de una verficación de usuarios y autorización se debe de proteger el sistema en contra
de ataques mal intencionados 

## Niveles de abstracción de datos

Los datos se procesan por los sistemas de gestión de base de datos para que el usuario los pueda comprender, pero en entre que se procesan pasan por varias capas

### Nivel físico

En este nivel están los datos como realmente son, osea como colecciones de archivos, indices y estructura de datos, es trabajo del equipo encargado del sistema de mantener las estructuras de datos
y modificarlas si es necesario, esto no debe de alterar los demás niveles y se conoce como independencia de datos físicos

### Nivel lógico 

En este nivel están todos los datos de la organización, representados de una manera más similar al mundo real, esta forma de representación es decidida por los encargados del sistema de mantener 
las  estructuras de datos 

### Nivel de vista de usuario

En este nivel se puede proporcionar porciones de la información a ciertos usuarios, estas porciones no tienen que ser iguales

## Tipos de usuarios

### Implementador del DBMS

Empresas como Microsoft, Oracle y IBM

### El diseñador de la B. de D

Analistas de sistemas, arquitectos de software y administradores de base de datos(DBA)

### Desarrollador de aplicaciones

Programadores y desarrolladores de implementar el código que interactua con la base de DBMS

### Administrador de B. de D(DBA)

Encargado de que el DBMS funcione correctamente, de realizar las copias de seguridad y de mantener a salvo la información de la organización

### Usuarios de aplicaciones

Personal no técnico que usa las aplicaciones de las bases de datos
[[Indice comunicaciones y laboratorio]] para ir al indice

El modelos tcp/ip tiene 4 capas mientras que el modelo OSI tiene 7, tcp/ip tiene programación mientras que OSI no tiene, OSI tiene más capas porque debe de detallar con exactitud todos sus procesos
el modelo tcp/ip tiene menos capas que el modelo OSI porque algunas de sus capas abarcan varias del OSI, las capas del modelos OSI son Physical, Data Link, Network, Transport, Session, Presentation,
y Aplication, las capas del modelo tcp/ip son Physical Network Interface que equivale a las primeras dos capas de la OSI, Network que equivale a la tercera capa de la OSI, Transport que equivale a la 
cuarta capa del modelo OSI y Application que equivale a las ultimas 3 capas del modelos OSI
## Capas del modelos OSI

### Physical

Es la capa encargada de describir como se van a realizar las conexiones físicas entre los dispositivos, describe todo el hardware necesario para la comunicaciones entre las redes y ademas define las
características que tiene la red por la que se va a realizar la conexión, por ejemplo esta capa es responsable del cable de fibra óptica

En esta capa la información que enviamos sería un bit

### Data Link 

Se encarga de definir como se va a transmitir la data en la red local, se asegura de que la data llegue al dispositivo correcto y verifica si ocurren errores, para esto usa cosas como la dirección MAC de 
los dispositivos

En esta capa la información que enviamos sería un trama

### Network

Esta capa se encarga de rutar, darle una dirección y enviar nuestra información, para esto debe de encontrar la mejor ruta física para enviar la data, teniendo en cuenta factores como las condiciones
de la red y la prioridad del servicio, para encontrar el destino de la data esta capa utiliza la dirección IP

En esta capa la información que enviamos sería un paquete

### Transport

Esta capa se encarga de decidir que sucede si se pierde un poco de la información que estamos enviando antes de llegar al destino, si es una comunicación TCP se intentará enviar nuevamente, la
información para que no este incompleta, mientras que si la comunicación UDP no se preocupa por reenviar la información sino de enviarla de la mejor manera que pueda, sin importar que se pierdan 
algunas partes

En esta capa la información que enviamos sería un Segementos

### Session

Se encarga de manejar la conexión entre dispositivos, iniciando, estableciendo y terminando una conexión asegurando eficiencia y organización, también puede definir que sesiones pueden ser 
restauradas luego de una interrupción 

### Presentation

Se encarga de asegurar que la información que llego desde la capa de application de un sistema puede ser interpretada por la capa de application del sistema, para esto se encarga de formatear, 
encriptar y comprimir, por ejemplo se encargaría de pasar de ASCII a caracteres como hello world

### Application

Sirve como la interfaz que van a ver los usuarios finales, dándoles diferentes protocolos para comunicarse entre el host y el usuario

[[origen de las redes]]
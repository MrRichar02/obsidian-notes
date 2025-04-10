recomendado capa de encaces en wikipedia

capa 2 consideraciones: se toman los bits y se combiernte en algo que el entiende, esas son las tramas

## tipos de tramas

### ethernet

#### Partes de esta trama

preambulo: los pc estan atentos al medio escuchando, debe haber una señal que indica a los pcs que llega info importante esto es el preambulo, cuando llega un 1 seguido de otro es que luego ya sigue la info

MAC destino: dirección MAC del dispositivo destino

broadcast: comunicación de uno para todos

dirección fuente: la dirección MAC de la tarjeta de red 

etiqueta: dice el protocolo que se va a usar en la capa superior

Longitud

Carga util: cuantos bytes se van a usar

Secuencia de control: sirve para verificar si llego con algún error o no, por ejemplo paridad par o impar que cuenta la cantidad de unos que hay también se puede hacer en estilo matriz
![[Pasted image 20250329141757.png]] También se puede hacer enviando una división entera para ver si al otro lado da exactamente la misma división

código de redundancia cíclica, es la forma de verificar errores usada en la capa 2 

### ATM

Se puede crear conexiones computador computador, incluso varias. Esta trama tiene una info muy  grande, la ruta, el canal , la información


## Como funciona ehternet ?

Existe un cable al que todos los computadores están pegados, cada uno con su dirección MAC especifica, entre mas computadores hay mas posibilidades de colisiones, esto era con los HUB, pero la solución fueron los switches 

### Tabla CAM

Es una tabla creada por los switches donde se especifica la dirección MAC del dispositivo, junto al puerto donde esta conectado

CSMA/CD

## Aniño por paso de testigo: 

Se colocan los computadores en un circulo, para trasmitir se debe de tener un token que es una trama especial, esta trama se va pasando entre los dispositivos para que pueden transmitir. El token se pasa en el orden en que se hayan encendido los dispositivos osea que se puede saber cuanto se va a tardar en transmitir. Era bastante costoso pero muy efectivo



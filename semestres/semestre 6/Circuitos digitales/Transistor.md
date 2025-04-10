[[Indice diseño de circuitos digitales]] para ir al indice
[[dispositvos electronicos]] para ir al anterior 

## Tipos de transistores básicos

### Bipolar Junction Transistor (BJT)
Opera por corriente, es un amplificador de señal

### Field Effect Transistor (FET)
Opera por voltaje, es un amplificador de señal 

Literalmente, todos los dispositivos eléctricos modernos son construidos en base de estos componentes llamados transistores, dándoles el sobre nombre de los dispositivos básicos más importantes de la tecnología moderna

## Transistor BJT 
Se juntan tres semiconductores en una especie de sandwich, cuentan con dos junturas, cuenta con regiones en cada semiconductor n, n+ y una p, las regiones n no son iguales 

![[Pasted image 20250402061955.png]]

Este transistor se llamada npn, lo que forma es como si dos diodos se estuvieran dando la espalda 
![[Pasted image 20250402062349.png]]
la corriente sale por el emisor

Luego tenemos otro tipo que es pnp
![[Pasted image 20250402062156.png]]
aquí lo que cambia es que ahora en lugar de tener dos n vamos a tener dos p, lo que forma es como si dos diodos se estuvieran mirando
![[Pasted image 20250402062431.png]]
la corriente entra por el emisor 

En ambos transistores el diodo que es dominando va a ser el que este del lado donde esta el +, en el primero sería el del emisor y en el segundo igualmente 

La corriente que fluye por la base es mucho más pequeña que la corriente que pasa por el conector y la que pasa por el emisor 

![[Pasted image 20250402063121.png]]

También podemos decir que la corriente del emisor es aproximadamente la corriente del colector, ya que la corriente de la base es mucho mas pequeña que la corriente del colector

Ganancia de corriente del colector ![[Pasted image 20250402063217.png]]

El transistor es como una llave de agua que se controla desde la base. Siempre entre la base y el emisor existe el diodo dominante 

### Configuración del emisor común 

#### NPN

![[Pasted image 20250402064720.png]]
Un parámetro importante en este circuito es el voltaje entre el conector y el emisor (VcE) si este voltaje nos da menor o igual a cero o aproximadamente 0 significa que le transistor esta saturado y no hay mas corriente disponible. SI VcE es mayor que Vcc o igual el transistor esta en corte, osea que no hay corriente(la corriente del colector es 0), si $0<VcE<Vcc$ el transistor esta en triode, osea que no esta saturado o en corte

#### Ejemplo

Caso 1:

![[Pasted image 20250402070607.png]]

Caso 2:

![[Pasted image 20250402071246.png]]

Caso 3:

![[Pasted image 20250402072037.png]]

#### PNP

![[Pasted image 20250402073108.png]]


Los transistores pueden disipar potencia(=calor) lo que significa que los transistores generan calor adentro de los dispositivos electrónicos, potencia transistor: ![[Pasted image 20250402080322.png]]. Normalmente los dispositivos electrónicos tienen cientos de miles o millones de transistores, lo que implica mucho calor

## Aplicaciones del BJT:

En corte y saturado: Switch electrónico permite y detiene la corriente
Triode: Amplificador de señales eléctricas 

### Puente H
Algunas aplicaciones requieren controlar la dirección de corriente en una carga(resistencia o motor), porque a veces se necesita que vayan para una dirección y otras veces para otra 

![[Pasted image 20250402081221.png]]

El puente H es  un circuito que nos permite hacer lo anterior 

![[Pasted image 20250402082351.png]]

separemos un poco

![[Pasted image 20250402082812.png]]

![[Pasted image 20250402083405.png]]


## Transistor MOSFET (Metal- Oxide - Semiconductor - FET)

No necesitan corriente en la base para operar, solo voltaje


![[Pasted image 20250402091024.png]]

![[Pasted image 20250402091457.png]]
La miniaturization de los transistores ha sido la razón de los dispositivos mobiles


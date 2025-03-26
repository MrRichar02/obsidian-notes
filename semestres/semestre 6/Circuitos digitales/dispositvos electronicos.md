[[Indice diseño de circuitos digitales]] para ir al indice
[[tipos de conexiones electricas]] para ir al anterior

La electrónica nació en 1902, con el tubo de vacío que es utilizado en la radio

1947: El primer dispositivo semiconductor fue creado en los laboratorios bell

1971: El primer microprocesador es creado en Intel (4004) usando mile de dispositivos semiconductores

La industria electrónica hoy en día esta basada en semiconductores y es considerada como la tecnología más importante del siglo 20 y posiblemente del siglo 21

Los semiconductores son elementos de la tabla periódica or combinaciones, los más usados actualmente son:
- Germanio, Ge
- Silicio, Si.  Este es el mas usado
- Galio arsénico GaAs

Tienen la propiedad de tener 4 electrones en la capa mas externa de la órbita conocida como la capa de valence. Esta propiedad les permite tener comportamientos curiosos

### Semiconductores negativos

Se añade un electron a la capa de valence

### Semiconductores positivos

Se saca a un electron de la capa de valence

## Diodo

El dispositivo electrónico mas simple se trata de juntar un semiconductor positivo y uno negativo, el punto donde se junta se llama la juntura. El semiconductor positivo se suele conocer como el Anode(A) y el negativo como  el Cathode(K)

El fenómeno mas interesante de un diodo es que la corriente solo puede fluir desde el Anode hasta el Cathode, pero no en la dirección opuesta no es posible
![[Pasted image 20250326064155.png]]

Símbolo eléctrico: ![[Pasted image 20250326064805.png]]

En condiciones ideales:
- Un diodo es un cable de polarización directa
- Un diodo es un circuito abierto en polarización inversa

ejemplo polarización directa

![[Pasted image 20250326065115.png]]
En estos casos es como si el Diodo se convirtiera en un alambre

ejemplo polarización inversa

![[Pasted image 20250326065430.png]]
En estos caso el Diodo se comporta como un circuito abierto, la condición de circuito abierto significa que no hay corriente


Un Diodo más real muestra una caída de voltaje debido a la conducción. Cuando la corriente atraviesa el Diodo es cuando se presenta la caída del voltaje, esta caída depende de varios factores pero normalmente esta entre 0,3 y 4.7 inclusivo. El voltaje de la fuente debe ser mayor que la caída de voltaje para exista un flujo de corriente  

![[Pasted image 20250326070858.png]]

Ejercicio: Para el circuito la caída de voltaje 1 es 0.8 V y la caída de voltaje 2 es 1.5 V. Encontrar la potencia de cada elemento en condiciones ideales y reales

![[Pasted image 20250326071308.png]]

Digamos que el voltaje de la fuente es 5 V

En condiciones ideales:
![[Pasted image 20250326071517.png]]

![[Pasted image 20250326071859.png]]

![[Pasted image 20250326072113.png]]

En condiciones reales:
![[Pasted image 20250326071723.png]]

![[Pasted image 20250326072149.png]]

## Algunas aplicaciones de los Diodos

- Rectificación de corrientes alternas para convertir de alterna a directa
- En corriente directa para la regulación de voltaje normalmente para estabilizarlo
- Indicadores e iluminación(emisores de luz)

### Diodo emisor de luz(LED) 

Un tipo de Diodo con la propiedad de emitir fotones de luz cuando una corriente eléctrica pasa por ellos, los fotones pueden ser luz visible, luz infrarroja o luz ultravioleta
![[Pasted image 20250326080243.png]]

![[Pasted image 20250326080741.png]]

Los Diodos tiene que tener polarización directa para generar luz. La potencia de la luz es proporcional a la corriente del led.

Un led muy especial es llamado RGB led, este led tiene 3 Diodos, uno para cada color, la unión de estos tres Diodos se conoce como tanto como Cathode común o anode común dependiendo de por donde estén juntos

![[Pasted image 20250326081627.png]]

Nota: cuando ponemos un led este debe ir acompañado por una resistencia 

Una buena corriente para un led es cercana a 20 mA, basado en eso podemos despejar otros elementos por ejemplo la resistencia 
![[Pasted image 20250326082831.png]]

La resistencia de un led suele estar entre 100$\ohm$ y 300$\ohm$ para un voltaje de 5 V
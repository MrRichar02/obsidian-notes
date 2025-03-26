[[Lenguajes y expresiones regulares]] para regresar al anterior
[[Indice teoría de lenguajes y lab]] para regresar al indice

Son autómatas no deterministicos que tienen un conjunto de estados, un alfabeto, un 
estado inicial, una función de transición delta y un conjunto de estados de aceptación
se le llama de transición $\large{\lambda}$ porque puede avanzar de un estado a otro 
espontáneamente sin recibir algún símbolo gracias a $\large{\lambda}$, una cadena w es aceptada 
por un AFN-$\large{\lambda}$ si existe una trayectoria desde q0 cuyas etiquetas sean los símbolos 
de  w intercalado por 0 o mas $\large{\lambda}$s 

ejm
![[Pasted image 20240907210804.png]]

este autómata acepta cadenas como 

aab, abaa y abbaa

Se tiene la e.r $\large{a^*b^*c^*}$ un autómata AFN-$\large{\lambda}$ que la acepta es el siguiente 

![[Pasted image 20240907211501.png]]

Si se observa se puede ver que las concatenaciones se reemplazaron con $\large{\lambda}$ 

veamos otro ejemplo 

Se tiene un AFD para detectar cadenas con un numero par de aes

![[Pasted image 20240907220109.png]]

y otro AFD para detectar cadenas con un numero par de bes 

![[Pasted image 20240907220149.png]]

si se quisiera hacer un AFN-$\large{\lambda}$ que detecte cadenas con un numero par de aes o de 
bes sería 

![[Pasted image 20240907221511.png]]

con el ejemplo anterior podemos notar como se representa la unión usando las 
transiciones $\large{\lambda}$ simplemente se crea un estado inicial y de el salen dos flechas 
disparados con $\large{\lambda}$ y estas flechas van al estado inicial de las dos expresiones
respectivamente, para este ejemplo una va al inicial de ADF que detecta los 
números pares de aes y la otra va al ADF que detecta los números pares de bes


aplicando lo anterior veamos un ejemplo final 

![[Pasted image 20240907222852.png]]

primero se inicia formando los AFN-$\large{\lambda}$ que representen lo mas interno de la e.r

para ab

![[Pasted image 20240907222942.png]]

aquí simplemente se usa la forma de representar concatenación 

para ba

![[Pasted image 20240907223048.png]]

otra simple concatenación 

para ab + ba 

![[Pasted image 20240907223116.png]]

ahora usamos la definición de la unión para juntar los dos anteriores 

para ( ab + ba )* 

![[Pasted image 20240907223449.png]]

para representar el asterisco al final de la e.r vamos a poner una flecha de regreso al 
estado inicial que se active con $\large{\lambda}$, así va a ser en general cuando se use el * en una 
expresión grande 

para a*(ab U ba)*

![[Pasted image 20240907223842.png]]

agregamos al inicio el a con * y la concatenación con lo demás que ya teníamos en el 
anterior 

para b U a*

![[Pasted image 20240907224609.png]]

lo mismo pa la unión y se coloca al a tomando en cuenta que tiene *

para a(b U a*)

![[Pasted image 20240907224707.png]]

aquí simplemente se concatena al inicio la a 

para a*(ab U ba)* U a(b U a*)

![[Pasted image 20240907224752.png]]

aquí simplemente combinamos usando la definición de la unión las dos expresiones 
separadas que habíamos obtenido 

[[gramaticas regulares]]
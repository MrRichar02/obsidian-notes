[[Minimización y equivalencia AFD]] para regresar al anterior
[[Indice teoría de lenguajes y lab]] para ir al indice 

Un autómata finito no deterministico se diferencia porque desde un mismo estado se 
puede ir a 0 o mas estados recibiendo el mismo símbolo

veamos un ejemplo de un AFN

![[Pasted image 20240825133408.png]]

Tiene los mismo componentes que un AFD solo que no tiene una función sino una 
relación lo que le permite que de un estado se vaya a varios con el mismo símbolo

![[Pasted image 20240825133555.png]]

Observemos el ejemplo anterior pero en forma de tabla 

![[Pasted image 20240825142408.png]]
como vemos ahora tenemos conjuntos para el resultado de estado símbolo y también
pueden estar vacíos 


<b>Equivalencia entre AFD y AFN:</b>

Primero tenemos que expresar nuestro AFN y lo que nos resulte lo vamos a llamar M, 
por ejemplo para 
![[Pasted image 20240825144319.png]]
nos quedaría de la siguiente manera 

![[Pasted image 20240825144344.png]]

Ahora debemos crear M', para eso debemos fusionar los conjuntos que tengan mas 
de un estado en un nuevo estado y al conjunto vacío le asignamos un estado nuevo

por ejemplo para el anterior nos queda la siguiente tabla 

![[Pasted image 20240825144822.png]]

Para los estados nuevos derivados de conjuntos serán estados de aceptación si 
al menos uno de los estados del conjunto es un estado de aceptación. Ahora 
veamos como que en forma de diagrama 

![[Pasted image 20240825145631.png]]

Si miramos bien podremos observar que el estado q1 no esta y esto es porque con los
cambios se volvió un estado inalcanzable ya que si miramos la tabla ninguna 
combinación nos lleva a q1, entonces para el diagrama no se coloca ya que no aporta


[[Lenguajes y expresiones regulares]]
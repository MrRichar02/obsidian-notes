Un AFD es un modelo computational donde el estado futuro depende de el 
estado presente y de la entrada actual 

<b>Un AFD tiene :</b>

un alfabeto de entrada que se representa con $\large{\Sigma}$, una colección de estados finita que 
se representa con Q, un estado inicial que se representa con s, una colección de 
estados de aceptación( el estado de aceptación es el estado al que buscamos llegar 
para que se puede cumplir una acción ) esta colección se representa con F y 
finalmente se tiene una función de transición de estados que se representa con $\large{\delta}$ 

<b>Ejemplo de un AFD:</b>

![[Pasted image 20240813212923.png]]

En la tabla de transición se define el estado al que se ira si se encuentra cierto 
símbolo $\large{\sigma}$ y cierto estado $\large{q_x}$ 

![[Pasted image 20240813213220.png]]

El diagrama de transición de estados es otra forma de representar, en este diagrama 
la flecha de entrada que inicia desde lo blanco representa al estado inicial, cada 
estado tiene un punto cuando ese punto esta encerrado en un circulo significa que 
este estado es el estado de aceptación 

<b>Estados muertos:</b>

Un estado muerto es un estado que no es el de aceptación y ademas al llegar a el no 
hay forma de salir de el ya que cada entrada nos llevara al mismo estado 
ejm:

![[Pasted image 20240813215121.png]]

<b>Autómatas incompletos:</b>

Son aquellos en los cuales no se especifican el resultado de la función $\large{\delta}$ para todas 
las posibles combinaciones de los símbolos del alfabeto $\large{\Sigma}$ con los diferentes estados 
Q, una manera de completarlos es añadiendo un estado muerto para sea el resultado
para las funciones $\large{\delta}$ no especificadas 
ejm:

![[Pasted image 20240813215606.png]]

[[Minimización y equivalencia AFD]]
[[ondas de presion y densidad en ondas estacionarias]] para ir al anterior
[[Indice física de ondas]] para ir al indice 

regla mano derecha de x a y, de y a z, de z a x 

$\large{ \vec{k}}$ es el vector del numero de onda que tiene componentes en x, y, z, anteriormente k 
solo se acompañaba de una coordenada pero ahora se va a acompañar por un vector
con componentes en las 3 dimensiones que vamos a representar como $\large{\vec{r}}$ 

$\large{\vec{k} . \vec{r}}$ me da la dirección de la onda

para obtener k debemos sacarle la magnitud al vector $\large{\vec{k}}$ 

ejm

![[Pasted image 20240915142240.png]]

aqui vemos como obtener los componentes de k, solo debemos ver que letra exta 
acompañando y con eso sabemos si es en x, y o z y si no esta alguna significa que 
vale 0 

para el ejemplo queremos saber si es A-A, N-N, A-N, N-A para eso primero 
calculamos algunas cositas  

![[Pasted image 20240915142753.png]]

luego graficamos 

![[Pasted image 20240915142827.png]]

primero evaluamos con el $\large{\vec{r}}$ del origen, al reemplazar eso nos da cero entonces 
sabemos que empieza así N- ahora nos falta encontrar en el punto B 

necesitamos hallar los ángulos que resaltamos en la gráfica 

![[Pasted image 20240915143114.png]]

para eso usamos el triangulo formado con k al descomponerlo en sus componentes 
de x y z 

![[Pasted image 20240915143311.png]]

![[Pasted image 20240915143338.png]]

ahora con el angulo podemos encontrar el zB haciendo otro triangulo 

![[Pasted image 20240915143443.png]]

![[Pasted image 20240915143502.png]]

![[Pasted image 20240915143519.png]]

ahora repetimos pero para encontrar xB 

![[Pasted image 20240915143619.png]]

![[Pasted image 20240915143624.png]]

![[Pasted image 20240915143650.png]]

![[Pasted image 20240915143708.png]]

ahora que tenemos las dos coordenadas en B podemos calcular el valor, el resultado 
nos da diferente de 0 por lo que en B es un antinodo osea que el sistema es N-A 

Ya vimos que la ecuación del desplazamiento depende de un vector $\large{\vec{r}}$ y el tiempo t 
osea que nos quedaría $\large{\xi ( \vec {r}, t)}$ y recordemos que la forma en que presentamos a las 
ondas viajeras 

$\Large{ \frac{\partial ^2 \xi}{\partial ^2 t} = v^2\frac{\partial ^2 \xi}{\partial ^2 x}}$ 

En este caso solo tomamos en cuenta una dimensión pero como ahora estamos 
trabajando  en 3 dimensiones tenemos que usar el vector $\large{ \vec{r}}$ 

$\Large{ \frac{\partial ^2 \xi}{\partial ^2 t} = v^2(\frac{\partial ^2 \xi}{\partial ^2 x} + \frac{\partial ^2 \xi}{\partial ^2 y} + \frac{\partial ^2 \xi}{\partial ^2 z})}$   

de esta ecuación podemos sacar a $\large{\xi}$ de factor común lo que nos dejaría 

$\Large{ \frac{\partial ^2 \xi}{\partial ^2 t} = v^2(\frac{\partial ^2 }{\partial ^2 x} + \frac{\partial ^2 }{\partial ^2 y} + \frac{\partial ^2 }{\partial ^2 z})\xi}$ 

$\large{\vec{\nabla}}$. se conoce como el operador divergencia y equivale al conjunto de las derivadas 
parciales 

$\large{\vec{\nabla}. \vec{\nabla} = \nabla ^2}$ el resultado de este operador es conocido como el naplaciano, usandolo 
la ecuación de la onda viajera nos queda 

$\Large{ \frac{\partial ^2 \xi}{\partial ^2 t} = v^2 \nabla ^2 \xi ( \vec{r}, t)}$   

[[pulsos]]
[[lentes delgados]] para ir al anterior 
[[Indice física de ondas]] para ir al indice 

![[Pasted image 20241130103402.png]]
el hueco por el que pasan los rayos de luz se le conoce como fuente, podemos tener 1 o varias de estas 

con dos fuentes vemos que se producen dos campos eléctricos
![[Pasted image 20241130103521.png]]
que luego de ser sumados nos darían la interferencia, con este resultado podemos saber si es constructiva osea un antinodo o destructiva osea un nodo 

se conoce como pantalla hasta donde llega los rayos de luz luego de salir de las fuentes
se conoce como dispositivo al objeto que tiene los agujeros que producen las fuentes, los agujeros deben de tener el mismo ancho y largo, aunque en la imagen vemos sus anchos 

Separaciones:

la primera separación que tenemos es desde el inicio de ambos agujeros 
![[Pasted image 20241130104058.png]]

la segunda separación sería desde el final de ambos agujeros 
![[Pasted image 20241130104153.png]]
la tercera separación es desde la mitad de ambos agujeros 
![[Pasted image 20241130104549.png]]

las tres separaciones deben ser iguales 

vamos a representar la distancia desde el dispositivo hasta la pantalla usando D
![[Pasted image 20241130104832.png]]

para definir un sistema cartesiano vamos a medir la tercera separación, osea desde la mitad de ambos agujeros y la vamos a llamar a, en la mitad de a trazamos una linea punteada que sea perpendicurlar a a y con esas dos lineas
ya nos quedaría el plano cartesiano 
![[Pasted image 20241130105123.png]]

cuando ponemos la pantalla podemos ver que luego de que los rayos de luz pasan por los agujeros van a formar un patron en la pantalla, donde podemos observar unos máximos y mínimos
![[Pasted image 20241130105341.png]]
para obtener esos máximos y mínimos debemos de sumar los dos campos eléctricos lo que nos da un campo eléctrico total, con este podemos calcular la intensidad
$$
\begin{aligned}
&\large{I = \frac{1}{2}*c*\epsilon_{0}*E^2}
\end{aligned}
$$
donde E representa el campo eléctrico total 

veamos otras definiciones, tenemos que $\large{r_{1} \text{ , } r_{2}}$ son las distancias desde los extremos de la linea a hasta un punto definido en la pantalla 
![[Pasted image 20241130115333.png]]

usando estas variables y las definiciones de los campos eléctricos llegamos a la siguiente formula

$$
\begin{aligned}
&\large{\delta = K * \Delta r } \\ \\
&\large{\delta = \frac{2\pi}{\lambda} * (a * \sin(\theta))} \\ \\
&\large{\frac{\delta}{2} = \frac{\pi}{\lambda} * a * \sin(\theta)}
\end{aligned}
$$

usando la definición anterior podemos obtener una ecuación para el campo eléctrico total 

$$
\begin{aligned}
&\large{E_{total} = 4 * E_{01}^2 * \cos^2\left( \frac{\delta}{2} \right)} \\ \\
&\large{E_{total} = 4 * E_{01}^2 * \cos^2\left( \frac{\pi}{\lambda} * a * \sin \theta \right)} \\ \\
\end{aligned}
$$
Luego con estas formulas podemos definir la intensidad, para la intensidad vamos a crear una nueva variable $\large{I_{0}}$ para el resultado de varias constantes para que no se haga muy larga la ecuación 

$$
\begin{aligned}
&\large{I_{0} = \frac{1}{2} * c * \epsilon_{0} * 4 * E_{01}^2} \\ \\
&\large{I = I_{0} * \cos^2\left( \frac{\pi}{\lambda} \right) * a \sin \theta}
\end{aligned}
$$
según la función que nos quedó en la formula de I esta tendrá una gráfica similar a lo siguiente 

![[Pasted image 20241130130837.png]]

si nos fijamos la gráfica es muy similar a lo que vemos cuando ponemos en la pantalla 
![[Pasted image 20241130105341.png]]

para saber cuando vamos a tener máximos y cuando mínimos debemos de saber cuando la función cos² vale 1 y cuando vale 0 

el caso de los máximos lo tenemos cuando se cumple lo siguiente 

$$
\begin{aligned}
&\large{\frac{\pi}{\lambda} * a * \sin \theta = m * \pi} \\ \\
&\large{\frac{\delta}{2} = m * \pi} \\ \\
&\large{\delta = 2 * m * \pi}
\end{aligned}
$$
donde m es un entero 
todos estos máximos tienen la misma intensidad y entre ellos siempre hay un mínimo 

En el caso de los mínimos existen cuando se cumple lo siguiente 
$$
\begin{aligned}
&\large{a * \sin \theta = (2 * m - 1) * \frac{\lambda}{2}} \\ \\
&\large{\delta = 2 * (m - 1) * \pi}
\end{aligned}
$$
Luego usando la aproximación paraxial podemos llegar a las siguientes ecuaciones 

$$
\begin{aligned}
&\large{a * \Delta \theta = \Delta m * \lambda} \\ \\
&\large{\Delta \theta = \Delta m * \frac{\lambda}{a}}
\end{aligned}
$$

gracias a lo anterior puedo definir una distancia constante entre todos los m máximos que es $\Huge{\frac{\lambda}{a}}$ 
![[Pasted image 20241130154109.png]]

ademas con la formula de $\large{\Delta \theta}$ podemos hallar el ángulo entre dos m máximos pero este ángulo nos saldrá en radianes 


[[ejemplo interferencia OEM1]]


[[difraccion en OEM 1 agujero]]
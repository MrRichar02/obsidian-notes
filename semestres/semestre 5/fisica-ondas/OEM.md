[[ecuaciones de maxwell]] para ir al anterior 
[[Indice física de ondas]] para ir al indice

onda electro magnética(O.E.M)

veamos un ejemplo de como representar ambas ondas en un gráfico 

![[Pasted image 20240926112214.png]]

ya que la velocidad es constante y es la de la luz podemos crear una relación entre la longitud de onda y de frecuencia, junto al espectro electromagnético podemos deducir que 
mientras mayor sea la frecuencia de la onda, mayor sera la energía de la onda.

Si nos fijamos en el gráfico anterior podemos ver que los campos presentados E, B y K mantienen una transversalidad entre si, por esta razón los campos se definen con productos punto

$\Large{\vec{B} = }\Huge{\frac{1}{\omega}}\Large{\vec{K} \times \vec{E}}$     

$\Large{\vec{B} \perp \vec{K}, \vec{E} \perp \vec{E}, \vec{B} \perp \vec{E}}$ 

Ya que los campos siempre van a ser perpendiculares a la dirección de propagación, las ondas eléctricas y magnéticas siempre van a ser trasversales y nunca longitudinales 

$\Large{\vec{E} = }\Huge{\frac{1}{\omega}}\Large{\vec{K} \times \vec{B}}$     

Hagamos un ejemplo con los campos de la gráfica 

$\Large{c = \lambda f}$ 

$\Large{f = }\Huge{\frac{c}{\lambda}}$  

$\Large{\omega = 2\pi f}$ 

$\Large{\vec{E} = 10 sen(K_z - \omega t)\hat{u}_x}$  también es equivalente lo siguiente $\Large{E_x = 10 sen(K_z - \omega t)}$ 

$\Large{\vec{B} = }\Huge{\frac{1}{\omega}}\Large{\vec{K} \times \vec{E}}$      

$\Large{\vec{K} = ( 0, 0, K)}$ 
$\Large{\vec{E} = ( E_x, 0, 0)}$ 

$$
\begin{aligned}
= \frac{1}{\omega}
\begin{pmatrix}
+u_x & -u_y & +u_z \\
0 & 0 & K \\
E_x & 0 & 0
\end{pmatrix}
\end{aligned}
$$
Ahora saco la determinante usando el método que tapa filas y columnas y nos queda

$\Large{\vec{B} = }\Huge{\frac{1}{\omega}} \Large{(\hat{u}_y K \vec{E}_x)}$   

$\Large{\vec{B} = (0, B_y, 0)}$ 

Ahora veamos como podemos interpretar alguna ecuación que nos den en un ejercicio, en este caso tenemos la siguiente 

![[Pasted image 20240927100322.png]]

En este caso se refiere a la ecuación de un campo eléctrico, podemos ver que K esta acompañada de x entonces la onda se esta propagando a lo largo del eje x, pero los $\Large{u_z, u_z}$ nos 
indican que el campo eléctrico esta oscilando en los ejes Y y Z, gracias a esto podemos deducir que el campo tiene un carácter vectorial y se puede descomponer en sus componentes 
Y y Z, usando esto podemos representar el campo en dos campos diferentes, el campo eléctrico en el eje Z $\Large{E_z}$ y el campo eléctrico en el eje y $\Large{E_y}$, con esto podemos formular lo siguiente 
$\Large{\vec{E} = E_z + E_y}$, otra cosa que podemos deducir es la velocidad angular, que es la que acompaña a la t en la formula, para nuestro ejemplo seria $\Large{6\pi \times 10^{16}}$, otra cosa para hacer es 
simplificar las expresiones de $\Large{E_z}$ porque si vemos tenemos un b de $\Huge{-\frac{\pi}{2}}$ lo que significa que podemos trasformar ese sen en un -cos. La interpretación del máximo valor de los campos en en
los diferentes ejes tiene la misma interpretación ya que son cuando la función cos o la sen valen 1 y -1 dependiendo de si es máximo negativo o positivo 

Polarización:

para encontrar la forma de polarización de se debe de sumar las ecuaciones del campo en los ejes a ambos lados, osea que el lado izquierdo de tanto $\Large{E_z}$ como de $\Large{E_z}$ lo mismo al lado 
izquierdo, solo que ambos lados antes de sumarse se elevan al cuadrado, también antes de elevarlos al cuadrado se pueden intercambiar cosas de un lado a otro, un truco es solo dejar lo 
trigonométrico en un lado para llegar a la expresión de sen²+cos² que equivale a 1, veamos un ejemplo para ilustrar mas lo anterior 

![[Pasted image 20240927122328.png]]

![[Pasted image 20240927122228.png]]

en este caso es una polarización elíptica por la forma con que quedo la ecuación 

Una igualdad importante para modificar las ecuaciones que nos vayan dando es $\Large{Kc = \omega}$ ; $\Huge{\frac{K}{\omega} = \frac{1}{c}}$ donde c es la velocidad de la luz 

Energía OEM:

vector de poynting se representa como $\Large{\vec{S}}$, nos da cuanta energía promedio por unidad de tiempo y unidad de area transportan las OEM, $\Large{\vec{S}}$ es paralelo con $\Large{\vec{K}}$ porque siempre 
van en la misma dirección, la magnitud de $\Large{\vec{S}}$ representa la energía por unidad de tiempo y unidad de area lo que es la intensidad, pero en este caso debe ser la intensidad promediada
esto significa que si me salen funciones trigonométricas al cuadrado la vamos a promediar a $\Huge{\frac{1}{2}}$, el vector $\Large{\vec{S} = C² \epsilon_0 \vec{E} \times \vec{B}}$  para el producto cruz sacamos la determinante 
de ambos vectores, veamos un ejemplo para ponerlo mas en perspectiva

![[Pasted image 20240927130833.png]]

las moradas son las componentes del campo eléctrico y las rojas las componentes del campo magnético , en el ejemplo anterior luego de hacer los calculos nos queda lo siguiente 

![[Pasted image 20240927131026.png]]

(ignorar las ces arriba del resultado), ahora hay que promediar las funciones trigonométricas entonces la intensidad promediada nos quedaría 

![[Pasted image 20240927131300.png]]

existe otra forma de calcular la intensidad que es mas rápida pero mas propensa a que nos equivoquemos usándola, veamos como se hace 

![[Pasted image 20240927131540.png]]
lo siguiente es calcular la magnitud o del campo magnético o del campo eléctrico usando las ecuaciones 

$\Large{\vec{B} = }\Huge{\frac{1}{\omega}}\Large{\vec{K} \times \vec{E}}$     

ó 

$\Large{\vec{E} = -}\Huge{\frac{c²}{\omega}}\Large{\vec{K} \times \vec{B}}$     

en nuestro ejemplo usaremos la del campo magnético 

![[Pasted image 20240927131959.png]]

![[Pasted image 20240927132036.png]]
se multiplica al final por $\Huge{\frac{1}{2}}$  porque la intensidad esta promediada 

ahora pa sacar la magnitud de $\Large{\vec{E}}$ sumamos sus componentes al cuadrado, todo adentro de una raíz cuadrada, luego con la magnitud ya podemos sacar la intensidad promedio 

La radiación electromagnética puede incidir en una superficie y esta superficie puede ser absorbente, osea que absorbe toda la radiación, o refelctiva, osea que refleja toda la radiación
Recordemos que Energía = mc·c donde m es masa y c es la velocidad de la luz también recordemos que P = mc donde P es momentum, entonces Energía = P·c y P = Energía/c, también 
recordemos  que Fuerza = $\Huge{\frac{mc}{t} = \frac{P}{t} = \frac{Energía}{c·t}}$, entonces la presión que es producida por la incidencia de la radiación electromagnética se puede definir como Fuerza/Area entonces 

presión de radiación = $\Huge{\frac{Energía}{Area·c·t}}$ luego de unas trasformaciones nos queda que la presión de radiación = $\Huge{\frac{I}{c}}$ con I como intensidad y c como la velocidad de la luz, lo anterior es
para superficies absorbentes, ahora para superficies reflecitvas debemos multiplicar el momentum por 2 ya que en estos casos el momentum es el doble porque se suma el que llega 
y el que se refleja, al realizar estos ajustes nos queda que la presión de radiación = $\Huge{\frac{2I}{c}}$

Ahora que podemos calcular la presión de radiación también podemos despejar la fuerza y el area ya que recordemos que presión es Fuerza/Area, en el caso donde la superfice es absorbente 
obtenemos lo siguiente $\Huge{\frac{F}{A} = \frac{I}{c}}$ entonces $\Large{F = }\Huge{\frac{IA}{c}}$ 


[[reflexion y refraccion de la luz]]
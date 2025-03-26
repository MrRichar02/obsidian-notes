[[OEM]] para ir al anterior 
[[Indice física de ondas]] para ir al indice 

El caso a estudiar es muy parecido a temas ya vistos respecto a cambios de sistemas, ya que vamos a tener una OEM incidente que se desplaza primero en un medio y al chocar con otro
genera una reflexión y trasmisión, lo que causa que se deban estudiar ambos medios donde estos medios compartes algunas variables como la frecuencia pero luego tienen otras
que van a ser diferentes para cada medio, en este caso tendremos entre otras $\large{V_1, V_2, \lambda_1, \lambda_2, K_1, K_2}$ lo nuevo que se agrega respecto a lo que habíamos visto anteriormente es que 
asignamos una dirección usando ángulos a las ondas resultantes y también a la incidente.

Vamos a llamar punto de incidencia al punto donde la onda chocha con la interfaz, a ese punto le trazo una recta que vamos a llamar normal la cual esta en una angulo de 90 respecto
a la interfaz, si nuestra onda chocha con el punto de incidencia de forma paralela a la normal, osea que tiene un angulo de 90 respecto a la interfaz, se llama incidencia normal 

![[Pasted image 20241010082608.png]]

Por otro lado si nuestra onda choca con el punto de incidencia siendo paralelo a la interfaz, osea formando un angulo de 90 con la normal se llama incidencia rasante 

![[Pasted image 20241010082750.png]]

Finalmente tenemos la incidencia oblicua la cual se presenta cuando la onda se presenta entre la normal y la interfaz formando ángulos diferentes de 90 o 0. En la mayoría de los casos
nos interesará calcular el ángulo que se forma entre la onda y la normal 

![[Pasted image 20241010083124.png]]

en el caso de que ambos medios sean iguales se presenta que 
![[Pasted image 20241010083230.png]]

pero si los medios son diferentes 

![[Pasted image 20241010083335.png]]

A este tipo de planos se les conoce como plano de incidencia, este tipo de planos debe tener siempre los 3 vectores K y debe representar la dirección de cada uno 


Relaciones de la velocidad con el medio

La velocidad de la luz en el vacío, entonces V en el aire = C, pero en el agua V = 0.75C, esto es porque la velocidad se va a aver afectada por una nueva propiedad del medio la cual es 
llamada  indice de reflexión que se representa con "n", entonces tenemos que V = C/n 

recordemos la formula $\large{V = \lambda f}$ en este caso tanto la frecuencia es constante para ambos medios pero la velocidad y la longitud de onda varían por cada medio, gracias a lo anterior 
podemos sacar una relación muy importante la cual es $\large{n_1 \lambda_1 = n_2 \lambda_2}$ (nota: a veces se conoce a la longitud de onda del medio 2 como longitud de onda relativa 

<b>Leyes</b>

Para llegar a las leyes se trata a la onda como un cilindro de luz que abarca entre dos puntos de incidencia a la interfaz 

![[Pasted image 20241010125059.png]]

usando lo anterior y el frente de onda que se refiere a una linea que corta en este caso a las dos lineas que hacen referencia a los puntos de incidencia en un ángulo de 90

![[Pasted image 20241010125258.png]]
y los puntos en el frente de onda se pueden considerar iguales entre si, gracias a lo anterior podemos encontrar mas relaciones como 

![[Pasted image 20241010125615.png]]

en este caso ? = $\large{\theta_i}$ 

ahora vamos a añadir el reflejado 

![[Pasted image 20241010125854.png]]

ahora agreguemos el trasmitido

![[Pasted image 20241010125934.png]]

ahora vamos a agregar unos puntos en los frentes de onda 

![[Pasted image 20241010130133.png]]

En este caso el que parece una 0 representa a D y por la propiedad de que todos los puntos dentro de un frente de onda son iguales, podemos decir que AC = BD por ende 
$\large{t_{AC} = t_{BD}}$, entonces

$\Huge{\frac{AC}{V_1}} \large{ = }\Huge{\frac{BD}{V_1}}$ 

ahora saquemos otras relaciones pero ahora sera trigonométricas

Sen$\large{\theta_r}$ = AC/AD entonces reemplazando el primer tiempo nos queda 

$\Huge{ \frac{AD sen\theta_r}{V_1}}$ =

otra relación es sen$\large{\theta_i}$ = BD/AD

$\Huge{ \frac{AD sen\theta_r}{V_1}}$ =$\Huge{\frac{ADsen\theta_i}{V_1}}$ 

Luego de cancelar algunas cosas nos queda que 

$\large{sen\theta_r = sen\theta_i}$ 

$\large{\theta_r = \theta_i}$: segunda ley 

agregamos otro punto 

![[Pasted image 20241010131321.png]]

Con esto se agrega otra relación $\large{t_{AC} = t_{BD} = t_{AE}}$ 

$\Huge{\frac{AC}{V_1}} \large{ = }\Huge{\frac{BD}{V_1}} \large{ = } \Huge{\frac{AE}{V_2}}$  

$\Huge{ \frac{AD sen\theta_i}{V_1}}$ =$\Huge{\frac{ADsen\theta_t}{V_2}}$ 

$\large{V_2sen\theta_i = V_1sen\theta_t}$ 

$\Huge{\frac{c sen\theta_i}{n_2} = \frac{c sen\theta_t}{n_1}}$ 

$\large{n_1 sen\theta_i = n_2 sen\theta_t}$: tercera ley de Snell


La primera ley se refiere a que el gráfico que contiene a los tres vectores, los ángulos y que los vectores son coplanares

Que sucede si el indice de refracción del medio 1 es mayor que el del medio dos?

Lo que puede ocurrir es que al ir aumentando el ángulo $\large{\theta_i}$ se llegue a un punto donde el ángulo $\large{\theta_t}$ sea aproximadamente 90 y eso hace que lo trasmitido viaje paralelo a la interfaz, a 
este fenómeno se le conoce como el fenómeno de la reflección total interna

[[ejemplo fibra optica]]
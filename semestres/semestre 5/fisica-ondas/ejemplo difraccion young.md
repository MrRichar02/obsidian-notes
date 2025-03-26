[[difraccion de young]] para volver 

Los rectángulos negros de la Figura son las dos rendijas de un dispositivo de Young. Cada cuadrado pequeño mide 0.1mm de lado. El dispositivo se ilumina con luz de longitud de onda λ = b/150, donde b es el ancho de una de
las rendijas. Halle
![[Pasted image 20241201154004.png]]
(a) la separación de las rendijas 

b = 0.1 mm
a = 0.25 mm

(b) el orden de los máximos principales que pierden por coincidir con mínimos de difracción

para resolver este punto debemos de usar las siguientes ecuaciones y llevarlas a cuando coinciden 
$$
\begin{aligned}
&\large{b \sin \theta = m^\text{"} \lambda \text{ para los mínimos }} \\ \\
&\large{a \sin \theta = m \lambda \text{ para los máximos} } \\ \\
\end{aligned}
$$
para llegar a cuando coinciden vamos a simplificar las ecuaciones aprovechando que ambas tienen $\large{ \sin \theta \text{ y } \lambda}$, lo que nos deja con lo siguiente 

$$
\begin{aligned}
&\large{ \frac{a}{b} = \frac{m}{m^\text{"}} } \\ \\
&\large{ 2.5 = \frac{m}{m^\text{"}} } \\ \\
\end{aligned}
$$
el valor mínimo en la relación para que me de 2.5 es 5/2, entonces el orden de los máximos sería 5 luego 10 luego 15 y así y si aumentamos el máximo con multiplicación debemos hacer lo mismo para el mínimo, pero como nos 
piden que el orden donde se pierde por coincidir con la difracción nos habla del caso donde coinciden un máximo con un mínimo lo que anula el máximo como en el siguiente ejemplo 
![[Pasted image 20241201155648.png]]

(c)Grafique, hasta el tercer mínimo de difracción, el patrón de difracción de campo lejano para este dispositivo 

ahora para graficar la intensidad lo que vamos a hacer es poner en el eje x tanto a m como a $\large{m\text{"}}$ y en y podemos el eje de intensidad 
![[Pasted image 20241201160744.png]]
lo que se hace es superponer las dos gráficas y lo que queda encerrado entre ambas que en este caso se resalto con morado sería lo de la gráfica total, para encontrar esa separación de $\large{\lambda / b}$ lo que se hizo fue 
![[Pasted image 20241201160908.png]]
ese 5 sería como desde el mínimos -1 hasta el mínimo 1 y ya con eso en mente partimos lo demás 

(d) Cuántos máximos principales completos contiene el máximo central de difracción

el numero de máximos que contiene el máximo central siempre es un numero impar, en el caso del ejemplo es 5 

(e)cuál es el orden del máximo más lejano que se puede, en principio, observar en la pantalla, y a qué ángulo?

ya que estamos hablando de máximos vamos a usar la formula $\large{a \sin \theta = m \lambda}$ ademas, para encontrar este $\large{\theta}$ vamos a ilustrar la situación 
![[Pasted image 20241201175600.png]]

si nos fijamos vemos que entre mas grande sea el ángulo mayor sera a donde lleguemos, en esta situación el ángulo máximo que podemos usar es 90 por eso este será el valor de $\large{\theta}$ ahora reemplazamos en la ecuación
$$
\begin{aligned}
&\large{a \sin(90) = m \lambda} \\ \\
&\large{a = m \lambda} \\ \\
&\large{\frac{a}{\lambda} = m} \\ \\
&\large{\text{del enunciado tenemos que } \lambda = \frac{b}{150}} \\ \\
&\large{\frac{a}{\frac{b}{150}} = m } \\ \\
&\large{\frac{a}{b} * 150 = m} \\ \\
&\large{\frac{0.25}{0.1} * 150 = m = 375} \\ \\
\end{aligned}
$$
375 es el máximo mas grande que se puede obtener pero fallamos en algo que nos preguntaron y es que este debe ser posible de observar en la pantalla, si el ángulo es de 90 este nunca llegara a la pantalla, entonces debemos ir 
restando de 1 en 1 al 375 y luego despejando el ángulo que obtenemos hasta que el ángulo no sea 90, empecemos desde 374

$$
\begin{aligned}
&\large{a \sin \theta = m \lambda} \\ \\
&\large{a \sin \theta = 374 \lambda} \\ \\
&\large{\sin \theta = \frac{374}{a}\lambda} \\ \\
&\large{\theta = \sin^{-1}\left( \frac{374}{a} \frac{b}{150} \right)} \\ \\
&\large{\theta \approx 85.8 \neq 90} \\ \\
\end{aligned}
$$

ya que el $\large{\theta}$ es diferente de 90 ese será el ángulo que vamos a usar y 374 sería el máximo que vamos a usar 


(f) Cuál es la intensidad de este máximo en términos de $\large{I_{0}}$ 

para calcular esto usamos la formula de la intensidad 

$$
\begin{aligned}
&\large{I = I_{0}\left[ \frac{\left( \sin\left( \frac{\pi}{\lambda} b \sin \theta \right) \right)}{\frac{\pi}{\lambda} b \sin \theta}  \right]^2 \cos^2 \left( \frac{\pi}{\lambda} a \sin \theta \right)} \\ \\
&\large{\text{antes de nada recordemos que según el resultado del punto anterior } a \sin \theta = 374 \lambda \text{ ; } \frac{a\sin(\theta)}{\lambda} = 374 \text{ entonces podemos reemplzar en la formula de intensidad}} \\ \\
&\large{I = I_{0}\left[ \frac{\left( \sin\left( \frac{\pi}{\lambda} b \sin \theta \right) \right)}{\frac{\pi}{\lambda} b \sin \theta}  \right]^2 \cos^2 \left( \pi * 374\right)} \\ \\
&\large{I = I_{0}\left[ \frac{\left( \sin\left( \frac{\pi}{\lambda} b \sin \theta \right) \right)}{\frac{\pi}{\lambda} b \sin \theta}  \right]^2 * 1} \\ \\
&\large{\text{ahora para simplificar la parte de la difracción vamos a usar el siguiente truco } \frac{a}{b} = 2.5 \text{ ; } \frac{a\sin(\theta)}{\lambda} = 374 \text{ ; } \frac{2.5\sin(\theta)}{\lambda} = 374 \text{ ; } \frac{b\sin(\theta)}{\lambda} = \frac{374}{2.5} \text{ entonces podemos reemplzar }} \\ \\
&\large{I = I_{0}\left[\frac{\sin\left( \pi * \frac{374}{2.5} \right)}{\pi * \frac{374}{2.5}}\right]^2 * 1} \\ \\
&\large{I = I_{0} * 4.095 *10^{-6} * 1} \\ \\
\end{aligned}
$$



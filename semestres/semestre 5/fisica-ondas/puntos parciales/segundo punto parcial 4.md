En el gráfico se ilustra un dispositivo de N rendijas iguales y uniformemente espaciadas. El ancho de cada rendija es de 1.5 mm. Las rendijas son iluminadas con un láser de longitud de onda de 605 nm. En la grafica tome x= 25.5 mm

![[Pasted image 20241209181250.png]]
b = 1.5 mm
$\large{\lambda}$ = 605 nm = 605E-9
x = 25.5 mm
N = 4

a. [1/3] ¿Cuál es el orden del primer máximo principal que se pierde por coincidir con mínimos de difracción?

25.5 = 4a + 1.5 ; 4a = 24; a = 6mm = 6E-3

a/b = m/m" = 6/1.5 = 4/1

b. [1/3] ¿Cuál es el tamaño angular en rad del lóbulo central de difracción?

el lóbulo central va desde el máximo principal de orden -4 hasta el máximo principal de orden 4, ambos máximos tienen el mismo tamaño angular, entonces podriamos calcular el de uno de ellos y multiplicarlo por 2 

$$
\begin{aligned}
&\large{a \sin \theta = m \lambda} \\ \\
&\large{\text{usando la aproximación paraxial}} \\ \\
&\large{a \theta = m \lambda} \\ \\
&\large{\theta = \frac{m\lambda}{a} = 0.000403 = 403E-6 } \\ \\
&\large{2 \theta = 806E-6} \\ \\
\end{aligned}
$$
c. [2/3] Ilustre el patrón completo de intensidad, mostrando la función de difracción, la función de interferencia y los máximos principales que contiene el lóbulo central. 

$$
\begin{aligned}
&\large{N - 2 = \text{número de máximos secundarios entre los máximos principales} = 2} \\ \\
&\large{N - 1  = \text{número de mínimos entre los máximos principales} = 3} \\ \\
\end{aligned}
$$

![[Pasted image 20241209190052.png]]

d. [1/3] Determine en función de Io la intensidad del primer máximo secundario, ubiquelo contando desde el origen.

el primer máximo secundario esta entre m' = 1 y m ' 2 entonces podemos hacer lo siguiente para calcular su máximo

$$
\begin{aligned}
&\large{\text{primero saquemos unas expresiones para simplificar }} \\ \\
&\large{\theta_{\text{máximo secundario}} = \frac{\theta_{1} + \theta_{2}}{2} = \frac{ \frac{m'_{1}\lambda}{aN} + \frac{m'_{2}\lambda}{aN} }{2} = \frac{\frac{(m'_{1} + m'_{2})\lambda}{a N}}{2} = \frac{(m'_{1} + m'_{2})\lambda}{2aN} = \frac{3\lambda}{8a}  } \\ \\
&\large{\frac{a\sin(\theta)}{\lambda} = \frac{3}{8}} \\ \\
&\large{\frac{4b\sin(\theta)}{\lambda} = \frac{3}{8} \text{  ;  } \frac{b\sin(\theta)}{\lambda} = \frac{3}{32}} \\ \\
&\large{I = I_{0} \left[ \frac{\sin\left( \frac{\pi}{\lambda} b \sin \theta \right)}{\frac{\pi}{\lambda} b \sin \theta} \right]^2\left[ \frac{\sin\left( N \frac{\pi}{\lambda} a \sin \theta \right)}{\sin\left( \frac{\pi}{\lambda} a \sin \theta \right)} \right]^2}\\ \\
&\large{I = I_{0} \left[ \frac{\sin\left(\frac{3\pi}{32}\right)}{\frac{3\pi}{32}} \right]^2\left[ \frac{\sin\left(\frac{3N\pi}{8}\right)}{\sin\left(\frac{3\pi}{8}\right)} \right]^2 = 1.138 I_{o}  }\\ \\
\end{aligned}
$$

![[Pasted image 20241209190228.png]]

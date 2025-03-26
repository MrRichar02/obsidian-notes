[[difraccion con n fuentes]] para volver

![[Pasted image 20241207192703.png]]
determinar a y b según la imagen 

b sería 1mm
para sacar a usamos la siguiente relación observada en el dibujo 7 = 4a + 1, lo que nos deja con que a es 1.5

ahora usamos la relación de a/b = m/m" para hallar los máximos principales que coinciden con los mínimos y por ende se vuelven mínimos, en este caso encontramos 3/2, 6/4 y 9/6

ahora grafiquemos la intensidad para eso primero debemos obtener el numero de máximos secundarios entre máximos principales y de mínimos entre máximos principales

máximos secundarios = N -2 = 5 - 2 = 3
mínimos = N -1 = 5 - 1 = 4
![[Pasted image 20241207210412.png]]
ahora pongamos el sombrero mexicano, para saber cuanto abarca el máximo en 0 del sombrero mexicano usamos lo siguiente 

$$
\begin{aligned}
&\large{\frac{\Delta \theta d}{\Delta \theta i} = \frac{\frac{2\lambda}{b}}{\frac{\lambda}{a}} = 2 \frac{a}{b} = 3}
\end{aligned}
$$
esto significa que el máximo en 0 abarca 3 por la parte del eje negativo y el positivo osea que 1.5 para el negativo y 1.5 para el positivo, luego cada máximo del sombrero abarcaría en total solo 1.5
![[Pasted image 20241207210934.png]]

de la siguiente manera es como debemos de contar los mínimos entre los máximos principales, el 0 no cuenta como mínimo 
![[Pasted image 20241207211448.png]]

de las ecuaciones de los máximos principales y lo mínimos entre máximos principales podemos como que llegar a una conclusión 
![[Pasted image 20241207211931.png]]
lo anterior no se puede cumplir porque en un espacio no puede haber un máximo y un mínimo al mismo tiempo por lo que cuando eso se pueda cumplir debemos de ignorar y continuar al siguiente como en el siguiente ejemplo 
![[Pasted image 20241207212140.png]]


ahora calculemos el $\large{\theta}$ para m' = 11, usando la aproximación paraxial nos queda lo siguiete

$$
\begin{aligned}
&\large{N a \sin \theta = m' \lambda} \\ \\
&\large{\theta = \frac{m'lambda}{a N}} \\ \\
&\large{\theta = \frac{11\lambda}{5a}} \\ \\
&\large{\text{Inventemos que } \lambda \text{ vale 550 nm}} \\ \\
&\large{\theta = \frac{11 * 550 * 10^{-9}}{5 * 1.5 * 10^{-3}} = } \\ \\
\end{aligned}
$$

ahora intentemos sacar el $\large{\theta}$ de el máximo secundario que esta justo luego del mínimo m' = 11
![[Pasted image 20241207212939.png]]
para hacer esto primero calculemos el $\large{\theta}$ de m' = 12, lo que nos queda $\Huge{\theta = \frac{12\lambda}{5a}}$ con esto podemos obtener el $\large{\theta}$ entre m' = 11 y m' = 12,  esto lo podemos dividir por 2 y lo que nos de sumarlo al $\large{\theta}$ de m' = 11 lo que nos daría 
el $\large{\theta}$ del máximo secundario que esta después del mínimo m' = 11, al final nos queda que  

$$
\begin{aligned}
&\large{\theta_{\text{máximo secundario}} = \frac{\theta_{11} + \theta_{12}}{2} } \\ \\
&\large{\theta_{\text{máximo secundario}} = \frac{\left( \frac{11\lambda}{5a} + \frac{12\lambda}{5a} \right)}{2} =\frac{\left(\frac{23}{5} \frac{\lambda}{a}\right)}{2} = \frac{23\lambda}{10a}  } \\ \\
\end{aligned}
$$

ahora saquemos la intensidad 
$$
\begin{aligned}
&\large{I = I_{0} \left[ \frac{\sin\left( \frac{\pi}{\lambda} b \sin \theta \right)}{\frac{\pi}{\lambda} b \sin \theta} \right]^2\left[ \frac{\sin\left( N \frac{\pi}{\lambda} a \sin \theta \right)}{\sin\left( \frac{\pi}{\lambda} a \sin \theta \right)} \right]^2}\\ \\
&\large{\text{del calculo de los } \theta \text{ sabemos que } \frac{a\theta}{\lambda} = \frac{23}{10} \text{ y usando la aproximación paraxial lo podemos expresar como }\frac{a\sin(\theta)}{\lambda} =\frac{23}{10} \text{ entonces podemos reemplzar esto en la ecuación de la intensidad}}\\ \\
&\large{I = I_{0} \left[ \frac{\sin\left( \frac{\pi}{\lambda} b \sin \theta \right)}{\frac{\pi}{\lambda} b \sin \theta} \right]^2\left[ \frac{\sin\left(5 * \frac{23}{10}\right)}{\sin\left(\pi * \frac{23}{10}\right)} \right]^2}\\ \\
&\large{\text{ahora usamos la ecuación } \frac{a}{b} = 1.5 \text{ para simplificar otra vez } \frac{1.5b\sin(\theta)}{\lambda} = \frac{23}{10} \text{ lo que luego nos queda como }\frac{b\sin(\theta)}{\lambda} = \frac{23}{10 * 1.5} = \frac{b\sin(\theta)}{\lambda} = \frac{23}{15}}\\ \\
&\large{I = I_{0} \left[ \frac{\sin\left(\frac{\pi * 23}{15}\right)}{\frac{\pi * 23}{15}} \right]^2\left[ \frac{\sin\left(5 * \frac{23}{10}\right)}{\sin\left(\pi * \frac{23}{10}\right)} \right]^2}\\ \\
\end{aligned}
$$

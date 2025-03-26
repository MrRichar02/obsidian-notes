[[Indice diseño de circuitos digitales]] para ir al indice
[[intro a electricidad]] para ir al anterior

## Tipos de conexiones eléctricas

### Series

Dos o mas dispositivos eléctricos comparten la misma corriente 

![[Pasted image 20250319062103.png]]
la ley de ohms 

$\Large{V_{R_{1}} = R_{1}I}$

$\Large{V_{R_{2}} = R_{1}I}$
....
$\Large{V_{R_{6}} = R_{1}I}$

$\Huge{\frac{v_{1}}{R_{1} } = \frac{v_{2}}{R_{2}} = \dots \frac{v_{6}}{R_{6}}}$

![[Pasted image 20250319062603.png]]

El voltaje que prove la fuente debe ser igual a la suma de todos los voltajes

el voltaje es $\Large{V = R_{T}I}$

Ejemplo: hallar todas las corrientes y voltajes para el siguiente circuito

![[Pasted image 20250319062804.png]]

$$
\begin{aligned}
&\Large{R_{T} = 100 + 980 + 2200 = 4180 \ohm} \\ \\
&\Large{\text{Ley de ohm}} \\ \\
&\Large{V = R_{T}I ; I = \frac{V}{R_{T}} = \frac{12}{4180} = 0.00287 A = 2,87 mA } \\ \\
&\Large{V_{R_{1}} = R_{1}I = 1K * 2.87 m = 2.87V} \\ \\
&\Large{V_{R_{2}} = R_{2}I = 980 * 2.87 m = 2.81v} \\ \\
&\Large{V_{R_{3}} = R_{3}I = 2.2k * 2.87 m = 6.31V} \\ \\
&\Large{V = 12 = 1.87 + 2.81 + 6.31 = 11.99v} \\ \\
\end{aligned}
$$

### Conexión paralela

Los elementos eléctricos comparten el voltaje, este tipo de conexión es mas común que la anterior

![[Pasted image 20250319063851.png]]

$$
\begin{aligned}
&\Large{\text{Ley de ohm} V_{R_{1}} = V_{R_{2}} = V_{R_{3}} = V_{R_{4}}} \\ \\
&\Large{I_{R_{1}} = \frac{V_{R_{1}}}{R_{1}} = \frac{V_{R_{2}}}{R_{2}} = \dots \frac{V_{R_{1}}}{R_{4}}} \\ \\
&\Large{I = \sum I_{i} = I_{R_{1}} + I_{R_{2}} + I_{R_{3}} + I_{R_{4}} = \frac{V_{1}}{R_{1}} + \frac{V_{2}}{R_{2}} + \frac{V_{3}}{R_{3}} + \frac{V_{4}}{R_{4}} = V(R_{1}^{-1} * R_{2}^{-1} * R_{3}^{-1} * R_{4}^{-1})} \\ \\
&\Large{R_{T} = (R_{1}^{-1} + R_{2}^{-1} + R_{3}^{-1} + R_{4}^{-1})^{-1}}
\end{aligned}
$$


Ejemplo: encontrar todas las corrientes y sus voltajes para el siguiente circuito

![[Pasted image 20250319064726.png]]

$$
\begin{aligned}
&\Large{R_{T} = (R_{1}^{-1} * R_{2}^{-1} * R_{3}^{-1} * R_{4}^{-1})^{-1}} \\ \\
&\Large{R_{T} = (180 ^{-1} + 330 ^{-1} + 250 ^{-1})^{-1} = 79.454 \ohm} \\ \\
&\Large{V = R_{T}I = I = \frac{15}{91.454} = 0.189 A = 189 mA} \\ \\
&\Large{V_{R_{1}} = 15V = I_{R_{1}} R_{1} ; I_{R_{1}} = \frac{15}{250} = 0.06 = 60 mA} \\ \\
&\Large{V_{R_{2}} = \frac{15}{330} = 45 mA} \\ \\
&\Large{V_{R_{3}} = \frac{15}{180} = 83 mA} \\ \\
&\Large{189m = 60m + 45m + 83m} \\ \\
&\Large{189m \approx  189} \\ \\
\end{aligned}
$$

Estas soluciones son  matemáticas y deben corresponder con circuitos reales. Los circuitos reales se miden usando un multimetro (Corrientes y voltajes). 

Para medir el voltaje el multimetro debe ser colocado en paralelo con el elemento
![[Pasted image 20250319065926.png]]

para medir la corriente se debe interrumpir el flujo de corriente y obligar que la corriente pase por el elemento de medida
![[Pasted image 20250319065954.png]]

para esto se usa un simulador llamado Thinkercad simulator

Los circuitos pueden ser la combinación de conexiones series/paralelas y pueden tener multiples fuentes

ejm

![[Pasted image 20250319080423.png]]

En estos casos el análisis es un poco más complicado, lo que se hace es usar la superposición, la superposición es un teorema que nos da una manera de analizar 

seque analiza el circuito apagando una fuente esto significa cambiar la fuente por un cable. Luego encontramos las corrientes y voltajes, luego apagamos la otra fuente y hacemos el mismo análisis.
la respuesta real es la suma de ambas respuestas 

por ejemplo apagamos V1(lo reemplazamos por un cable) y analizamos 

![[Pasted image 20250319081051.png]]

Luego apagamos V2 y analizamos 

![[Pasted image 20250319081250.png]]

 la respuesta real es la superposición de ambos osea sumarlos

## Consideraciones de potencia 

Un dispositivo eléctrico puede suministrar energía(fuentes) o consumirla(resistencias)  al final existe un equilibrio entre la energía que se produce y lo que se consume. La potencia es que tan rápido un dispositivo eléctrico puede suministrar energía o consumir energía

Energía = Fuerza por distancia sus unidades son Newton por metro osea Jules 
Potencia = Energía sobre unidad de tiempo osea que las unidades de potencia son Jules sobre segundo y esto se conoce como Watt

En los componentes eléctricos la potencia es P = V * I osea Voltaje por corriente, si aplicamos la ley de ohms podemos reemplazar a I o V, con lo que nos da mas formulas para la potencia 

![[Pasted image 20250319082620.png]]

las potencias de las fuentes deben ser iguales a las potencias que consumen las resistencias 

Los elementos eléctricos suelen ser marcados en términos de potencia 

Todas la cosas conectadas a las redes eléctricas demandan potencia y energía, lo que produce mucho calor. Toda esta potencia tiene que ser suministrada 

## Existen dos tipos principales de energía eléctrica

Corriente directa (DC): Los voltajes y corrientes son suministrados por una fuente de valor constante, por ejemplo una batería de 9V

![[Pasted image 20250326061415.png]]

Corriente alterna(AC): Los voltajes y las corrientes muestran un comportamiento variante en el tiempo(usualmente en forma de ondas seno), por ejemplo los toma corrientes. AC es la forma de generación y distribución mas usada 

![[Pasted image 20250326061431.png]]

[[dispositvos electronicos]]
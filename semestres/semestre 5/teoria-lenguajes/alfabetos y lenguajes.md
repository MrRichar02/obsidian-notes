[[Indice teoría de lenguajes y lab]] Para volver al indice 

A continuación se definirán términos importantes para comprender los lenguajes y de que están compuesto  

<b>Alfabeto:</b>

Se representa con $\large{\Sigma}$ y es un un conjunto no vació de símbolos finitos, un ejemplo 
seria el alfabeto de los dígitos $\large{\Sigma=\{0,1,2,3,4,5,6,7,8,9\}}$.  Para representar un 
símbolo individual se debe de usar  $\large{\sigma}$. También son alfabetos los siguientes 
$\large{\Sigma_1\cup\Sigma_2}$,  $\large{\Sigma_1\cap\Sigma_2}$, $\large{\Sigma_1-\Sigma_2}$, $\large{\Sigma_2-\Sigma_1}$  

<b>Palabra:</b>

Es una secuencia finita de símbolos que también suele ser llamada cadena, la cadena 
vacía es una que se encuentra en todos los alfabetos y se representa como $\large{\lambda}$, las 
palabras se representan con $\large{\omega}$ 

<b>Lenguaje:</b>

Los lenguajes son conjuntos que contienen palabras definidas sobre algún alfabeto
los lenguajes se representan con L y el lenguaje vacío que no contiene cadenas se 
representa con $\large{\phi}$ 

<b>Cierre de Kleene:</b>

Es el conjunto de todas las palabras que se pueden formar con un alfabeto $\large{\Sigma}$ y se le 
representa como $\large{\Sigma^*}$ 

<b>Operaciones con palabras:</b>

Teniendo la cadena $\large{\omega}$ si se deseara denotar su longitud se debe de usar
|$\large{\omega}$|. Si se tienen dos cadenas $\large{\omega_1}$ $\large{\omega_2}$ y se deseara realizar una concatenación 
se denotaría de la siguiente manera $\large{\omega_1}$.$\large{\omega_2}$  

<b>Potencia de una cadena:</b>

Se tiene una cadena $\large{\omega}$ y un $\large{n\in N}$ , la operación $\large{\omega^n}$ seria concatenar n veces la 
cadena a si misma y para le caso especial donde n sea 0 se considera que el 
resultado da la cadena vacía osea $\large{\lambda}$ 

<b>Igualdad:</b>

Dos cadenas son iguales si tiene la misma longitud y caracteres en la misma 
posición, se denota como $\large{\omega_1}$ = $\large{\omega_1}$ 

<b>Prefijo y subfijo:</b>

Se tienen dos cadenas $\large{\omega_1}$ $\large{\omega_2}$ se considera que $\large{\omega_2}$ es prefijo de $\large{\omega_1}$ si existe alguna 
cadena $\large{\omega_3}$ que nos permite hacer lo siguiente $\large{\omega_1}$ = $\large{\omega_2}$.$\large{\omega_3}$. Para que $\large{\omega_2}$ sea subfijo
de $\large{\omega_1}$ se debe de cumplir que existe algún $\large{\omega_3}$ que nos permite hacer lo siguiente 
$\large{\omega_1}$ = $\large{\omega_3}$.$\large{\omega_2}$

<b>Subcadena:</b>

Se tienen dos cadenas $\large{\omega_1}$ $\large{\omega_2}$ se dice que $\large{\omega_2}$ es una subcadena de $\large{\omega_1}$ 
si existen las cadenas $\large{\omega_3}$ $\large{\omega_4}$ que nos permiten hacer lo siguiente 
$\large{\omega_1}$ = $\large{\omega_3}$.$\large{\omega_2}$.$\large{\omega_4}$  

<b>Inversa o traspuesta:</b>

Se tiene una cadena $\large{\omega_1 = able}$ la operación inversa nos daría lo siguiente
$\large{\omega_1^I=elba}$, ademas la operación inversa tiene una propiedad interesante que 
es que si tenemos dos cadenas $\large{\omega_1}$ $\large{\omega_2}$ y realizamos lo siguiente $\large{(\omega_1}.\large{\omega_2)^I}$ eso
sera lo mismo que tener $\large{\omega_2^I}$.$\large{\omega_1^I}$ 

<b>Operaciones con lenguajes:</b>

Sean $\large{L_1 L_2}$ dos lenguajes, se define la concatenación estos lenguajes como 
$\large{L_1.L_2}$ = $\large{ \{ \omega_1.\omega_2 | \omega_1 \in L_1 \land \omega_2 \in L_2 \}}$ por lo tanto  $\large{L_1.L_2}$ equivale a concatenar 
cada cadena de $\large{L_1}$ con cada cadena de $\large{L_2}$ para realizar la concatenación de 
lenguajes no es necesario que ambos lenguajes ya que si por ejemplo para los 
lenguajes anteriores se dijera que pertenecen a los alfabetos $\large{\Sigma_1 \Sigma_2}$ respectivamente
el alfabeto del resultado de la concatenación seria $\large{\Sigma_1 \cup \Sigma_2}$ 

<b>Identidad:</b>

Para los lenguajes y cadenas se cumple lo siguiente, teniendo la cadena $\large{\omega}$ y el 
lenguaje $\large{L}$ se cumple que $\large{\omega.\lambda=\omega=\lambda.\omega}$ y $\large{L.\{\lambda\}=L=\{\lambda\}}$ 

<b>Potencia lenguajes:</b>

L es un lenguaje y podemos definir a $\large{ L^n=(\{\lambda\},\text{si n}=0;LL^{(n-1)},\text{si n} \geq 1)}$  

<b>Unión e intersección:</b>

Sean $\large{L_1}$ $\large{L_2}$ dos lenguajes del alfabeto $\large{\Sigma}$, $\large{L_1 \cup L_2 = \{\omega /  \omega \in L_1 \text{ ó } \omega \in L_2\}}$ 
$\large{L_1 \cap L_2 = \{\omega /  \omega \in L_1 \text{ y } \omega \in L_2\}}$  

<b>Sub lenguajes:</b>

Tenemos dos lenguajes $\large{L_1}$ $\large{L_2}$ sobre el alfabeto $\large{\Sigma}$ si todas las cadenas de $\large{L_1}$ 
pertenecen también a $\large{L_2}$ se dice que $\large{L_1}$ es sub lenguaje de $\large{L_2}$ 

<b>Lenguajes iguales:</b>

Se dice que dos lenguajes son iguales si contienen exactamente las mismas cadenas
y se les denota como $\large{L_1}$ $\large{L_2}$ 

<b>Complemento de un lenguaje:</b>

Se tiene un lenguaje L y un alfabeto $\large{\Sigma}$ se dice que el complemento de L es igual a 
$\large{\Sigma^*}$ - L osea todas las palabras que se pueden formar con el alfabeto menos las que
están en el lenguaje L 
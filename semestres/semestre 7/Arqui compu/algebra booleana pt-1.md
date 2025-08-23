[[Indice arqui de compu]] para ir al indice 
[[Representación de datos pt-2]] para ir al anterior 

El álgebra booleana consiste en un conjunto de elementos que tiene por los menos dos elementos y un máximo de un numero finito de elementos, este conjunto se conoce como B, ademas se cuenta con dos operadores binario {+} y {.} y con un operador unario {´} 

Axiomas del álgebra booleana:

El conjunto B tiene por los menos dos elementos a y b tal que $\large{a \neq b}$

**Propiedad de cierre** $\large{\forall a,b \in B,}$
$\large{\text{a) } a + b \in B}$
$\large{b) \text{ } a + b \in B}$

**Propiedad conmutativa** $\large{\forall a,b \in B,}$

$\large{\text{a) } a + b = b + a}$
$\large{\text{b) } a . b = b . a}$

**Propiedad asociativa** $\large{\forall a,b,c \in B,}$

$\large{\text{a) } (a + b) + c = a + (b + c) = a + b + c}$
$\large{\text{b) } (a . b) . c = a . (b . c) = a . b . c}$

Identidades
- Existe un elemento identidad con respecto al operador {+}, designado como 0, tal que a + 0 = a, $\large{\forall a \in B}$
- Existe un elemento identidad con respecto al operador {·}, designado como 1, tal que a · 1 = a, $\large{\forall a \in B}$

**Propiedad distributiva** $\large{\forall a,b,c \in B}$

$\large{\text{a) } a + (b.c) = (a+b).(a+c)}$
$\large{\text{b) } a . (b+c) = (a.b)+(a.c)}$

**Complementos** para cada $\large{a \in B}$, existe un elementos $\large{a´ \in B}$(El complementos de a) tal que,

$\large{\text{a) } a + a´ = 1}$
$\large{\text{b) } a . a´ = 0}$

## Álgebra de conmutación 

Aquí el conjunto B = {0, 1}, el operador binario {+} corresponde al OR lógico 
 y el operador {.} corresponde al AND lógico con eso se puede verificar que aún se cumplen los axiomas del álgebra booleana 
### [[tablas de verdad algebra booleana]]

### [[compuertas logicas]]

### Extensión de XOR y XNOR

#### Odd Parity (Paridad impar, 2k + 1)

Interpretación del operador XOR que regresa 1 en la salida cuando al contar el numero de 1's en la entrada obtiene un numero **impar** 

#### Even Parity (Paridad par, 2k)

Interpretación del operador XNOR que regresa 1 en la salida cuando al contar el numero de 1's en la entrada obtiene un numero **par**

### Ejemplo evaluando una función con tablas de verdad

Evalúe la función F(A,B) = AB + A´B´ para todos los valores posibles de sus variables de entrada 

Para evaluar la función partimos en varias partes la función y evaluamos esas partes hasta llegar a evaluar la función entera


| A   | B   | ${F_1(A, B) = A´}$ | ${F_2(A, B) = B´}$ | ${F_3(A,B) = AB}$ | ${F_4(A,B) = A´B´}$ | ${F(A,B) = AB + A´B´}$ |
| --- | --- | ------------------ | ------------------ | ----------------- | ------------------- | ---------------------- |
| 0   | 0   | 1                  | 1                  | 0                 | 1                   | 1                      |
| 0   | 1   | 1                  | 0                  | 0                 | 0                   | 0                      |
| 1   | 0   | 0                  | 1                  | 0                 | 0                   | 0                      |
| 1   | 1   | 0                  | 0                  | 1                 | 0                   | 1                      |
A continuación una imagen de como se vería el circuito para la función 

![[Pasted image 20250822130412.png]]

### Orden en que se aplican las operaciones

- Signos de agrupación 
- NOT
- AND
- OR

### Principio de dualidad 

Cualquier expresión algebraica sigue siendo valida si intercambiamos los OR por AND y los 0 por 1 o viceversa, por ejemplo 

X + 1 = 1 y su otra versión versión que se conoce como versión dual sería esta X . 0 = 0 lo cual es correcto 

### [[teoremas algebra booleana mas usados]]

### Equivalencia de expresiones algebraicas 

Para probar que dos expresiones algebraicas se debe cumplir al menos una de las siguientes condiciones 

- Que al trasformar las expresiones usando los axiomas se llegue a la misma expresión
- Que el resultado de la tabla de valor sea igual para las $2^n$ combinaciones posibles 

Veamos un ejemplo donde se comprueba la equivalencia usando la tabla de verdad 

SI tenemos 
${F_1(X, Y, Z) = XY + XY´Z + X´YZ}$
${F_2(X, Y, Z) = XY + XZ + YZ}$

| XYZ | XY  | XY´Z | X´YZ | XZ  | YZ  | ${F_1(X, Y, Z) = XY + XY´Z + X´YZ}$ | ${F_2(X, Y, Z) = XY + XZ + YZ}$ |
| --- | --- | ---- | ---- | --- | --- | ----------------------------------- | ------------------------------- |
| 000 | 0   | 0    | 0    | 0   | 0   | 0                                   | 0                               |
| 001 | 0   | 0    | 0    | 0   | 0   | 0                                   | 0                               |
| 010 | 0   | 0    | 0    | 0   | 0   | 0                                   | 0                               |
| 011 | 0   | 0    | 1    | 0   | 1   | 1                                   | 1                               |
| 100 | 0   | 0    | 0    | 0   | 0   | 0                                   | 0                               |
| 101 | 0   | 1    | 0    | 1   | 0   | 1                                   | 1                               |
| 110 | 1   | 0    | 0    | 0   | 0   | 1                                   | 1                               |
| 111 | 1   | 0    | 0    | 1   | 1   | 1                                   | 1                               |
En este caso podemos ver que al final se obtienen los mismos resultados con ambas funciones para todas las posibles combinaciones 

[[algebra booleana pt-2]] para ir al siguiente
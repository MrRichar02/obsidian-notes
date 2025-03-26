Integrantes:
Jhoan Esteban Echeverri Villa
Ricardo Medina Herrera

(1) Dado el alfabeto $\large{\Sigma}$ = {0, 1}, definir una máquina de Turing que acepte el lenguaje L = {w $\large{\in}$ {0, 1}$^*$, $\large{n_{0}(w) = n_{1}(w)}$}. 

M = ({q0, q1_0, q2_0, q1_1, q2_1, qf}, $\large{\Sigma}$, $\Gamma$, $\large{\delta}$, q0, B, {qf})

$\large{\Sigma}$ = {0, 1}

$\large{\Gamma = \Sigma}$   U {X, Y, B}

| $\large{\delta}$ | 0            | 1            | X            | Y            | B   |
| ---------------- | ------------ | ------------ | ------------ | ------------ | --- |
| -> q0            | (q1_0, X, R) | (q1_1, Y, R) | (q0, X, R)   | (q0, Y, R)   | qf  |
| q1_0             | (q1_0, 0, R) | (q2_0, Y, L) |              | (q1_0, Y, R) |     |
| q2_0             | (q2_0, 0, L) |              | (q0, X, R)   | (q2_0, Y, L) |     |
| q1_1             | (q2_1, X, L) | (q1_1, 1, R) | (q1_1, X, R) |              |     |
| q2_1             |              | (q2_1, 1, L) | (q2_1, X, L) | (q0, Y, R)   |     |

![[Pasted image 20241126231928.png]]

(2) Dado el alfabeto $\large{\Sigma}$ = {0, 1, 2}, sea M la máquina de Turing definida de la siguiente manera:

M = ({q0, q1, q2, q3, q4, qf}, $\large{\Sigma}$, $\Gamma$, $\delta$, q0, B, {qf})

donde $\large{\Gamma = \Sigma}$ U {X, Y} y $\large{\delta}$ es la función de transición definida mediante el siguiente diagrama de transiciones: 

![[Pasted image 20241126153820.png]]

a) Describir el lenguaje L(M)

L = {$\large{0^n 1^n 2^+}$: n > 0}

b) Definir un autómata a pila determinista que acepte L(M)

reglas de sustitución:

(q0, 0, z0) -> (q1, 0z0)
(q1, 0, 0) -> (q1, 00z0)
(q1, 1, 0) -> (q2, z0)
(q2, 1, 0) -> (q2, z0)
(q2, 2, z0) -> (q3, z0)
(q3, 2, z0) -> (q3, z0)
(q3, $\large{\lambda}$, z0) -> (q0, z0)

ejemplo de uso: 00112

(q0, 0, z0) -> (q1, 0z0)
(q1, 0, 0) -> (q1, 00z0)
(q1, 1, 0) -> (q2, 0z0)
(q2, 1, 0) -> (q2, z0)
(q2, 2, z0) -> (q3, z0)
(q3, $\large{\lambda}$, z0) -> (q0, z0)

c) ¿Cuál sería la configuración final después de ejecutar la máquina de Turing M cuando la configuración inicial es $q_{0}$ 0011222

$q_{0}$ 0011222 $\vdash$ X$q_{1}$ 011222 $\vdash$ X0$q_{1}$ 11222 $\vdash$ X$q_{2}$ 0Y1222 $\vdash$ $q_{2}$ X0Y1222 $\vdash$ X$q_{0}$ 0Y1222 $\vdash$ XX$q_{1}$ Y1222 $\vdash$ XXY$q_{1}$ 1222 $\vdash$ XX$q_{2}$ YY222 $\vdash$ X$q_{2}$ XYY222 $\vdash$ XX$q_{0}$ YY222 $\vdash$ XXY$q_{3}$ Y222 $\vdash$ XXYY$q_{3}$ 222 $\vdash$ XXYY2$q_{4}$ 22 $\vdash$ XXYY22$q_{4}$ 2 $\vdash$ XXYY222$q_{4}$ B $\vdash$ XXYY222B $q_{f}$ 

la configuración final sería XXYY222B$q_{f}$ 

(3) Dado el alfabeto $\large{\Sigma}$, definir una máquina de Turing que acepte el lenguaje formado por las cadenas que contienen al menos un símbolo x, un símbolo y y un símbolo z (considerar que al inicio de la cadena  entrada siempre hay un símbolo en blanco, esto es la configuración inicial para cualquier cadena de entrada w es BwBB, con la cabeza de lectura/escritura situada en el primer símbolo de la izquierda de la  cadena w).

M = ({q0, q1, q2, q3, q4, q5, q6, q7 qf}, $\large{\Sigma}$, $\Gamma$, $\delta$, q0, B, {qf})

$\large{\Sigma}$ = {0, 1}

$\large{\Gamma = \Sigma}$   U {B}


|     | x          | y          | z          | B          |
| --- | ---------- | ---------- | ---------- | ---------- |
| q0  |            |            |            | (q1, B, R) |
| q1  | (q2, x, L) | (q1, y, R) | (q1, z, R) |            |
| q2  |            | (q2, y, L) | (q2, z, L) | (q3, B, R) |
| q3  | (q3, x, R) | (q4, y, L) | (q3, z, R) |            |
| q4  | (q4, x, L) |            | (q4, z, L) | (q5, B, R) |
| q5  | (q5, x, R) | (q5, y, R) | (q6, z, R) |            |
| q6  | (q6, x, R) | (q6, y, R) | (q6, z, R) | (q7, B, R) |
| q7  |            |            |            | (qf, B, R) |

![[Pasted image 20241127113521.png]]

(4) Dado un alfabeto $\large{\Sigma}$ = {a, b, c}, definir una máquina de Turing que acepte el lenguaje formado por las cadenas no vacías tal que el primer símbolo de cada cadena no vuelva a aparecer en el resto de la  cadena.

M = ({q0, q1, q2, q3, qf}, $\large{\Sigma}$, $\Gamma$, $\delta$, q0, B, {qf})

$\large{\Sigma}$ = {a, b, c}

$\large{\Gamma = \Sigma}$   U {B}

|     | a          | b          | c          | B          |
| --- | ---------- | ---------- | ---------- | ---------- |
| q0  | (q1, a, R) | (q2, b, R) | (q3, c, R) |            |
| q1  |            | (q1, b, R) | (q1, c, R) | (qf, B, R) |
| q2  | (q2, a, R) |            | (q2, c, R) | (qf, B, R) |
| q3  | (q3, a, R) | (q3, b, R) |            | (qf, B, R) |

![[Pasted image 20241127133901.png]]

(5) Dado el alfabeto $\large{\Sigma}$ = {a, b, c}, definir una máquina de Turing que acepte el lenguaje

M = ({q0, q1, q2, q3, q4, q5, q6, qf}, $\large{\Sigma}$, $\Gamma$, $\delta$, q0, B, {qf})

$\large{\Sigma}$ = {a, b, c}

$\large{\Gamma = \Sigma}$   U {B, X, Y, Z}

$$
\begin{aligned}
&\large{L = \{ a^n b^n c^{2n} : n > 0 \}}
\end{aligned}
$$


|     | a          | b          | c          | X          | Y          | Z          | B          |
| --- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| q0  | (q1, X, R) |            |            |            | (q5, Y, R) |            |            |
| q1  | (q1, a, R) | (q2, Y, R) |            |            | (q1, Y, R) |            |            |
| q2  |            | (q2, b, R) | (q3, Z, R) |            |            | (q2, Z, R) |            |
| q3  |            |            | (q4, Z, L) |            |            |            |            |
| q4  | (q4, a, L) | (q4, b, L) |            | (q0, X, R) | (q4, Y, L) | (q4, Z, L) |            |
| q5  |            |            |            |            | (q5, Y, R) | (q6, Z, R) |            |
| q6  |            |            |            |            |            | (q6, Z, R) | (qf, B, R) |

![[Pasted image 20241127133548.png]]

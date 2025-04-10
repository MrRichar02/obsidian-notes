En este documento pongo tabla pero eso también puede significar relación y cabecera columna 

$\Large{\sigma}$ esto representa una condición, para aplicar a las tuplas que deseamos seleccionar

$\Large{\pi}$ representa la proyección y nos permite seleccionar las columnas que deseamos traer, ademas asegura que no tendremos repetidos 

X producto cartesiano, con este podemos realizar una operación de relación entre dos tablas, de esta manera tabla1 X tabla2 lo que va a hacer es que creara tuplas combinando cada tupla de la tabla1 con todas las tuplas de la tabla2

$\Large{\rho}$ nos permite renombrar columnas temporalmente para los casos donde realicemos un producto cartesiano y existan columnas con nombres iguales 

Unión $\Large{tabla_{1} \cup tabla_{2}}$: Retorna las tuplas de ambas tablas y elimina las tuplas que estén repetidas 

Intersección $\Large{tabla_{1} \cap tabla_{2}}$: retorna una tabla con las tuplas que tengan en común ambas tablas 

Diferencia $\Large{tabla1 - tabla2}$: retorna las tuplas que están en la tabla1 pero que no estan la tabla2 

Reunión $\Large{tabla_{1} \Join tabla_{2}}$: tiene varias modalidades la primera es la natural, en este caso se va a retornar una tabla de tuplas que va a tener tuplas de la combinación de cada tupla de ambas tablas donde se tenga un atributo en común, la columna del atributo en común no debe de tener necesariamente el mismo nombre, también tenemos la reunión natrual por la derecha que sería traer lo que tenga el atributo en común y todos los que tenemos en la tabla de la izquierda, al igual la reunión natural por la derecha que sería lo mismo pero con la tabla de la derecha 

División: esta operación retorna una tabla con tuplas formadas por las columnas que esten presentes en la tabla 1 pero no en la tabla2, también debe de haber una columna en común y que cada atributo de la columna en común tenga atributos de las otras columnas

la división mira que el los elementos de la columna que no es común este combinando tenga una combinación con cada elemento de la columna que es en común 

Ejercicios algebra relacional 

```

-- encontrar los vendedores que venden el producto 2
-- pi snombre (Snatural join sigma p = 'P2' (SP))

-- encontrar los vendedores que venden productos de color rojo
-- pi snombre (S natural join (SP natural join  sigma color = 'Rojo' (P)))


-- encontrar los vendedores que venden todos los productos
/*productos = pi p (P)
atributos = pi s, p (SP)
pi snombre (S natural join atributos ÷ productos)*/

```

script para crear las tablas 

```
group: Algebra relacional

 

S= {

	s		snombre 	situacion 	ciudad 

	S1 		Salazar 		20 		Londres 

	S2 		Jaramillo 	10 		Paris

	S3 		Bernal		30 		Paris 

	S4 		Caicedo 		20 		Londres 

	S5 		Aldana 		30 		Atenas 

}

 

P = {

	p 		pnombre 	color 		peso 	ciudad 

	P1 		Tuerca 		Rojo 		12 	Londres 

	P2	 	Perno		Verde 		17 	Paris

	P3 		Tornillo 		Azul 		17 	Roma 

	P4 		Tornillo 		Rojo 		14 	Londres 

	P5 		Leva 		Azul 		12 	Paris

	P6 		Rueda 		Rojo 		19 	Londres

}

 

SP = {

	s 	p 	cantidad:number 

			S1 	P1 	  300 

			S1 	P2 	  200 

			S1 	P3 	  400 

			S1 	P4 	  200 

			S1 	P5 	  100 

			S1 	P6 	  100 

			S2 	P1 	  300 

			S2 	P2 	  400 

			S3 	P3 	  200 

			S4 	P2 	  200 

			S4 	P4 	  300 

			S4 	P5 	  400 

}
```

otros ejercicios 

•Obtener los códigos de los proveedores situados en Londres y que suministran el producto P3.

```
-- Obtener los códigos de los proveedores situados en Londres y que suministran el producto P3.
pi s (SP natural join sigma ciudad='Londres' and p='P3' (SP natural join S))
```

•Obtener los códigos de los proveedores que suministran al menos todos los productos suministrados por el proveedor S2.

```
-- Obtener los códigos de los proveedores que suministran al menos todos los productos suministrados por el proveedor S2.

products = pi p (sigma s='S2' SP) 
all = pi s, p SP

(all natural join products) ÷ products

-- otra solución de un fucking goat

-- Obtener los códigos de los proveedores que suministran al menos todos los productos suministrados por el proveedor S2.

A = pi p (sigma s='S2' SP) 

pi s,p(SP) ÷ A

-- otra de un sigma void
A = sigma s='S2' (SP)
B = pi p (A)
C = pi s, p (SP natural join B)
D = sigma s≠'S2'(C÷B)
pi s (S natural join D)
```


info para el taller

```
group: Algebra relacional4

EMPLEADO = {

	emp_id     emp_nombre         edad   depto_id 

	E1         Julia        	  34     D1

	E2         Mateo        	  28     D2

	E3         Luisa       		 45     D1

	E4         Andres      		 31     D3

	E5				 Leon							19		D3

	}

 

DEPARTAMENTO = {

	depto_id     depto_nombre          ciudad_dpto

	D1           RH     					 			Bogota

	D2           Tecnologia            Medellin

	D3           Finanzas              Cali

}

 

PROYECTO = {

	proy_id     proy_nombre           ciudad_proy

	P1          Datos       				Bogota

	P2          Movil            		 Medellin

	P3          Automatizacion        Cali

}

 

ASIGNACION = {

	emp_id     proy_id     horas 

	E1         P1          20

	E2         P2          35

	E3         P1          40

	E3         P3          15

	E4         P3          30

	E3				 P2					 15

}
```

1.	Mostrar los empleados mayores de 30 años.

```
sigma edad>30 EMPLEADO
```

2.	Listar todos los nombres de empleados que trabajan en el proyecto “Datos”.

```
pi emp_nombre (EMPLEADO natural join (pi emp_id ASIGNACION natural join (pi proy_id sigma proy_nombre='Datos' PROYECTO)))
```

3.	Obtener los departamentos donde al menos un empleado trabaja más de 30 horas en cualquier proyecto.

```
DEPARTAMENTO natural join (pi depto_id (sigma horas>30 ASIGNACION natural join EMPLEADO))
```

4.	Calcular la cantidad total de horas trabajadas por cada empleado.

```
pi emp_id, total_horas ((gamma emp_id; SUM(horas) -> total_horas (ASIGNACION)) right outer join (EMPLEADO))
```

5.	Mostrar los empleados que han participado en todos los proyectos.

```
empleados = pi emp_id, proy_id ASIGNACION

proyectos = pi proy_id ASIGNACION
EMPLEADO natural join (empleados ÷ proyectos)
```

6.	Obtener la lista de empleados que trabajan en proyectos que no están en la misma ciudad que su departamento.

```
A = pi DEPARTAMENTO.depto_id, PROYECTO.proy_id (DEPARTAMENTO ⨝ DEPARTAMENTO.ciudad_dpto ≠ PROYECTO.ciudad_proy PROYECTO)

B = pi EMPLEADO.emp_id, EMPLEADO.depto_id, ASIGNACION.proy_id (EMPLEADO natural join ASIGNACION)

C = pi EMPLEADO.emp_id (B natural join A)

EMPLEADO natural join C
```

7.	Mostrar los nombres de empleados que trabajan en más de un proyecto.

```
A = (gamma emp_id; COUNT(proy_id) -> proyectos (ASIGNACION)) 
pi emp_nombre (EMPLEADO natural join (sigma proyectos > 1 A))
```

8.	Obtener los nombres de los proyectos en los que trabaja algún empleado del departamento Tecnología

```
A = pi depto_id (sigma depto_nombre='Tecnologia' DEPARTAMENTO)
B = pi proy_id (ASIGNACION natural join (EMPLEADO natural join A))

pi proy_nombre (PROYECTO natural join B)
```

9.	Obtener los nombres de empleados que no han sido asignados a ningún proyecto.

```
A = pi emp_id EMPLEADO
B = pi emp_id ASIGNACION
A - B
```

10.	Mostrar los nombres de todos los proyectos y, si tienen empleados asignados, su nombre.

```
A = pi proy_id, emp_nombre (EMPLEADO natural join ASIGNACION)

B = pi proy_nombre, emp_nombre (A natural join PROYECTO)

tau proy_nombre asc B
```

11.	Para cada ciudad por Departamento, listar cuántos empleados trabajan en proyectos que se desarrollan en esa misma ciudad.

```
A = pi depto_id, proy_id, ciudad_dpto (DEPARTAMENTO ⨝ DEPARTAMENTO.ciudad_dpto = PROYECTO.ciudad_proy PROYECTO)

B = pi emp_id, depto_id, proy_id (ASIGNACION natural join EMPLEADO)

C = A natural join B

gamma ciudad_dpto; COUNT(emp_id) -> total_proy_dpto_iguales C
```
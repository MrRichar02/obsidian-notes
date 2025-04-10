## Info para el taller

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

## Desarrollo del taller

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
pi emp_nombre (EMPLEADO natural join (A - B))
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
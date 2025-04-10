Ricardo Medina Herrera
Jeferson Alexander Del Rio Herrera

--- 
Ejercicios

1. Mostrar los empleados mayores de 30 años.
```
select * from empleado 
where edad > 30;
```

2. Listar todos los nombres de empleados que trabajan en el proyecto “Datos”.
```
select emp_nombre from empleado as e join asignacion as a
on e.emp_id = a.emp_id
join proyecto as p 
on p.proy_id = a.proy_id
where p.proy_nombre = 'Datos'
```

3. Obtener los departamentos donde al menos un empleado trabaja más de 30 horas en cualquier proyecto.
```
select d.depto_id, d.depto_nombre, d.ciudad_dpto from empleado as e join asignacion as a on e.emp_id = a.emp_id
join departamento as d on e.depto_id = d.depto_id
where a.horas > 30
```

4. Calcular la cantidad total de horas trabajadas por cada empleado.
```
select e.emp_id, e.emp_nombre, sum(a.horas) from empleado e
join asignacion a on e.emp_id = a.emp_id
group by e.emp_id
```

5. Mostrar los empleados que han participado en todos los proyectos.
```
select e.emp_nombre from empleado e
join asignacion a on e.emp_id = a.emp_id
group by e.emp_id
having count(e.emp_id) = (select distinct count(proy_id) from proyecto)
```

6. Obtener la lista de empleados que trabajan en proyectos que no están en la misma ciudad que su departamento.
```
select distinct e.emp_nombre from empleado e, departamento d, asignacion a, proyecto p
where e.emp_id = a.emp_id and
e.depto_id = d.depto_id and
p.proy_id = a.proy_id and
d.ciudad_dpto <> p.ciudad_proy
```

7. Mostrar los nombres de empleados que trabajan en más de un proyecto.
```
select e.emp_nombre from empleado e , asignacion a
where e.emp_id = a.emp_id group by e.emp_id
having count(e.emp_id) > 1
```

8. Obtener los nombres de los proyectos en los que trabaja algún empleado del departamento Tecnología
```
SELECT p.proy_nombre
FROM proyecto p
INNER JOIN asignacion a ON p.proy_id = a.proy_id
INNER JOIN empleado e ON a.emp_id = e.emp_id
INNER JOIN departamento d ON e.depto_id = d.depto_id
WHERE d.depto_nombre = 'Tecnologia';
```

9. Obtener los nombres de empleados que no han sido asignados a ningún proyecto.
```
select e.emp_nombre from empleado e
left join asignacion a on e.emp_id = a.emp_id 
where a.proy_id is null
```

10. Mostrar los nombres de todos los proyectos y, si tienen empleados asignados, su nombre.
```
select p.proy_nombre, e.emp_nombre from proyecto p
inner join asignacion a on p.proy_id = a.proy_id
inner join empleado e on e.emp_id = a.emp_id
order by p.proy_nombre
```

11. Para cada ciudad por Departamento, listar cuántos empleados trabajan en proyectos que se desarrollan en esa misma ciudad.
```
select d.ciudad_dpto, count(e.emp_id) from departamento d
inner join empleado e on e.depto_id = d.depto_id
inner join asignacion a on e.emp_id = a.emp_id
inner join proyecto p on a.proy_id = p.proy_id
where d.ciudad_dpto = p.ciudad_proy
group by (d.ciudad_dpto)
```
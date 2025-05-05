## Integrantes:

- Ricardo Medina Herrera 
- Jeferson Alexander Del Rio Herrera  

## Crear la función para el trigger:

```
create or replace function autitoria_update_salario()
returns trigger as $$
begin
    if new.salario > (old.salario*1.2) then
        insert into audit_empleados(empleado_id, old_salary, new_salary, changed_on, fue_aprovado, responsable_cambio, motivo) values (old.empleado_id, old.salario, new.salario, now(), false, session_user, 'Aumento salario');
        return old;
    end if;

    insert into audit_empleados(empleado_id, old_salary, new_salary, changed_on, fue_aprovado, responsable_cambio, motivo) values (old.empleado_id, old.salario, new.salario, now(), true, session_user, 'Aumento salario');    

    return new;
end;
$$ language plpgsql;
```

## Crear el trigger:

```
create or replace trigger auditoria_salario_update
before update on empleados 
for each row
execute function autitoria_update_salario();
```

## Update de prueba:

```
update empleados
set salario = 3002
where empleado_id = 1;
```

## Select para mostrar la tabla de empleados:

```
select * from empleados;
```

## Select para mostrar la tabla de audit:

```
select * from audit_empleados;
```
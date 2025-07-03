## Propósito del trigger

Se va a crear un trigger que automatice la asignación de estados a los equipos. Los estados de los equipos se asignan en función de la cantidad de miembros que tenga cada equipo.

## ¿Cuando se va a ejecutar el trigger?

Este trigger se ejecutará después de que se actualice la información de un usuario, ya que el estado del equipo solo debe actualizarse si la actualización del usuario fue exitosa.

## ¿ Cómo se va a realizar?

### Verificar si el campo `id_team` cambio 

Si el valor de `id_team` no cambió respecto al valor anterior, no se realiza ninguna acción.

### Actualizar el estado del equipo anterior

Si el valor anterior de id_team no era `null`, se cuentan los miembros actuales del equipo antiguo (excluyendo al usuario que fue movido) y se actualiza su estado según la cantidad de miembros.

### Actualizar el estado del nuevo equipo

Si el nuevo valor de `id_team` no es `null`, se cuentan los miembros actuales del nuevo equipo (incluyendo al usuario recién asignado) y se asigna el nuevo estado del equipo con la misma lógica anterior.

## Consideraciones adicionales

Si el equipo anterior o el nuevo es `null`, no se realiza ninguna acción sobre ese equipo.

## Creación de función

Se usa una función para tener toda la lógica y evitar que esta este en el trigger

```
CREATE OR REPLACE FUNCTION auditoria_estado_equipo()

RETURNS TRIGGER AS $$

DECLARE

user_count INTEGER;

new_status INTEGER;

BEGIN

-- Verificamos si el id_team cambió

IF NEW.id_team IS DISTINCT FROM OLD.id_team THEN

  

IF OLD.id_team IS NOT NULL THEN

SELECT COUNT(*) INTO user_count

FROM app_user

WHERE id_team = OLD.id_team;

  

IF user_count = 0 THEN

new_status := 4;

ELSIF user_count = 1 THEN

new_status := 2;

ELSIF user_count = 2 THEN

new_status := 1;

ELSE

new_status := 3;

END IF;

  

UPDATE team

SET id_team_status = new_status

WHERE id_team = OLD.id_team;

END IF;

  

  

IF NEW.id_team IS NOT NULL THEN

SELECT COUNT(*) INTO user_count

FROM app_user

WHERE id_team = NEW.id_team;

  

IF user_count = 0 THEN

new_status := 4;

ELSIF user_count = 1 THEN

new_status := 2;

ELSIF user_count = 2 THEN

new_status := 1;

ELSE

new_status := 3;

END IF;

  

UPDATE team

SET id_team_status = new_status

WHERE id_team = NEW.id_team;

END IF;

  

END IF;

  

RETURN NEW;

END;

$$ LANGUAGE plpgsql;
```

## Creación de trigger

Ya con la función creada podemos crear el trigger con la cualidad de que se ejecute después de actualizar a un usuario

```
CREATE TRIGGER trg_update_team_status
AFTER UPDATE ON app_user
FOR EACH ROW
EXECUTE FUNCTION auditoria_estado_equipo();
```
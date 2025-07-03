## Consultas relacionadas a equipos:

#### Listar todos los miembros de un equipo por id

```
SELECT au.user_name, au.user_email, r.role_name
FROM app_user au
JOIN role r ON au.id_user_role = r.id_role
WHERE au.id_team = 1;
```

#### Obtener numero de integrantes de un equipo por id

```
SELECT COUNT(id_user) AS numero_integrantes
FROM app_user
WHERE id_team = 1;
```

#### Obtener equipos a los que se puede unir

```
select * from team t
join team_status ts on t.id_team_status = ts.id_team_status
where ts.team_status_name = 'En formación' or ts.team_status_name = 'Incompleto'
```

#### Obtener todos los equipos completos

```
select * from team t
join team_status ts on t.id_team_status = ts.id_team_status
where ts.team_status_name = 'Completo'
```

#### Listar todos los equipos con información útil

```
SELECT t.team_name, ts.team_status_name AS estado_equipo, COUNT(au.id_user) AS numero_integrantes
FROM team t
JOIN team_status ts ON t.id_team_status = ts.id_team_status
left JOIN app_user au ON t.id_team = au.id_team
GROUP BY t.team_name, ts.team_status_name
ORDER BY t.team_name;
```

## Consultas relacionadas a usuarios:

#### Obtener todos los usuarios que no pertenecen a un equipo

```
select * from app_user where id_team is null
```

#### Obtener los usuarios junto a sus equipos

```
select au.user_name, t.team_name from app_user au
join team t on au.id_team = t.id_team
```

#### Obtener los logs de un usuario por id

```
SELECT timestamp, event_name, event_description
FROM log
WHERE id_user = 5
ORDER BY timestamp DESC;
```

#### Obtener rol de un usuario por id

```
SELECT r.role_name
FROM app_user au
JOIN role r ON au.id_user_role = r.id_role
WHERE au.id_user = 1;
```

#### Obtener la información del equipo de un usuario por id

```
SELECT t.id_team, t.team_name, ts.team_status_name
FROM app_user au
JOIN team t ON au.id_team = t.id_team
JOIN team_status ts ON t.id_team_status = ts.id_team_status
WHERE au.id_user = 3;
```
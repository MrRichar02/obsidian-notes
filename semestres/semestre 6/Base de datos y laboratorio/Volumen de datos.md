## Tabla ROLE:

id_role 4 bytes max
role_name 1020 bytes max

#### Tamaño para un registro 1024 bytes max

#### Tamaño para 10 000 registros 10 240 000 bytes max

## Tabla COURSE:
  
id_course 4 bytes max
course_name 1020 bytes max
  
#### Tamaño para un registro 1024 bytes max
  
#### Tamaño para 10 000 registros 10 240 000 bytes max

## Tabla TEAM_STATUS:

id_team_status 4 bytes max
team_status_name 1020 bytes max

#### Tamaño para un registro 1024 bytes max

#### Tamaño para 10 000 registros 10 240 000 bytes max

## Table TEAM:

id_team 4 bytes max
id_team_status 4 bytes max
creator_id 4 bytes max
team_name 1020 bytes max
created_at 8 bytes max
updated_at 8 bytes max
  
#### Tamaño para un registro 1048 bytes max

#### Tamaño para 10 000 registros 10 480 000 bytes max

### Tabla APP_USER:

id_user 4 bytes max
user_email 1020 bytes max
enabled 1 byte max
user_identity_document 1020 bytes max
user_name 1020 bytes max
password 1020 bytes max
registered_at 8 bytes max
id_user_role 4 bytes max
id_user_course 4 bytes max
id_team 4 bytes max

#### Tamaño para un registro 4105 max

#### Tamaño para 10 000 registros 41 050 000 bytes max

### Tabla LOG:

id_log 4 bytes max
timestamp 8 bytes max
id_user 4 bytes max
event_name 120 bytes max
event_description 1020 bytes max
  
#### Tamaño para un registro 1156 bytes max
  
#### Tamaño para 10 000 registros 11 560 000 bytes max

## Tabla revoked_token:

id 4 bytes max
expiration 8 bytes max
revoked_at 8 bytes max
token 1073741823 bytes max 
token_type 1020 bytes max
user_email 1020 bytes max
#### Tamaño para un registro 1 074 063 867 bytes max
  
#### Tamaño para 10 000 registros 10 740 638 670 000 bytes max

## General 

#### Tamaño para un registro 1 074 073 248 bytes max
  
#### Tamaño para 10 000 registros 10 740 732 480 000 bytes max
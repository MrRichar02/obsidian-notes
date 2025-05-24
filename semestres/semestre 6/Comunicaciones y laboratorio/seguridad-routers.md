## Agregar contraseña para acceder al enable en un router

Primero entramos a modo config

```
en
conf t
```

Ahora vamos a definir una contraseña

```
enable passowrd your-password
```

al hacer esto nos va a pedir la contraseña para entrar al modo enable, pero tiene el problema de que podemos ver luego la contraseña usando `sh running-config`, lo cual no es lo más seguro por lo que exploremos una forma más segura

## Secret

Primero entramos a modo config

```
en
conf t
```

Ahora vamos a definir el secret 

```
enable secret yourt-secret
```

Nota: si ya se definió una password en la primera forma el secret no puede ser igual al definido o sino dará un error

Luego de definir el secret este será el que se nos pide para entrar al modo enable, incluso si ya habíamos definido un password anteriormente este lo va a reemplazar, la ventaja que tiene el secret respecto al password es que si ejecutamos   `sh running-config` no se va a mostar el secret tal como es, sino encriptado 


## Console

Primero entramos a modo config

```
en
conf t
```

Ahora vamos a entrar a la configuración de la consola 0 y vamos a definir una password y luego vamos activar que se pida la contraseña al momento de acceder a la consola 

```
line console 0
password your-password
login
```

si quierieramos desactivar que nos pida la contraseña para entrar a al consola primero entramos a modo config

```
en
conf t
```

Ahora entramos a la consola 0 y desctivamos el login

```
line console 0
no login
```

## Acceso remoto router

Primero entramos a modo config

```
en
conf t
```

Ahora vamos a entrar en la configuración de la consola 0 para vty y vamos a establecer una contraseña y activarla

```
line vty 0
password your-password
login
```

Con eso listo ahora se podría acceder desde un pc al router para configurarlo, solo debemos de ejecutar algo como lo siguiente en el pc

```
telnet ip-interface-router
```

donde `ip-interface-router` es la dirección IP de cualquiera de las interfaces del router

Si quisiéramos desactivar el vty para que no se puede configurar el router desde un pc remoto, debemos de primero entrar al modo config

```
en
conf t
```

luego entramos al vty desactivamos el login

```
line vty 0
no login
```

## Orden para asignar las contraseñas

- consola
- password
- secret 
- vty
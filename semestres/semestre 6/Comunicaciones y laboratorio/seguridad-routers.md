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


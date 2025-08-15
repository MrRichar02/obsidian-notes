```
mutation {
  register(
    name: "Juan Pérez"
    ssn: "123-45-6789"
    password: "superSegura123"
    email: "juan.perez@example.com"
    role: ADMIN
  ) {
    id
    name
    email
    role
  }
}
```

```
query{
  allUsers{
    id,
    name
  }
}
```

```
mutation {
  updateUser(
    id: 1
    ssn: "123-890-765"
  ) {
    id
    name
    email
    role
  }
}
```

```
mutation {
  deleteUser(
    id: 1,
  )
}
```
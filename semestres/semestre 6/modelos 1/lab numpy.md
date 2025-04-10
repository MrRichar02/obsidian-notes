Solución punto 1

```
def cauchy(x, y):

    r = np.zeros((x.shape[0], y.shape[0])) + (x.reshape(1,x.shape[0]) - y.reshape(-1,1)).T
    if len(r[r==0]) > 0:
      raise ValueError("division by zero")
    
    return 1/r
```

Solución punto 1 mejorada por gpt

```
def cauchy(x, y):
    r = x.reshape(-1, 1) - y
    if np.any(r == 0):
        raise ValueError("division by zero")
    return 1 / r
```

Solución punto 2

```
def minimo(x,v):
    return np.argmin(np.absolute(x-v))
```

Solución punto 3

```
def media(X):
    return X - np.mean(X, axis=1).reshape(-1,1)
```

Solución punto 3 por gpt

keepdims mantiene las dimensiones originales 

```
def media(X):
    return X - X.mean(axis=1, keepdims=True)
```

Solución punto 4

```
def doublediag(X):
    return X + np.eye(X.shape[0]) * X
```

Solución punto 4 por gpt

```
def doublediag(X):
    return X * (1 + np.eye(len(X)))
```
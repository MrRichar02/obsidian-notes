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


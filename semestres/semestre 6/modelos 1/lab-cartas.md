solución punto 1:

```
def make_heaps(c, n_heaps=3):
    assert n_heaps%2==1, "must have an odd number of heaps"
    assert len(c)%n_heaps==0, "the length of the deck must be a multiple of the number of heaps"
    
    h = [[np.str_(x) for x in c[i::n_heaps]] for i in range(n_heaps)]
    return h
```

solución punto 1 por gpt

```
def make_heaps(c, n_heaps=3):
    assert n_heaps % 2 == 1, "must have an odd number of heaps"
    assert len(c)%n_heaps==0, "the length of the deck must be a multiple of the number of heaps"
    
    return [list(map(np.str_, c[i::n_heaps])) for i in range(n_heaps)]
```

solución punto 2:

```
def collect_heaps(h, n):
    
    left = []
    right = []

    size_of_groups = len(h)//2

    for index, heap in enumerate(h):
      if n in heap:
        choosen_one = h.pop(index)

    for _ in range(size_of_groups):

      left.append(h.pop(np.random.randint(0,len(h))))
      right.append(h.pop(np.random.randint(0,len(h))))

    r = []

    for heap in left:
      for item in heap:
        r.append(item)

    for item in choosen_one:
      r.append(item)

    for heap in right:
      for item in heap:
        r.append(item)
    
    
    return r            
```

solución punto 2 por gpt:

```
def collect_heaps(h, n):
    # Encontrar el heap que contiene 'n' y eliminarlo de h
    choosen_one = next(heap for heap in h if n in heap)
    h.remove(choosen_one)  # Eliminamos la sublista directamente

    # Mezclamos aleatoriamente la lista h
    np.random.shuffle(h)

    # Dividimos en dos grupos
    size_of_groups = len(h) // 2
    left, right = h[:size_of_groups], h[size_of_groups:]

    # Aplanamos la lista en el orden correcto
    return [item for heap in left for item in heap] + choosen_one + [item for heap in right for item in heap]
```

solución punto 3:

```
def run(c, n, n_heaps=3):

  w = c
  for _ in range(3):
    m = make_heaps(w,n_heaps)
    w = collect_heaps(m, n)
  r = w.index(n)
  return r
```

solución punto 3 por gpt:

```
def run(c, n, n_heaps=3):
    for _ in range(3):
        c = collect_heaps(make_heaps(c, n_heaps), n)
    return c.index(n)
```
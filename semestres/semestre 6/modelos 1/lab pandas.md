solución punto 1
```
def select_items(df):
    # make sure to make a copy in case you modify the original df
    df = df.copy()
    
    if 'margin' not in df.columns:
      m = df[(df.price>100)].index
    else:
      m = df[(df.price>100) | (df.margin>10)].index
    
    result = [i for i in m]
    
    return result
```

solución punto 1 optimizada por gpt

```
def select_items(df):
    df = df.copy()
    
    margin_col = df.get('margin', pd.Series(0, index=df.index))  # Si 'margin' no existe, usa una serie de ceros
    
    m = df[(df['price'] > 100) | (margin_col > 10)].index
    
    return m.tolist()  # Convierte directamente en lista
```

solución punto 2

```
def get_stats(df):
    # make sure to make a copy in case you modify the original df
    tdf = df.copy()
        
    result = pd.DataFrame()
    result['media'] = df.groupby("category")['price'].mean()
    result['maximo'] = df.groupby("category")['price'].max()
    result['minimo'] = df.groupby("category")['price'].min()
    result.index = result.index.map(int)
    result.index.name = "categoria"
    return result
```

solución punto 2 bien insana por gpt

```
def get_stats(df):
    # Asegurar que la categoría es el índice para facilitar la agrupación
    result = df.groupby("category")['price'].agg(
        media="mean",
        maximo="max",
        minimo="min"
    )

    # Convertir los índices de categoría a enteros
    result.index = result.index.astype(int)
    result.index.name = "categoria"

    return result.reset_index()  # Devolver un DataFrame con la categoría como columna

```

solución punto 3

```
def fillna(df):
    # make sure to make a copy in case you modify the original df
    df = df.copy()
    
    mean = df.price.mean()
    std = df.price.std()

    m = df[df.isna().price].index

    for i in m:
      replace_value = np.random.normal(mean, std)
      df.loc[i,'price'] = replace_value

    result = df
    return result
```

solución punto 3 del sigma void gpt

```
def fillna(df):
    df = df.copy()  # Evita modificar el original
    
    mean = df["price"].mean()
    std = df["price"].std()
    
    # Generar valores aleatorios solo para las posiciones con NaN
    df.loc[df["price"].isna(), "price"] = np.random.normal(mean, std)

    return df
```

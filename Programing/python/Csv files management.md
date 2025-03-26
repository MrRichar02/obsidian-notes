### Native python way

#### Reading

Normalmente los archivos csv se manejan con librerías como pandas pero primero veamos como hacerlo sin ellas, para esto primero debemos de abrir el archivo con la función open(), luego importamos 
csv, con csv  podemos crear un objeto reader con el cual leer el archivo csv, para eso utilizamos el método de la librería csv llamado reader() y le pasamos como parámetro el objeto que nos dio la 
función open(), el método reader() nos retornara una interfaz con el cual podemos leer el contenido del archivo csv

#### Iterate over rows

Podemos iterar sobre las filas del archivo csv en una manera similar a un for each, veamos un simple ejemplo 

```
import csv

file = open('path/to/file.csv', 'r')

reader = csv.reader(file)

i=0
for line in reader:
  if i == 3:
    break
  print(line)
  i += 1

file.close()
```

#### Writing

Para escribir un archivo csv primero usamos la función open() en modo w luego con la librería csv llamamos el método writer para crear una interfaz con la cual podemos escribir al archivo, este método
recibe el objeto que nos retorna la función open(), un parámetro separator que indica como se van a separar la información de las filas, finalmente recibe un parámetro quoting, 

# Select

El comando select nos es de utilidad para retornar información de una o varias tablas, un comando Select inicia con la palabra SELECT seguida de uno o varios campos de los cuales queremos retornar 
la información, si queremos retornar información de todos lo campos podemos usar $*$, si vamos a retornar info de varios campos debemos de separar los nombres de los campos con comas, luego de los
campos sigue la palabra FROM, después de esta palabra debemos poner el nombre de la tabla de la cual se extraerá la información.

### Count 

Podemos utilizar la función `count()` junto al SELECT pasando como argumento $*$ para obtener el numero de registros en una tabla, veamos un ejemplo 

```
SELECT count(*) FROM users;
```

### Where

El comando where nos ayuda a filtrar nuestra búsqueda usando  select, para utilizar where solo debemos agregarlo al final de como haríamos un select normal luego de la palabra `WHERE` colocamos la condición a aplicar 
para el filtrado, veamos un ejemplo

```
SELECT name FROM users WHERE power_level >= 9000
```

# Table

### Create 

Para crear una tabla usamos las dos palabras CREATE TABLE luego colocamos el nombre de la tabla y después entre paréntesis y separados por comas ponemos el nombre de cada fila y su tipo  
veamos un ejemplo

```
CREATE TABLE employees (id INTEGER, name TEXT, age INTEGER, is_manager BOOLEAN, salary INTEGER);
```

También podemos separar los parámetros en varias lineas 

```
CREATE TABLE employees(
    id INTEGER,
    name TEXT,
    age INTEGER,
    is_manager BOOLEAN,
    salary INTEGER
);
```

### Alter

Podemos alterar las filas de una tabla para o eliminar alguna fila o añadir alguna, para esto primero vamos a usar las palabras ALTER TABLE luego colocamos el nombre de la tabla a modificar, es 
importante no colocar ";" al final de esta línea de código  luego en la siguiente línea colocamos la acción que deseemos realizar y el ";" al final

#### Rename

Si queremos renombrar la tabla podemos usar las palabras RENAME TO y luego el nuevo nombre

también podemos renombrar una columna de una manera similar, solo que ahora usaremos RENAME COLUMN luego el nombre de la columna, luego TO y por ultimo el nuevo nombre que le deseamos 
asignar a la columna 

#### Add

Si queremos añadir una columna podemos usar las palabras ADD COLUMN, después el nombre de la columna a añadir y por ultimo el tipo de la columna 

#### Drop

Si queremos eliminar una columna podemos usar las palabras DROP COLUMN y después colocamos el nombre de la columna a eliminar 

# Constraints

Un constraint es una regla que definimos para la base de datos por ejemplo podemos definir NOT NULL para una columna de alguna tabla y esa columna ya no aceptara valores NULL, para asignar 
un constraint a una columna podemos ponerlo justo después del  tipo de la columna cuando estamos creando la tabla, ejem
```
CREATE TABLE employees(
    id INTEGER PRIMARY KEY,
    name TEXT UNIQUE,
    -- The UNIQUE constraint ensures that no two rows can have the same value in the 'name' column
    title TEXT NOT NULL
    -- The NOT NULL constraint ensures that the 'title' column cannot have NULL values
);
```

### Primary key

La columna con el constraint es una columna especial que nos ayuda a identificar registros de la tabla, cada tabla puede tener solo una columna con el constraint de primary key

### Foreign key

Las foreign key definen relaciones entre tablas, la foreign key hace referencia al primary key de otra tabla, para crear un foreign key en sqlite primero debemos de crear un constraint en la tabla donde 
queremos crear el foreign key, luego asignamos a ese foreign key le asignamos le asignamos una columna de la tabla, por ultimo definimos a que tabla y que columna de esa tabla va a hacer referencia
veamos un ejemplo 
```
CREATE TABLE departments (
    id INTEGER PRIMARY KEY,
    department_name TEXT NOT NULL
);

CREATE TABLE employees (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    department_id INTEGER,
    CONSTRAINT fk_departments
    FOREIGN KEY (department_id)
    REFERENCES departments(id)
);
```

en este ejemplo la tabla con la foreign key es la tabla de employees, usando la palabra CONSTRAINT definimos la constraint fk_departments luego usando las palabras FOREGIN KEY le asignamos 
a la constraint fk_departments la columna department_id de la tabla employees, por ultimo creamos la referencia con la palabra REFERENCES luego el nombre de la tabla que es el de la tabla de 
departments y después entre  paréntesis ponemos la columna de la tabla departments a la cual vamos a hacer referencia 

# Insert

Podemos insertar registros a una tabla para eso vamos a usar las palabras INSERT INTO luego el nombre de la tabla a la que queremos insertar el registro, luego entre paréntesis y separado por comas 
ponemos los campos luego ponemos la palabra VALUES y después otra vez entre paréntesis y separado por comas ponemos lo valores para los campos que definimos anteriormente, veamos un ejem
```
INSERT INTO employees(id, name, title)
VALUES (1, 'Allan', 'Engineer');
```

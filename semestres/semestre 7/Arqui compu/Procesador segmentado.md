## Como funciona el procesamiento segmentado

Para realizar un procesamiento segmentado primero se debe de tener un proceso secuencial que se pueda dividir en varias etapas independientes, con esto se pueden realizar varias operaciones secuenciales al mismo tiempo, operando en distintas etapas para cada una

La etapa más lenta del proceso es la que va marcar el ritmo de avance porque se va a necesitar esperar hasta que esta termine, esto afecta al tiempo en que se cumple una etapa en todos los procesos, porque se debe esperar hasta que la etapa más lenta termine para avanzar en los demás procesos, lo que puede disminuir el speed up. 

### Fill

Ocurre al principio de la ejecución de los procesos y se refiere al momento donde se empiezan a iniciar todos los procesos pero no pueden iniciar a la vez porque todos tienen una etapa de inicio que no se puede ejecutar más de una vez por etapa, entonces algunos recursos no se usan durante estas etapas empeorando la productividad

### Flush

Ocurre al final de la ejecución de los procesos y se refiere al momento donde los procesos llegan a su etapa final, pero esto no ocurre al mismo tiempo, entonces algunos recursos no se utilizan por lo que se pierde productividad 

## Etapas de ejecución de una instrucción MIPS 

### IF
En esta etapa se trae a la instrucción y se actualiza el valor del pc
### ID
En esta etapa se decodifica la instrucción y con esto se deciden las salidas de la unidad de control, ademas se realiza la lectura de los registros especificados en la de-codificación
### EX
En esta etapa pueden ocurrir varias cosas dependiendo del tipo de instrucción que se este ejecutando:
- si es una aritmético lógica se realiza el calculo de la operación 
- Si es una de acceso a memoria se realiza el calculo de la dirección efectiva de acceso a memoria 
- Si es una de salto condicional se realiza la comparación especificada  
### MEM
En esta etapa es donde se realizan los accesos a la memoria, estos accesos pueden ser de lectura o de escritura 
### WB
En esta etapa es donde algunos tipos de instrucciones van a escribir su resultado obtenido sobre algunos de los registros del banco de registros 


## Riesgos (Hazards)
(nota: Vamos a suponer que una etapa de una instrucción se puede realizar en un ciclo de reloj)

Los riesgos son situaciones que ocurren en el código donde alguna instrucción no puede realizar alguna etapa de una forma continua porque de hacerlo la instrucción no realizaría lo que se supone, la solución simple a esto es que la instrucción con algún riesgo espere durante los ciclos de reloj necesarios hasta que el riesgo no exista, esta solución aunque simple no es la mejor en cuanto a rendimiento se refiere

Existen tres tipos de riegos:
- Riesgos estructurales ( Structural hazards)
- Riegos de datos( Data hazards)
- Riesgos de control( Control hazards)

### Riesgos estructurales ( Structural hazards)
Estos se presentan debido a limitaciones que tiene el hardware con el que se esta trabajando veamos algunos ejemplos:

**Ejemplo memoria**

Si tenemos solo un puerto de acceso a memoria y esta memoria guarda tanto las instrucciones como los datos, si tenemos una instrucción que va a escribir o leer la memoria en su etapa de MEM y otra instrucción que esta trayendo sus instrucciones en su etapa de IF, entonces debemos de priorizar una sobre la otra para que una pueda completar su etapa y la otra deba esperar normalmente se prioriza a la que este en una etapa más avanzada, en este casos a la instrucción que esta en la etapa de MEM.

Una solución que no compromete el rendimiento es modificar el hardware para que no se tenga una sola memoria para guardar tanto instrucciones como los datos, por lo tanto se tendra una memoria para las intrucciones y otra para los datos.

**Ejemplo instrucciones:**
```
add $t0, $t1, $t2 
add $s0, $s1, $s2
add $s3, $t1, $t3
add $s2, $t0, $s2
```

En este caso la primera instrucción realiza una suma y guarda su resultado en el registro `$t0` mientras que la ultima instrucción realiza una suma usando entre sus sumando al registro `$t0` el problema aquí es que justo se cruza cuando se esta guardando el valor de la suma de la primera instrucción en su etapa de WB y que se trae el valor de los registros en la ultima instrucción en su etapa de ID.

Una solución a la situación sin añadir descansos para alguna instrucción es definir que en la etapa de WB se escribe sobre los registros en la primera mitad del ciclo de reloj y en la etapa de ID se traen los valores de los registros en la segunda mitad del ciclo de reloj.

### Riesgos de datos (Data hazards)

Se presentan cuando una instrucción no puede iniciar debido a que esta depende de una instrucción anterior produzca un valor y esta aún no lo ha hecho, veamos un ejemplo

~~~
add $t0, $t1, $t2
sub $t3, $t0, $t4
and $t5, $t0, $t6
or $t7, $t0, $t8
nor $t9, $t0, $t9
~~~
En este caso las instrucciones sub y and  dependen del resultado que arroje la instrucción add pero al momento que ellas van a realizar su etapa de ID la instrucción add aún no a escrito el resultado sobre el registro, lo simple aquí sería esperar hasta que la instrucción add escriba el resultado sobre el registro y luego ejecutar las instrucciones
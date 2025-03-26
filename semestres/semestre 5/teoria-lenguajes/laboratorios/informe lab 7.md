Integrantes:
- Ricardo Medina Herrera

Objetivo:

Desarrollar un analizador sintáctico para una calculadora básica, que valide los tokens en una expresión matemática y muestre el resultado de la operación. El programa debe manejar errores y reportar cuál es el error si ocurre.

Desarrollo:

1. Tokenización:
Se creó una función llamada tokenize que recibe una expresión matemática como cadena de texto y la divide en una lista de tokens. Cada token representa un número, un operador, o un paréntesis. Este proceso permite al analizador interpretar correctamente los elementos de la expresión y asegura que todos los caracteres sean válidos.

2. Análisis sintáctico:
La clase Parser procesa los tokens generados por tokenize. Contiene métodos para avanzar a través de los tokens, realizar operaciones aritméticas (suma, resta, multiplicación y división), y evaluar expresiones con el uso de paréntesis, aplicando la jerarquía correcta de operaciones. Esta clase incluye métodos específicos para la verificación de tokens y el manejo de errores sintácticos.

3. Evaluación:
La función evaluate combina el proceso de tokenización y análisis. Si se detecta un error, como una operación inválida o una división entre cero, la función devuelve un mensaje descriptivo para que el usuario comprenda el problema.

4. Interfaz gráfica:
Para mejorar la usabilidad, se utiliza la librería tkinter para crear una interfaz simple con un campo de entrada para las expresiones y un botón de evaluación. La clase ExpressionEvaluator configura la interfaz gráfica y se encarga de mostrar el resultado o cualquier mensaje de error.

Resultados:

![[Pasted image 20241112214433.png]]

![[Pasted image 20241112214454.png]]

![[Pasted image 20241112214556.png]]

![[Pasted image 20241112214611.png]]

Conclusiones: 
1. Eficiencia en el Procesamiento de Expresiones Matemáticas: El código implementa un analizador sintáctico efectivo que maneja adecuadamente la tokenización y evaluación de expresiones matemáticas, logrando identificar operadores, números y paréntesis.

2. Manejo de Errores Robusto: El diseño del analizador permite capturar errores comunes como caracteres no válidos, errores de sintaxis y divisiones entre cero, proporcionando retroalimentación clara al usuario.

3. Interfaz Gráfica Intuitiva: La inclusión de una interfaz gráfica desarrollada con tkinter mejora la usabilidad del programa, permitiendo a los usuarios realizar cálculos de manera sencilla y obtener resultados rápidamente.

4. Aplicación Modular y Reutilizable: La estructura modular del código, separando la tokenización, análisis sintáctico y evaluación de expresiones, facilita la comprensión y posible ampliación del programa, haciendo que sea adaptable a otros entornos o tipos de operaciones.
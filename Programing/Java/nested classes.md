Podemos definir clases dentro de otra clase, podemos hacerlo de dos maneras static o non static, las non se conocer como inner classes y las otras static nested classes, las inner tienen acceso a todos
los fields y métodos definidos en la clase donde esta anidada, sin importar el modificador que tengan, mientras que las static classes solo tienen acceso a los métodos o atributos que tengan el 
modificador static

podemos usar cualquier modificador con una nested class 

Una inner class necesita una instancia del objeto de la clase donde esta anidada para poder instanciar un objeto de la nested class, por esto una nested class no puede usar el modificador static para 
definir métodos o fields, para crear un objeto de una nested class debemos hacer algo como esto

```
OuterClass outerObject = new OuterClass();
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

Una static class no puede referenciar fields o métodos de la clase donde esta anidada, el proceso para instanciar un objeto de esta clase es igual al de las clases que no están anidadas, las static class
se consideran clases que se definieron dentro de otras clases solo por conveniencia 

## Local classes

Las classes locales son aquellas que se declaran adentro de métodos, estas classes tienen acceso a los fields y métodos de la clase donde esta anidado el método, pero para acceder a variables 
declaradas adentro del método estas deben de tener el modificador final

## Classes anonimas

las classes anonimas son como las locales ya que se definen adentro de métodos pero no llevan nombre y se define toda la estructura de la clase al momento que estamos intentando instanciar 
un objeto, luego de poner lo de new y el nombre de la clase de que va a heredar o la interfaz que va a implementar abrimos un par de llaves y en estas definimos la clase, estas clases tienen las 
mismas restricciones para acceder a variables o métodos que las classes locales
# Convert JSON to a go struct
Cuando estamos trabajando con archivos JSON en go podemos pasar el contenido a un struct que definamos por ejemplo un struct para un usuario, para hacer algo como esto debemos crear un 
decoder y luego utilizarlo para pasar el contenido del JSON, para hacer esto podemos hacer uso de la librería `encoding/json` veamos un ejemplo 
```
package main

import (
	"fmt"
	"net/http"
	"encoding/json"
)

func getIssues(url string) ([]Issue, error) {
	res, err := http.Get(url)
	if err != nil {
		return nil, fmt.Errorf("error creating request: %w", err)
	}
	defer res.Body.Close()

	issues := make([]Issue,0) 
	decoder := json.NewDecoder(res.Body)
	if err := decoder.Decode(&issues); err != nil {
		return nil, err
	}
	return issues, nil
}
```

en el ejemplo anterior en el JSON nos llegan varios Issues para los cuales tenemos un struct definido, luego creamos el decoder con el método `NewDecoder` al cual le pasamos el body de la request que 
es donde nos llega el JSON, luego del decoder generado usamos el método `Decode` para pasar la información al slice de issues que creamos previamente, si notamos ese array es de tipo Issue que 
sería la struct que creamos para este caso en particular 

El método `decoder` basa su funcionamiento en pasar un stream de data a un io.Reader y de ahí a una struct, pero este no es el único ya que la librería `encoding/json` cuenta con otro método llamado 
`Unmarshall` este método funciona con un `[]byte`, en la mayoría de los casos vamos a usar el método `decoder` porque nos genera mayor rendimiento pero el método `Unmarshall` puede resultar útil
si tenemos poca data JSON ya almacenada en `[]byte` veamos un ejemplo donde usemos el método `Unmarshall`
```
// res is an http.Response
defer res.Body.Close()

data, err := io.ReadAll(res.Body)
if err != nil {
	return nil, err
}

var issues []Issue
if err = json.Unmarshal(data, &issues); err != nil {
    return nil, err
}
```

En el ejemplo se usa `io.ReadAll` para obtener la información en forma de un slice de bytes, luego este slice se le pasa al método `Unmasrshal` junto a el slice del tipo struct al que queremos pasar la info
del JSON

# Convert a go struct to a binary representation of JSON 

Podemos pasar de una struct de go a la representación de esta en un slice de bytes utilizando el método `Marshal` de la librería `encoding/json` para obtener el array solo debemos de llamar el método y 
pasarle la struct veamos un pequeño ejemplo 

```
type Board struct {
	Id       int    `json:"id"`
	Name     string `json:"name"`
	TeamId   int    `json:"team"`
	TeamName string `json:"team_name"`
}

board := Board{
	Id:       1,
	Name:     "API",
	TeamId:   9001,
	TeamName: "Backend",
}

data, err := json.Marshal(board)
if err != nil {
	log.Fatal(err)
}
fmt.Println(string(data))
// {"id":1,"name":"API","team":9001,"team_name":"Backend"}
```

en ejemplo creamos un struct Board luego con el método `Marshal` lo pasamos a un slice de bytes y finalmente imprimimos el slice usando la función `string` para pasar de bytes a texto

# Unknown structure

Cuando no conozcamos la estructura de nuestro JSON podemos utilizar un `map[string]interface{}` para almacenar la información del JSON, veamos un ejemplo

```
var data map[string]interface{}
jsonString := `{"name": "Alice", "age": 30, "address": {"city": "Wonderland"}}`
json.Unmarshal([]byte(jsonString), &data)
fmt.Println(data["name"])  // Output: Alice
fmt.Println(data["address"].(map[string]interface{})["city"])  // Output: Wonderland
```

En el ejemplo definimos el map, luego creamos un ejemplo de JSON, luego usamos el método `Unmarshal` al que le pasamos el JSON en bytes junto al map luego imprimimos información desde el map
en la segunda impresión al acceder al valor del key hacemos un type assertion para convertirlo a un `map[string]interface{}` ya que el valor de address es un valor anidado 

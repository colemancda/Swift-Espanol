# Bienvenidos a Swift

## Sobre Swift

[*Swift*](https://es.wikipedia.org/wiki/Swift_(lenguaje_de_programación)) es una nueva lenguaje de programmacion para applicaciones de iOS, OS X, watchOS, y tvOS que estan cimentados en lo mejor de [*C*](https://es.wikipedia.org/wiki/C_(lenguaje_de_programación)) y [*Objective-C*](https://es.wikipedia.org/wiki/Objective-C), sin las restricciones de compatibilidad con C. Swift adopta patrones de programmacion seguros y añade caracterisitacas modernas para hacer programacion mas facil, mas flexible, y mas divertido. La implementacion nueva y limpia de Swift, apoyado por las librerias maduras de [*Cocoa*](https://es.wikipedia.org/wiki/Cocoa_(informática)) y [*Cocoa Touch*](https://es.wikipedia.org/wiki/Cocoa_Touch), es una oportunidad para reimaginar como funciona el desarollo de Software.

El proceso de la creacion de Swift ha estado ocurriendo por varios años. Apple creo el cimiento para Swift cuando avanzamos nuestra infraestructura de compilador, debuggeador y librerias. Hemos simplificado manejo de memoria con [Contabilidad de Referencia Automatica](https://es.wikipedia.org/wiki/Contabilidad_de_Referencia_Automatica) (*Automatic Memory Management*, *ARC*). Nuestras librerias, construidas sobre la base solida de [*Foundation* y Cocoa](https://es.wikipedia.org/wiki/Cocoa_(informática)), ha sido modernizada y estandarizado. Objective-C mismo ha evolucionado para soportar [bloques](https://es.wikipedia.org/wiki/Clausura_(informática)), literales de colleciones, y modulos, habilitando que librerias adopten technologias de lenguajes modernas sin obstaculos. Gracias a este trabajo, podemos introducir una nueva lengauaje de desarollo para el futuro de desarollo de Software para las plataformas de Apple.

Swift se siente familiar para desarolladores de Objective-C. Adopta la legibilidad de parametros nombrados y el poder del modelo de objectos dynamicos de Objective-C. Proveee acceso sin interrupciones a librerias existentes de Cocoa y completa interoperabilidad con codigo Objective-C. Construyendo encima de esta fundacion, Swift introduce muchos nuevos conceptos y unifica las porciones procedurales y orientados a objectos del lenguaje.

Swift es amigable para nuevos programmadores. Es el primer lenguaje de programmacion de sistemas de calidad industrial que es tan expresivo y agradable como un lenguaje de *scripting*. Soporta parque de juegos (*playgrounds*), una caractrerisitca innovadora que permite programmadores experimentar con codigo Swift y ver los resultados immediatamente, sin el gasto de compilar y correr la applicacion.

Swift combina lo mejor en filosofias de lenguajes modernas con sabidura de la amplia cultura de ingeneria Apple. El compilador esta optimizado para rendimiento, y el lenguaje esta optimizada para desarollo, sin comprometer ninguno de los dos. Esta disenado para escalar de la implementacion de "```hello world```" a un sistema operativo entero. Todo esto hace que Swift sea una inversion segura para desarrolladores y Apple.

Swift is una manera fantastica para escribir applicaciones iOS, OS X, watchOS, y tvOS, y continuara evolucionandose con nuevas caracterisitcas y capabilidades. Nuestras metas para Swift son ambiciosas. No podemos esperar para ver que podras crear con ello.

## Una Guia de Swift

Tradicion sugiere que el primer programa en una nueva lenguaje de desarollo deberia imprimir las palabras "Hola, mundo!" en la pantalla. En Swift, esto se puede hacer con una sola linea de codigo:

```
print("Hola, mundo!")
```

Si has escrito codigo en C or Objective-C, este sintaxsis deberia de verse familiar para usted. En Swift, esta linea de codigo is un programa completo. No necesitas importar una libreria separada para funcionalidad como entrada y salida (*input/output* o *IO*) o manejo de texto (*string*). Codigo escrito a nivel (*scope*) global es usado como un punto de entrada para la aplicacion, entonces no necesitas una funcion ```main()```. Tampoco necesitas escribir semicolones al final de cada sentencia.

Esta guia te da suficiente informacion para empezar a escribir codigo en Swift mediante mostrandote como implementar una variedad de tareas de programmacion. No te preocupes si no entendiste algo, todo introducido en este libro esta explicado en detalle en el resto del libro.

### Valores Simples

Se usa ```let``` para crear una constante y ```var``` para crear una variable. El valor de un constante no necesita saberse a la hora de compilar, pero deberias asignarle un valor exactamente una vez. Esto significa que puedes usar constantes para nombrar un valor que se determina una vez, pero se usa en muchos lugares.

```
var miVariable = 42
miVariable = 50
let miConstante = 42
```
Una constante o variable deberia de tener el mismo tipo de valor que le quieras asignar. Sin embargo, no deberias de siempre tener que escribir el tipo explicitamente. Proveer un valor cuando creas la constante o variable, permite que el compilador dedusca su tipo. En el ejemplo de arriba, el compilador deduce que ```myVariable``` es un numero entero (*Integer*) por que su valor inicial es un numero entero.

Si el valor inicial no provee suficiente informacion (o si no hay un valor inicial), especifica el tipo via escribiendolo despues del variable, separado por un colon.

```
let enteroImplicito = 70
let doubleImplicito = 70.0
let dobleExplicita: Double = 70
```

#### Experimento
Crea una constante con un tipo explicito de ```Float``` y un valor de ```4```.

Valores nunca son implicitamente convertidos a otro tipo. Si necesitas covnertir un valor a otro tipo, explicitamente has una instancia, del tipo deseado.

```
let etiqueta: "El ancho es "
let ancho = 94
let etiquetaAncho = etiqueta + String(ancho)
```

#### Experimento
Intenta remover la conversion a ```String``` de la ultima linea. Que error te da?

Hay una manera mas simple de incluir varios valores en texto: Escribe el valor en parentesis, y escripe una barra invertida (```\```) antes de los parentesis. Por ejemplo:

```
let manzanas = 3
let narajas = 5
let manazanaResumen = "Yo tengo \(manzanas) mazanas."
let frutaResumen = "Yo tengo \(manzanas + narajas) pedazos de fruta."
```

#### Experimento
Usa ```\()``` para incluir un calculo de punto flotante en un texto y para incluir el nombre de alguien en un saludo.

Crea [arreglos](https://es.wikipedia.org/wiki/Vector_(informática)) (*array*) y [diccionarios](https://es.wikipedia.org/wiki/Vector_asociativo) (*dictionaries*) usando brackets (```[]```) y accede sus elementos escribiendo el indice (*index*) o llave (*key*) en brackets. Una comma se permite despues del primer elemento.

```
var miListaDeCompras = ["bagre", "agua", "tulipanes", "pintura azul"]
miListaDeCompras[1] = "botella de agua"

var profesiones = [
	"Malcolm": "Capitan",
	"Kaylee": "Mecanico"
]

profesiones["Jayne"] = "Relaciones Publicas"
```

Si la informacion de tipo puede ser deducida, puedes escribir un arreglo vacio como ```[]``` y un diccionario vacio como ```[:]```: Por ejemplo, cuando creas un nuevo valor para una variable, o pasas un arguemento a una funcion.

```
lista de compras = []
profesiones = [:]
```

### Control de Flujo
Usa ```if``` y ```switch``` para crear [sentencias condicionales](https://es.wikipedia.org/wiki/Sentencia_condicional), y usa ```for```-```in```, ```for```, ```while```, y ```repeat``` para hacer un [ciclo](https://es.wikipedia.org/wiki/Bucle_(programación)) (*loop*). Parentesis cerrando la condicion o ciclo son opcionales. Llaves sobre el cuerpo son requeridos.

```
let puntajesIndividuales = [75, 43, 103, 87, 12]

var puntajeDeEquipo = 0

for puntaje in puntajesIndividuales {

	if puntaje > 50 {
		puntajeDeEquipo += 3		
	} else {
		puntajeDeEquipo += 1
	}
}
print(puntajeDeEquipo)
```

En una sentencia de ```if```, el condicional deberia ser una expresion [Booleana ](https://es.wikipedia.org/wiki/Tipo_de_dato_lógico) (*Boolean*, *Bool*), lo cual significa que codigo como ```if score { ... }``` es un error, no una comparision implicita a cero. Puedes usar ```if``` y ```let``` juntos para trabajar con valores que podrian estar faltantes. Estos valores se representa como opcionales (*optionals*). Un valor opcional contiene un valor o ```nil``` (nulo) para representar que un valor esta faltando. Escribe un signo de interrogacion (```?```) despues del tipo de valor para marcar el valor como opcional.

```
var textoOpcional: String? = "Hello"
print(textoOpcional == nil)
 
var nombreOpcional: String? = "John Appleseed"
var saludo = "Hello!"
if let nombre = nombreOpcional {
    saludo = "Hello, \(name)"
}
```

#### Experimento
Cambia ```textoOpcional``` a ```nil```. Que saludo obtienes? Añade una clausula de ```else``` que setea otro saludo si ```nombreOpcional``` es ```nil```.

Si el valor opcional es ```nil```, el valor condicional es falso y el codigo en las llaves se saltea. De lo contrario, el valor opcional es desenvuelto y asignado al constante despues de ```let```, lo cual hace el valor desenvuelto disponible dentro del bloque de codigo.

Otra manera de manejar valores opcionales es proveer un valor predeterminado usando el operador ```??```. Si el valor opcional esta faltando, el valor predeterminado es usado en su lugar.

```
let apodo: String? = nil
let nombreCompleto: String = "John Appleseed"
let saludoInformal = "Hola \(apodo ?? nombreCompleto)"
```

[Interruptores](https://es.wikipedia.org/wiki/Switch_case) (*switch*) soportan cualquier tipo de datos y una amplia variedad de operaciones de comparacion: no estan limitados a numeros enteros y preubas de igualdad.

```
let vegetal = "aji rojo"
switch vegetal {
case "apio":
	print("Añade unas pasas y prepara un bocado")
case "pepino", "berro":
	print("Eso haria un buen sandwich")
case let x where x.hasPrefix("aji")
	print("Es un \(x) picante")
default:
	print("Todo sabe bien en sopa.")
}
```

#### Experimento
Intenta remover el caso predeterminado (```default:```). Que error recibes?

Nota como ```let``` puede ser usado en un patron para asignar el valor que parejo esa parte del patron a un constante.

Despues de ejecutar el codigo dentro del caso que emparejo, el programa sale (*exits*) del sentencia de interrupcion. Ejecuccion no continua al siguiente caso, entonces no hay necesidad del explicitamente cesar (*break*) el interruptor que esta al final del codigo de cada caso.

Puedes usar ```for```-```in``` para iterar sobre elementos en un diccionario proveyendo una pareja de nombres que se usara para cada pareja de llave-valor (*key-value*). Dictionarios son una collecion sin orden, entonces sus llaves y valores son iteradas en una orden arbitriaria.

```
let numerosInteresantes = [
    "Primo": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Cuadrado": [1, 4, 9, 16, 25],
]
var masGrande = 0
for (tipo, numeros) in numerosInteresantes {
    for numero in numeros {
        if numero > masGrande {
            masGrande = numero
        }
    }
}
print(masGrande)”
```

#### Experimento
Anade otra variable para registar que tipo de numero era el mas grande, asi tambien como que era ese numero grande.

Usa ```while``` para repetir un bloque de codigo hasta que una condicion cambie. La condicion de una vuelta puede ser al final tambien, asegurando que la vuelta se ejecute una vez a lo minimo.

```
var n = 2
while n < 100 {
    n = n * 2
}
print(n)
 
var m = 2
repeat {
    m = m * 2
} while m < 100
print(m)
```

Puedes guardar una indice en una vuelta, usando ```..<``` para hacer un rango de indices, o mediante initializacion explicita, condicion, e incremento. Estas dos vueltas hacen lo mismo:

```
var primerCiclo = 0
for i in 0..<4 {
    primerCiclo += i
}
print(primerCiclo)
 
var segundoCiclo = 0
for var i = 0; i < 4; ++i {
    segundoCiclo += i
}
print(segundoCiclo)
```

### [Funciones](https://es.wikipedia.org/wiki/Subrutina) y [Clausuras](https://es.wikipedia.org/wiki/Clausura_(informática))

Usa ```func``` para declarar una funcion. Llama una funcion anexando una lista de argumentos en parentesis a la nombre de la funcion. Usa ```->``` para separar los nombres de los parametros y tipos del tipo de valor de retorno de la funcion.

```
func saludar(nombre: String, dia: String) -> String {
	return "Hola \(nombre), hoy es \(dia)."
}

saludar("Bob", dia: "Martes")
```

#### Experimento
Remueve el parametro ```dia```. Anade un parametro que incluya el almuerzo de hoy (menu del dia) en el saludo.

Usa una [tupla](https://es.wikipedia.org/wiki/Tupla) (*tuple*) para hacer un valor compuesta: por ejemplo, para retornar multiples valores de una funcion. Los elementos de una tupla se pueden referir por nombre o numero.

```
func calcularEstadisticas(puntajes: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0
    
    for puntaje in puntajes {
        if puntaje > max {
            max = puntaje
        } else if puntaje < min {
            min = puntaje
        }
        sum += puntaje
    }
    
    return (min, max, sum)
}
let estadisticas = calcularEstadisticas([5, 3, 100, 3, 9])
print(estadisticas.sum)
print(estadisticas.2)
```

Funciones tambien pueden tomar una cantidad variada de argumentos, collecionandolos en un arreglo.

```
func suma(numeros: Int...) -> Int {
	var suma = 0
	for numero in numeros {
		suma += numero
	}
	return suma
}
suma()
suma(42, 597, 12)
```

#### Experimento
Escribe una funcion que calcula el numero promedio de argumentos.








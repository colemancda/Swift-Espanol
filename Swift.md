# Bienvenidos a Swift

## Sobre Swift

[Swift](Glosario.md#swift) es una nueva lenguaje de programmacion para applicaciones de iOS, OS X, watchOS, y tvOS que estan cimentados en lo mejor de [C](Glosario.md#c) y [Objective-C](Glosario.md#objective-c), sin las restricciones de compatibilidad con C. Swift adopta patrones de programmacion seguros y añade caracterisitacas modernas para hacer programacion mas facil, mas flexible, y mas divertido. La implementacion nueva y limpia de Swift, apoyado por los [marcos de trabajo](Glosario.md#marco-de-trabajo) de [Cocoa](Glosario.md#cocoa) y [Cocoa Touch](Glosario.md#cocoa-touch), es una oportunidad para reimaginar como funciona el desarollo de [software](Glosario.md#software).

El proceso de la creacion de Swift ha estado ocurriendo por varios años. [Apple](Glosario.md#apple) creo el cimiento para Swift cuando avanzamos nuestra infraestructura de compilador, debuggeador y marcos de trabajo. Hemos simplificado manejo de memoria con [Conteo de Referencia Automatica](Glosario.md#conteo-de-referencia-automatica). Nuestras marcos de trabajo, construidas sobre la base solida de [Foundation](Glosario.md#foundation) y Cocoa, ha sido modernizada y estandarizado. Objective-C mismo ha evolucionado para soportar [clausuras](Glosario.md#clausura), colleciones literales, y modulos, habilitando que marcos de trabajo adopten technologias de lenguajes modernas sin obstaculos. Gracias a este trabajo, podemos introducir una nueva lengauaje de desarollo para el futuro de desarollo de Software para las plataformas de Apple.

Swift se siente familiar para desarolladores de Objective-C. Adopta la legibilidad de parametros nombrados y el poder del modelo de objectos dynamicos de Objective-C. Proveee acceso sin interrupciones a marcos de trabajo existentes de Cocoa y completa interoperabilidad con codigo Objective-C. Construyendo encima de esta fundacion, Swift introduce muchos nuevos conceptos y unifica las porciones [procedurales](Glosario.md#procedural) y [orientados a objectos](Glosario.md#orientado-a-objetos) del lenguaje.

Swift es amigable para nuevos programmadores. Es el primer lenguaje de programmacion de sistemas de calidad industrial que es tan expresivo y agradable como un lenguaje [interpretado](Glosario.md#intérprete). Soporta [parque de juegos](Glosario.md#parque-de-juegos), una caracteristica innovadora que permite programmadores experimentar con codigo Swift y ver los resultados immediatamente, sin el gasto de compilar y correr la applicacion.

Swift combina lo mejor en filosofias de lenguajes modernas con sabidura de la amplia cultura de ingeneria Apple. El compilador esta optimizado para rendimiento, y el lenguaje esta optimizada para desarollo, sin compromiso de ninguna de las dos partes. Esta diseñado para escalar de la implementacion de "```hola mundo```" a un sistema operativo entero. Todo esto hace que Swift sea una inversion segura para desarrolladores y Apple.

Swift es una manera fantastica para escribir applicaciones iOS, OS X, watchOS, y tvOS, y continuara evolucionandose con nuevas caracterisitcas y capabilidades. Nuestras metas para Swift son ambiciosas. No podemos esperar para ver que podras crear con ello.

## Una Guia de Swift

Tradicion sugiere que el primer programa en una nueva lenguaje de desarollo deberia imprimir las palabras "Hola, mundo!" en la pantalla. En Swift, esto se puede hacer con una sola linea de codigo:

```
print("Hola, mundo!")
```

Si has escrito codigo en C or Objective-C, este sintaxsis deberia de verse familiar para usted. En Swift, esta linea de codigo is un programa completo. No necesitas importar una marco de trabajo separada para funcionalidad como entrada y salida (*input/output*, *IO*) o manejo de texto (*string*). Codigo escrito a nivel (or contexto) (*scope*) global es usado como un punto de entrada para la aplicacion, entonces no necesitas una funcion ```main()```. Tampoco necesitas escribir semicolones al final de cada sentencia.

Esta guia te da suficiente informacion para empezar a escribir codigo en Swift mediante mostrandote como implementar una variedad de tareas de programmacion. No te preocupes si no entendiste algo, todo introducido en este libro esta explicado en detalle en el resto del libro.

### Valores Simples

Se usa ```let``` para crear una constante y ```var``` para crear una variable. El valor de un constante no necesita saberse a la hora de compilar, pero deberias asignarle un valor exactamente una vez. Esto significa que puedes usar constantes para nombrar un valor que se determina una vez, pero se usa en muchos lugares.

```
var miVariable = 42
miVariable = 50
let miConstante = 42
```
Una constante o variable deberia de tener el mismo tipo de valor que le quieras asignar. Sin embargo, no deberias de siempre tener que escribir el tipo explicitamente. Proveer un valor cuando creas la constante o variable, permite que el compilador dedusca su tipo. En el ejemplo de arriba, el compilador deduce que ```myVariable``` es un numero entero (*integer*) por que su valor inicial es un numero entero.

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

### [Control de Flujo](https://es.wikipedia.org/wiki/Estructuras_de_control)
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

En una sentencia de ```if```, el condicional deberia ser una expresion [Booleana ](https://es.wikipedia.org/wiki/Tipo_de_dato_lógico) (*Boolean*, *Bool*), lo cual significa que codigo como ```if score { ... }``` es un error, no una comparacion implicita a cero. Puedes usar ```if``` y ```let``` juntos para trabajar con valores que podrian estar faltantes. Estos valores se representa como opcionales (*optionals*). Un valor opcional contiene un valor o ```nil``` (nulo) para representar que un valor esta faltando. Escribe un signo de interrogacion (```?```) despues del tipo de valor para marcar el valor como opcional.

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

Usa ```while``` para repetir un bloque de codigo hasta que una condicion cambie. La condicion de un ciclo puede ser al final tambien, asegurando que la ciclo se ejecute una vez a lo minimo.

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

Puedes guardar una indice en una ciclo, usando ```..<``` para hacer un rango de indices, o mediante initializacion explicita, condicion, e incremento. Estas dos ciclos hacen lo mismo:

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
Escribe una funcion que calcula el valor promedio de sus argumentos.

Funciones pueden ser anidados. Funciones anidados tienen accesso a variables que fueron declaradas en la funcion exterior. Puedes usar funciones anidados para organizar el codigo en una funcion que es larga o compleja.

```
func retornarQuince() -> {
	var y = 10
	func añadir() {
		y += 5
	}
	añadir()
	return y
}
retornarQuince()
```

Funciones son un tipo de primera clase. Esto significa que una funcion puede returnar otra funcion como su valor.

```
func crearIncrementador() -> ((Int) -> (Int)) {
	func añadeUno(numero: Int) -> Int {
		return 1 + numero
	}
	return añadeUno
}
var incrementa = crearIncrementador()
incrementa(7)
```

Una funcion puede tomar otra funcion como uno de sus argumentos.

```
func tieneAlgunPareja(lista: [Int], condicion: (Int -> Bool)) -> Bool {
	for elemento in lista {
		if condicion(elemento) {
			return true
		}
	}
	return false
}

func menosQueDiez(numero: Int) -> Bool {
	return numero < 10
}
var numeros = [20, 19, 7, 12]
tieneAlgunPareja(numeros, condicion: menosQueDiez)
```

Funciones en verdad son un case especial de clausuras: bloques de codigo que pueden ser llamados despues. El codigo en una clausura tiene accesso a cosas como variables y funciones que estaban disponibles en el contexto donde fue creado, aun si la clausura esta ejecutandose en otro contexto: ya viste un ejemplo de esto con funciones anidadas. Puedes escribir una clausura sin nombre via encerrando codigo con llaves (```{}```). Usa ```in``` para separar los argumentos y tipo de valor retornado del cuerpo de la funcion.

```
numeros.map({ (numero: Int) -> Int in
	let resultado = 3 * numero
	return resultado
})
```

#### Experimento
Vuelve a escribir la clausura para que retorne cero para todo numero impar.

Tienes varias opciones para escribir clausuras mas concisamente. Cuando ya se sabe el tipo de clausura, asi como una [retrollamada](https://es.wikipedia.org/wiki/Callback_(informática)) (*callback*) para un [delegado](https://es.wikipedia.org/wiki/Delegación_(informática)) (*delegate*), puedes omitir el tipo de los parametros, valor de retorno o ambos. Clausuras de una sola sentencia implicitamente retornan el value de su unica sentencia.

```
let numerosMapeados = numeros.map({ numero in 3 * numero })
print(numerosMapeados)
```

Puedes referir a parametros por numero envez de su nombre, esta estrategia es especialmente usable en clausuras cortos. Una clausuras pasado como un ultimo argumento puede aparecer immediatamente despues de los parentesis. Cuando una clausura es el unico argumento a una funcion, puedes omitir los parentesis completamente.

```
let numerosOrdenados = numeros.sort { 0$ > $1 }
print(numerosOrdenados)
```

### [Objetos](https://es.wikipedia.org/wiki/Programación_orientada_a_objetos) y [Clases](https://es.wikipedia.org/wiki/Clase_(informática))

Usa ```class``` seguido del nombre de la clase para crear una clase. Una declaracion de una propiedad en una clase es escrita de la misma manera que la declaracion de una constante o variable, con la excepcion de que esta en el contexto de la clase. Declaraciones de metodos y funciones estan escritas de la misma manera.

```
class Figura {
	var numeroDeLados = 0
	func descripcionSimple() -> String {
		return "Una figura con \(numeroDeLados) lados."
	}
}
```

#### Experimento
Anade una propiedad constante con ```let```, y anade otra propiedad que toma un argumento.

Crea una instancia de una clase poniendo parentesis despues del nombre de la clase. Usa puntos (```.```) para accedar los propiedades y metodos de la instancia.

```
var figura = Figura()
figura.numeroDeLados = 7
var descripcionDeFigura = figura.descripcionSimple()
```

A esta version de la clase ```Figura``` le esta faltando algo importante: un initilizador para configurar la clase cuando una instancia se crea. Usa ```init``` para crear uno.

```
class FiguraNombrado {
	var numeroDeLados: Int = 0
	var nombre: String
	
	init(nombre: String) {
		self.nombre = nombre
	}
	
	func descripcionSimple() -> String {
		return "Una figura con \(numeroDeLados) lados."
	}
}
```

Nota como ```self``` es usado para distinguir la propiedad ```nombre``` del argumento al initializador tambien llamado ```nombre```. Los argumentos al initializador son pasados como una llamada de funcion cuando creas una instancia de la clase. Toda propiedad necesita un valor asignado, sea en su declaracion (como con ```numeroDeLados```) o en el initializador (como con ```nombre```).

Usa ```deinit``` para crear el deinitializador si necesitas hacer operaciones de limpieza cuando el objeto es deallocado.

Subclases incluyen el nombre superclase despues del nombre de su clase, separado por un colon. No hay requerimiento para que clases sean el subclase de alguna clase principal, entonces puede incluir o omitir una superclase segun tus necesidades.

Metodos en una subclase que redefinen la implementacion de la superclase estan marcados con ```override```. Redefinir un metodo por accidente, sin marcar ```override```, es detectado por el compilador como un error. El compilador tambien detecta metodos con ```override``` que en verdad no redefinen ningun metodo en su superclase.

```
class Cuadrado: FiguraNombrado {
    var anchoDeLado: Double
    
    init(anchoDeLado: Double, nombre: String) {
        self.anchoDeLado = anchoDeLado
        super.init(nombre: nombre)
        numeroDeLados = 4
    }
    
    func area() ->  Double {
        return anchoDeLado * anchoDeLado
    }
    
    override func descripcionSimple() -> String {
        return "Un cuadrado con \(anchoDeLado) ancho de lados."
    }
}
let prueba = Cuadrado(anchoDeLado: 5.2, nombre: "mi cuadrado de prueba")
prueba.area()
prueba.descripcionSimple()
```

#### Experimento
Haz otra subclase de ```FiguraNombrado``` llamado ```Circulo``` que toma una radio y un nombre como argumentos a su initializador. Implementa los metodos ```area()``` y ```descripcionSimple()``` en la clase ```Circulo```.

Ademas de propiedades simples que son guardados, propiedades pueden tener un accesor (*getter*) y fijador (*setter*).

```
class TrianguloEquilateral: FiguraNombrado {
	var anchoDeLado: Double = 0.0
	
	init(anchoDeLado: Double, nombre: String) {
        self.anchoDeLado = anchoDeLado
        super.init(nombre: nombre)
        numeroDeLados = 4
    }
    
    var perimetro: Double {
    	get {
    		return 3.0 * anchoDeLado
    	}
    	set {
    		anchoDeLado = newValue / 3.0
    	}
    }
    
    override func descripcionSimple() -> String {
    	return "Un triangulo equilateral con \(anchoDeLado) ancho de lados."
    }
}
var triangle = TrianguloEquilateral(anchoDeLado: 3.1, nombre: "un triangulo")
print(triangulo.perimetro)
triangulo.perimetro = 9.9
print(triangulo. anchoDeLado)
```

En el fijador para ```perimetro```, el nuevo valor tiene el nombre implicita de ```newValue```. Puedes proveer un nombre explicita en los parentesis despues de ```set```.


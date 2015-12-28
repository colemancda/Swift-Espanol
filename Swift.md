# Bienvenidos a Swift

## Sobre Swift

*Swift* es una nueva lenguaje de programmacion para applicaciones de iOS, OS X, watchOS, y tvOS que estan cimentados en lo mejor de *C* y *Objective-C*, sin las restricciones de compatibilidad con C. Swift adopta patrones de programmacion seguros y añade caracterisitacas modernas para hacer programacion mas facil, mas flexible, y mas divertido. La implementacion nueva y limpia de Swift, apoyado por las librerias maduras de *Cocoa* y *Cocoa Touch*, es una oportunidad para reimaginar como funciona el desarollo de Software.

El proceso de la creacion de Swift ha estado ocurriendo por varios años. Apple creo el cimiento para Swift cuando avanzamos nuestra infraestructura de compilador, debuggeador y librerias. Hemos simplificado manejo de memoria con Contador de Referencia Automatico (*Automatic Memory Management* o *ARC*). Nuestras librerias, construidas sobre la base solida de *Foundation* y Cocoa, ha sido modernizada y estandarizado. Objective-C mismo ha evolucionado para soportar bloques, literales de colleciones, y modulos, habilitando que librerias adopten technologias de lenguajes modernas sin obstaculos. Gracias a este trabajo, podemos introducir una nueva lengauaje de desarollo para el futuro de desarollo de Software para las plataformas de Apple.

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

Crea arreglos (*array*) y *diccionarios* dictionaries usando brackets (```[]```) y accede sus elementos escribiendo el indice o (*key*) en brackets. Una comma se permite despues del primer elemento.

```
var miListaDeCompras = ["bagre", "agua", "tulipanes", "pintura azul"]
miListaDeCompras[1] = "botella de agua"

var profesiones = [
	"Malcolm": "Capitan",
	"Kaylee": "Mecanico"
]

profesiones["Jayne"] = "Relaciones Publicas"
```

Si la informacion de tipo puede ser deducida

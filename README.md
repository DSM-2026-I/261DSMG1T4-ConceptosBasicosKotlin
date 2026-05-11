# Práctica: Conceptos básicos de Kotlin
Alumno: Bryan Edgard Ochoa Trillo

## 1. Notificaciones móviles
En el código inicial que se proporciona en el siguiente fragmento de código, escribe un programa que imprima el mensaje de resumen según la cantidad de notificaciones que recibiste. El mensaje debe incluir lo siguiente:

- La cantidad exacta de notificaciones cuando haya menos de 100
- 99+ como cantidad de notificaciones cuando haya 100 o más

```kotlin
fun main() {
    val morningNotification = 51
    val eveningNotification = 135
    
    printNotificationSummary(morningNotification)
    printNotificationSummary(eveningNotification)
}

fun printNotificationSummary(numberOfMessages: Int) {
    // Fill in the code.
}
```
Completa la función printNotificationSummary() para que el programa imprima estas líneas:
```
You have 51 notifications.
Your phone is blowing up! You have 99+ notifications.
```
**Solución**: [https://pl.kotl.in/QUwSm-B9O](https://pl.kotl.in/QUwSm-B9O)

## 2. Precio de las entradas de cine
Las entradas de cine suelen tener un precio diferente según la edad de los espectadores.

En el código inicial que se proporciona en el siguiente fragmento de código, escribe un programa que calcule los precios de estas entradas basados en la edad:

- Un precio de entrada infantil de USD 15 para personas de 12 años o menos.
- Un precio de entrada estándar de USD 30 para personas de entre 13 y 60 años. Los lunes, un precio estándar con descuento de USD 25 para el mismo grupo etario
- Un precio para adultos mayores de USD 20 para personas de 61 años o más (asumimos que la edad máxima de un espectador es de 100 años)
- Un valor de -1 para indicar que el precio no es válido cuando un usuario ingresa una edad fuera de las especificaciones

``` kotlin
fun main() {
    val child = 5
    val adult = 28
    val senior = 87
    val isMonday = true
    
    println("The movie ticket price for a person aged $child is \$${ticketPrice(child, isMonday)}.")
    println("The movie ticket price for a person aged $adult is \$${ticketPrice(adult, isMonday)}.")
    println("The movie ticket price for a person aged $senior is \$${ticketPrice(senior, isMonday)}.")
}

fun ticketPrice(age: Int, isMonday: Boolean): Int {
    // Fill in the code.
}
```
Completa la función ticketPrice() para que el programa imprima estas líneas:
```
The movie ticket price for a person aged 5 is $15.
The movie ticket price for a person aged 28 is $25.
The movie ticket price for a person aged 87 is $20.
```
**Solución**: [https://pl.kotl.in/Zmv8EBvlf](https://pl.kotl.in/Zmv8EBvlf)

## 3. Conversor de temperatura
En el mundo, se usan tres escalas de temperatura principales: Celsius, Fahrenheit y Kelvin.

En el código inicial que se proporciona en el siguiente fragmento de código, escribe un programa que convierta una temperatura de una escala a otra con estas fórmulas:

- De grados Celsius a Fahrenheit: °F = 9/5 (°C) + 32
- Kelvin a Celsius: °C = K - 273.15
- De Fahrenheit a Kelvin: K = 5/9 (°F - 32) + 273.15

Ten en cuenta que el método String.format("%.2f", /* measurement */ ) se usa para convertir un número en un tipo String con 2 decimales.
``` kotlin
fun main() {
    // Fill in the code.
}

fun printFinalTemperature(
    initialMeasurement: Double, 
    initialUnit: String, 
    finalUnit: String, 
    conversionFormula: (Double) -> Double
) {
    val finalMeasurement = String.format("%.2f", conversionFormula(initialMeasurement)) // two decimal places
    println("$initialMeasurement degrees $initialUnit is $finalMeasurement degrees $finalUnit.")
}
```
Completa la función main() para que llame a la función printFinalTemperature() e imprima las siguientes líneas. Debes pasar argumentos para la fórmula de conversión y temperatura. Sugerencia: Te recomendamos usar valores Double para evitar el truncamiento de Integer durante las operaciones de división.
```
27.0 degrees Celsius is 80.60 degrees Fahrenheit.
350.0 degrees Kelvin is 76.85 degrees Celsius.
10.0 degrees Fahrenheit is 260.93 degrees Kelvin.
```
**Solución**: [https://pl.kotl.in/Bmo8rr2iO](https://pl.kotl.in/Bmo8rr2iO)

## 4. Catálogo de canciones
Imagina que necesitas crear una app de reproducción de música.

Crea una clase que pueda representar la estructura de una canción. La clase Song debe incluir estos elementos de código:

Propiedades para el título, el artista, el año de publicación y el recuento de reproducciones
Propiedad que indica si la canción es popular (si el recuento de reproducciones es inferior a 1,000, considera que es poco popular)
Un método para imprimir la descripción de una canción en este formato:
"[Título], interpretada por [artista], se lanzó en [año de lanzamiento]".

**Solución**: [https://pl.kotl.in/yGNEAkCAD](https://pl.kotl.in/yGNEAkCAD)

## 5. Perfil de Internet
A menudo, debes completar los perfiles de sitios web en línea que contienen campos obligatorios y no obligatorios. Por ejemplo, puedes agregar tu información personal y un vínculo a otras personas que te refirieron para que registraras tu perfil.

En el código inicial que se proporciona en el siguiente fragmento de código, escribe un programa que imprima los detalles del perfil de una persona.

``` kotlin
fun main() {    
    val amanda = Person("Amanda", 33, "play tennis", null)
    val atiqah = Person("Atiqah", 28, "climb", amanda)
    
    amanda.showProfile()
    atiqah.showProfile()
}


class Person(val name: String, val age: Int, val hobby: String?, val referrer: Person?) {
    fun showProfile() {
       // Fill in code 
    }
}
```
Completa la función showProfile() para que el programa imprima estas líneas:
```
Name: Amanda
Age: 33
Likes to play tennis. Doesn't have a referrer.

Name: Atiqah
Age: 28
Likes to climb. Has a referrer named Amanda, who likes to play tennis.
```

**Solución**: [https://pl.kotl.in/EQMsi2IS9](https://pl.kotl.in/EQMsi2IS9)

## 6. Teléfonos plegables
Por lo general, la pantalla del teléfono se enciende y se apaga cuando se presiona el botón de encendido. En cambio, si un teléfono plegable está plegado, su pantalla interna principal no se enciende cuando se presiona el botón de encendido.

En el código inicial que se proporciona en el siguiente fragmento de código, escribe una clase FoldablePhone que se herede de la clase Phone. Debe contener lo siguiente:

- Una propiedad que indique si el teléfono está plegado
- Un comportamiento de función switchOn() diferente del de la clase Phone para que solo encienda la pantalla cuando el teléfono no esté plegado
- Métodos para cambiar el estado de plegado

``` kotlin
class Phone(var isScreenLightOn: Boolean = false){
    fun switchOn() {
        isScreenLightOn = true
    }
    
    fun switchOff() {
        isScreenLightOn = false
    }
    
    fun checkPhoneScreenLight() {
        val phoneScreenLight = if (isScreenLightOn) "on" else "off"
        println("The phone screen's light is $phoneScreenLight.")
    }
}
```

**Solución**: [https://pl.kotl.in/_jeQb3-yI](https://pl.kotl.in/_jeQb3-yI)

## 7. Subasta especial
Por lo general, en una subasta, el ofertante que ofrece el importe más alto determina el precio de un artículo. En esta subasta especial, si nadie oferta por un artículo, este se vende automáticamente a la casa de subastas al precio mínimo.

En el código inicial que se proporciona en el siguiente fragmento de código, se te proporciona una función auctionPrice() que acepta un tipo Bid? anulable como argumento:

```kotlin
fun main() {
    val winningBid = Bid(5000, "Private Collector")
    
    println("Item A is sold at ${auctionPrice(winningBid, 2000)}.")
    println("Item B is sold at ${auctionPrice(null, 3000)}.")
}

class Bid(val amount: Int, val bidder: String)
 
fun auctionPrice(bid: Bid?, minimumPrice: Int): Int {
   // Fill in the code.
}
```
Completa la función auctionPrice() para que el programa imprima estas líneas:
```
Item A is sold at 5000.
Item B is sold at 3000.
```
**Solución**: [https://pl.kotl.in/qEQESa_Dc](https://pl.kotl.in/qEQESa_Dc)
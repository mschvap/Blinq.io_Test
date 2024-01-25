# Primeros pasos con Blinq.IO

Este documento fue creado como guía para la implementación de la herramienta Blinq.IO.

Blinq.IO es una herramienta que permite utilizar inteligencia artificial para crear casos de pruebas automatizado en Playwright

Para más información ingresar a la página de Blinq.IO: [https://blinq.io/](https://blinq.io/))

Para consultar ejemplos ingresar a la página de youtube: [https://www.youtube.com/@blinqio](https://www.youtube.com/@blinqio)

> **PRE-REQUISITOS**:

> * Para ejecutar el proyecto se recomienda mínimo las siguientes versiones:

>  * Visual Studio Code (actualizado)
>  * Node JS (actualizado)
>  * Extension de VSCode: Blinq.IO
>  * Extension de Chrome: Selenium Session Connector
>  * Cuenta en la página de Blinq.IO

## Funcionalidades incluidas en el framework

> **Soporta automatización**:
> * Web

## Creación del proyecto

Ejecutar el comando `Contorl + Shift + P` y Seleccionar `BVT: Setup project`

Una vez descargadas todas las librerías y ficheros quedara la siguiente estructura armada:

```Gherkin
+ features
+ node_modules
package-lock.json
package.json
```

a continuación, dentro del fichero `features` creamos nuestro feature en Gherkin de tal forma que la estructura queda de la siguiente forma:

```Gherkin
+ features
    reserva.feature                         Caso de prueba creado
+ node_modules
package-lock.json
package.json
```

en donde el archivo `reserva.feature` debe tener el caso de prueba escrito en Gherkin:

```Gherkin
Feature: Realizar reserva de vuelo

    Scenario: Con origen y destino
    Given ingreso origen "Boston" y destino "Berlin"
    When continuo con la reservea de vuelo
    Then verifico que la pagina contenga el mensaje "Thank you for your purchase today!"
```

el siguiente paso es crear el archivo `env.json` con el código extraido de `Selenium Session Connector` en Chrome:

```Gherkin
+ features
    reserva.feature
+ node_modules
env.json                                    Se copia el código obtenido y se pega aquí
package-lock.json
package.json
```

> **NOTA**:

> * No olvidar guardar los cambios cada vez que se realizan modificaciones (por defecto VSCode no guarda automáticamente lo que hacemos)
> * Para guardar los cambios se puede hacer facilmente con el comando `Control + S`

por último ejecutamos el comando `Control + Shift + P` y Seleccionar `BVT: Generate Step Definitions`. Seleccionamos todos los Steps y presionamos el botón `OK`

## Pros y Contras

> **PROS**:
>  * Se puede ahorrar mucho tiempo escribiendo los test
>  * No se necesitan muchos conocimientos de JavaScript o Playwright (Para crear los test)
>  * Se desarrolla utilizando leguaje natural

> **CONTRAS**:
>  * Algunos componentes fallan o se reconocen de forma incorrecta (Por ejemplo, searchBox de Mercado libre)
>  * Páginas con mucho contenido dan errores de timeout debido a la cantidad de información que se está procesando en el análisis
>  * La herramienta está en una etapa muy temprana, lo cual puede presentar errores o no estar disponible


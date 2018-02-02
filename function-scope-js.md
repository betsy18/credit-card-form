# Identificando Funciones

Identificar las funciones globales, locales, funciones de callback, expresions, statement, clousure, scope, contextos de ejecucion, que funciones forman parte de la pila de ejecucion (stack execution) y que funciones forman parte de la cola de eventos (event queue).

## Funciones globales

Funciones que no forman parte de otra función y se crean como propiedad del objeto windows.

```js
// funcion global y dentro de esta hay una función anónima
$(document).ready(function(){}
```

## Funciones locales

Funciones que estan dentro de una función global.

```js
 function activeButton();
 function desactiveButton();
 function textLength(input);
 function onlyNumbers(input);
 function isValidCreditCard(numberCard);
 $inputCard.on('input', function(){});
```

## Funciones callback

Función dentro de otra función como parámetro, no solo funciona con los eventos.

```js
$inputCard.on('input', function() {});
function isValidCreditCard(numberCard) {
 creditCardNumber = onlyNumbers(textLength(numberCard))}
```

## Funciones expresions

Son funciones declaradas a partir de variables.

```js
var creditCardNumber = onlyNumbers(textLength(numberCard));
```

## Funciones statement

Funciones disponibles al 100% del ambiente lexical, se declaran con la palabra reservada `function`, seguido de un nombre.

```js
 function activeButton();
 function desactiveButton();
 function textLength(input);
 function onlyNumbers(input);
 function isValidCreditCard(numberCard);
```

## Funciones clousure

Memoria que tienen las funciones para recordar su contexto exterior, lo que le rodea.


+ function activeButton(); Recuerda su contexto global porque utiliza una variable que ha sido declarada anteriormente.
+ function desactiveButton(); Recuerda su contexto global porque utiliza una variable que ha sido declarada anteriormente.
+ function isValidCreditCard(numberCard); Recuerda su contexto global y local, ya que hace referencia a funciones declaradas anteriormente.


## Contextos de Ejecución

Código ejecutandose en el motor de Js, se crea el Global Object.

## Stack execution

Es como se ordena el código al momento de ejecutarlo.

+ Global Object
+ $(document).ready(function(){};
+ console.log('Probar con el numero valido 4544164785372342');
+ function onlyNumbers(input);
+ function textLength(input);
+ function isValidCreditCard(numberCard)
+ $inputCard.on('input', function();
+ function activeButton();
+ function desactiveButton()

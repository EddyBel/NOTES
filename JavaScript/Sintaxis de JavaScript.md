---
Completado: Yes
Dificultad: ⭐
Etiquetas: Bases, Conceptos, JavaScript, Sintaxis
Fecha: February 18, 2023
---

# Sintaxis de JavaScript

## **Variables y Constantes**

Las variables son nombres simbólicos que se usan para almacenar valores en un programa. JavaScript utiliza la palabra clave **`var`** para declarar variables. Las constantes, por otro lado, son variables cuyo valor no cambia a lo largo del programa. JavaScript utiliza la palabra clave **`const`** para declarar constantes.

```jsx
// Declaración de variables
var x = 5;
var y = "Hola, mundo!";

// Declaración de constantes
const PI = 3.14159;
```

## **Funciones**

Las funciones son bloques de código que se pueden llamar desde otras partes del programa. En JavaScript, se puede definir una función utilizando la palabra clave **`function`**. Las funciones pueden recibir parámetros y pueden devolver valores.

```jsx
// Definición de una función que suma dos números
function sumar(a, b) {
  return a + b;
}

// Llamado a la función sumar
var resultado = sumar(2, 3);
console.log(resultado); // Muestra 5 en la consola
```

## **Condicionales**

[La sentencia `if-else` es una estructura de control de flujo que permite ejecutar un bloque de código si se cumple una condición y otro bloque de código si no se cumple la condición](https://www.freecodecamp.org/espanol/news/javascript-if-else-y-if-then-sentencias-condicionales-en-js/). La sintaxis es la siguiente:

```jsx
if (condición) {
  // código a ejecutar si la condición es verdadera
} else {
  // código a ejecutar si la condición es falsa
}
```

La sentencia `else if` es una extensión de la sentencia `if-else` que permite evaluar múltiples condiciones. La sintaxis es la siguiente:

```jsx
if (condición1) {
  // código a ejecutar si la condición1 es verdadera
} else if (condición2) {
  // código a ejecutar si la condición2 es verdadera
} else {
  // código a ejecutar si ninguna de las condiciones anteriores es verdadera
}
```

La sentencia `switch` es otra estructura de control de flujo que permite evaluar una expresión y ejecutar diferentes bloques de código según el valor de la expresión. La sintaxis es la siguiente:

```jsx
switch (expresión) {
  case valor1:
    // código a ejecutar si expresión es igual a valor1
    break;
  case valor2:
    // código a ejecutar si expresión es igual a valor2
    break;
  default:
  // código a ejecutar si expresión no coincide con ninguno de los valores anteriores
}
```

Aquí te muestro un ejemplo para cada una de las sentencias:

```jsx
// Ejemplo con if-else
let edad = 18;

if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad");
}

// Ejemplo con else if
let hora = new Date().getHours();

if (hora < 12) {
  console.log("Buenos días");
} else if (hora < 18) {
  console.log("Buenas tardes");
} else {
  console.log("Buenas noches");
}

// Ejemplo con switch
let dia = new Date().getDay();

switch (dia) {
  case 0:
    console.log("Hoy es domingo");
    break;
  case 1:
    console.log("Hoy es lunes");
    break;
  case 2:
    console.log("Hoy es martes");
    break;
  case 3:
    console.log("Hoy es miércoles");
    break;
  case 4:
    console.log("Hoy es jueves");
    break;
  case 5:
    console.log("Hoy es viernes");
    break;
  case 6:
    console.log("Hoy es sábado");
}
```

## **Bucles**

[El bucle `while` es una estructura de control de flujo que permite ejecutar un bloque de código mientras se cumpla una condición](https://bing.com/search?q=bucles+while+for+y+do-while+javascript). La sintaxis es la siguiente:

```jsx
while (condición) {
  // código a ejecutar mientras la condición sea verdadera
}
```

[El bucle `for` es otra estructura de control de flujo que permite ejecutar un bloque de código un número determinado de veces](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Loops_and_iteration). La sintaxis es la siguiente:

```jsx
for (inicialización; condición; actualización) {
  // código a ejecutar mientras la condición sea verdadera
}
```

[El bucle `do-while` es similar al bucle `while`, pero se ejecuta al menos una vez antes de comprobar la condición](https://es.stackoverflow.com/questions/217466/cuando-se-cuando-tengo-que-usar-un-while-o-un-do-while). La sintaxis es la siguiente:

```jsx
do {
  // código a ejecutar al menos una vez
} while (condición);
```

Aquí te muestro un ejemplo para cada uno de los bucles:

```jsx
// Ejemplo con while
let i = 0;

while (i < 5) {
  console.log(i);
  i++;
}

// Ejemplo con for
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// Ejemplo con do-while
let j = 0;

do {
  console.log(j);
  j++;
} while (j < 5);
```

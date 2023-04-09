---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: C, Conceptos, Programación, Sintaxis
Fecha: February 17, 2023
---

# Sintaxis de C

## Declaración de variables

La declaración de variables en C es una parte fundamental del lenguaje y es importante conocer las buenas prácticas para escribir código legible y fácil de mantener.

La forma estándar para declarar una variable es colocar su tipo antes del nombre de la variable de la siguiente forma:

```c
int entero;
char letra;
```

También es posible declarar dos o más variables del mismo tipo en la misma declaración:

```c
int entero1, entero2;
```

Es una buena práctica inicializar las variables al momento de declararlas para evitar errores y comportamientos inesperados:

```c
int entero = 0;
char letra = 'a';
```

También es posible declarar constantes en C utilizando la palabra clave **`const`**:

```c
const int ENTERO_CONSTANTE = 10;
```

## Tipos de datos

En C existen varios tipos de datos que se pueden utilizar para declarar variables como:

- **char**: Este tipo de dato se utiliza para almacenar caracteres individuales como letras o números. Un char ocupa un byte de memoria.
  ```c
  char letra = 'a';
  ```
- **int**: Este tipo de dato se utiliza para almacenar números enteros. Un int puede ocupar 2 o 4 bytes de memoria dependiendo del compilador y la plataforma.
  ```c
  int numero = 10;
  ```
- **float**: Este tipo de dato se utiliza para almacenar números decimales con una precisión simple. Un float ocupa 4 bytes de memoria.
  ```c
  float decimal = 3.14;
  ```
- **double**: Este tipo de dato se utiliza para almacenar números decimales con una precisión doble. Un double ocupa 8 bytes de memoria.
  ```c
  double decimal_preciso = 3.14159265359;
  ```
- **void**: Este tipo de dato se utiliza para indicar la ausencia de tipo. Por ejemplo, una función que no devuelve ningún valor tiene un tipo void.
  ```c
  void funcion() {
      printf("Esta función no devuelve ningún valor.\n");
  }
  ```

Además, C también cuenta con tipos de datos más complejos como arreglos, estructuras y punteros.

- **Punteros**: Un puntero es una variable que almacena la dirección de memoria de otra variable. Los punteros se utilizan para acceder y manipular datos en memoria de manera eficiente. A continuación te proporciono un ejemplo de código para declarar un puntero y asignarle la dirección de memoria de una variable:
  ```c
  int numero = 10;
  int *puntero = &numero;
  ```
- **Arreglos**: Un arreglo es una colección de variables del mismo tipo que se almacenan en memoria contigua. Los arreglos se utilizan para almacenar y manipular datos relacionados de manera eficiente. A continuación te proporciono un ejemplo de código para declarar un arreglo y acceder a sus elementos:
  ```c
  int numeros[3] = {1, 2, 3};
  printf("%d\n", numeros[0]); // Imprime 1
  printf("%d\n", numeros[1]); // Imprime 2
  printf("%d\n", numeros[2]); // Imprime 3
  ```
- **Estructuras**: Una estructura es un tipo de dato que permite combinar varios tipos de datos relacionados en una sola entidad. Las estructuras se utilizan para representar objetos complejos de manera eficiente. A continuación te proporciono un ejemplo de código para declarar una estructura y acceder a sus miembros:
  ```c
  struct persona {
      char nombre[20];
      int edad;
  };

  struct persona p = {"Juan", 25};
  printf("%s\n", p.nombre); // Imprime "Juan"
  printf("%d\n", p.edad); // Imprime 25
  ```

## Strings

Para declarar una cadena de caracteres en C, se utiliza un arreglo de caracteres (char) y se asigna un tamaño al arreglo que sea suficiente para contener la cadena completa. Por ejemplo, si se desea declarar una cadena de caracteres llamada “nombre” que contenga el nombre “Juan”, se puede hacer de la siguiente manera:

```c
char nombre[5] = "Juan";

```

En este caso, se declara un arreglo de caracteres llamado “nombre” con un tamaño de 5 caracteres y se le asigna el valor “Juan”. El tamaño del arreglo debe ser igual al número de caracteres en la cadena más uno para el carácter nulo que indica el final de la cadena.

Si no conoces la longitud del string, puedes declarar un puntero a char y asignarle memoria dinámicamente utilizando la función malloc(). La función malloc() asigna la cantidad de memoria especificada en bytes y devuelve un puntero al primer byte de la memoria asignada. Por ejemplo:

```c
char *nombre;
nombre = (char*) malloc(10 * sizeof(char));

```

En este caso, se declara un puntero a char llamado “nombre” y se le asigna memoria para 10 caracteres utilizando la función malloc(). El tamaño de la memoria asignada es de 10 caracteres multiplicado por el tamaño de un char (1 byte). Después de utilizar la cadena, es importante liberar la memoria asignada utilizando la función free().

Un ejemplo de esto seria:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *nombre;
    nombre = (char*) malloc(10 * sizeof(char));
    printf("Ingresa tu nombre: ");
    scanf("%s", nombre);
    printf("Hola %s!\n", nombre);
    free(nombre);
    return 0;
}
```

En este ejemplo, se declara un puntero a char llamado “nombre” y se le asigna memoria para 10 caracteres utilizando la función malloc(). Después se utiliza la función scanf() para leer el valor del nombre ingresado por el usuario y se imprime un mensaje de saludo utilizando la función printf(). Finalmente, se libera la memoria asignada utilizando la función free().

## Declaración de funciones

Las funciones son bloques de código que realizan una tarea específica y se pueden llamar desde cualquier parte del programa. Las funciones se utilizan para dividir el código en partes más pequeñas y fáciles de mantener.

La declaración de una función consta de los siguientes elementos:

- **Tipo de retorno**: El tipo de dato que devuelve la función.
- **Nombre de la función:** El nombre que se le da a la función.
- **Parámetros**: Los valores que recibe la función para realizar su tarea.

A continuación te proporciono un ejemplo de código para declarar una función que suma dos números enteros:

```c
int suma(int a, int b) {
    return a + b;
}
```

En este ejemplo, la función se llama **`suma`**, devuelve un valor entero y recibe dos parámetros enteros llamados **`a`** y **`b`**. La función realiza la suma de los dos parámetros y devuelve el resultado.

Es una buena práctica declarar las funciones al principio del archivo para facilitar su lectura y comprensión:

```c
int suma(int a, int b);

int main() {
    int resultado = suma(1, 2);
    printf("%d\n", resultado); // Imprime 3
}

int suma(int a, int b) {
    return a + b;
}

```

También es posible utilizar funciones sin valor de retorno (void) para realizar tareas que no devuelven un valor:

```c
void imprimir_mensaje() {
    printf("Hola mundo!\n");
}
```

## Condicionales

En C existen las sentencias de control de flujo if-else y switch que permiten tomar decisiones en función del valor de una expresión o variable.

La sentencia if-else se utiliza para ejecutar un bloque de código si se cumple una condición y otro bloque de código si no se cumple la condición. La sintaxis es la siguiente:

```c
if (condición) {
  // código a ejecutar si la condición es verdadera
} else {
  // código a ejecutar si la condición es falsa
}
```

En caso de que se necesiten más condiciones se pueden utilizar los else if:

```c
if (condición1) {
  // código a ejecutar si la condición1 es verdadera
} else if (condición2) {
  // código a ejecutar si la condición2 es verdadera
} else {
  // código a ejecutar si ninguna de las condiciones anteriores es verdadera
}
```

Por otro lado, la sentencia switch se utiliza para seleccionar uno de varios bloques de código para ser ejecutado en función del valor de una expresión o variable. La sintaxis es la siguiente:

```c
switch (expresión) {
  case valor1:
    // código a ejecutar si la expresión es igual a valor1
    break;
  case valor2:
    // código a ejecutar si la expresión es igual a valor2
    break;
  ...
  default:
    // código a ejecutar si la expresión no coincide con ninguno de los valores anteriores
}
```

> Es importante tener en cuenta que el uso excesivo de sentencias switch puede hacer que el código sea difícil de leer y mantener, por lo que se recomienda utilizarlas con moderación.

## Bucles

Los bucles son estructuras de control que permiten repetir una sección de código varias veces. En C existen tres tipos de bucles: **`for`**, **`while`** y **`do-while`**.

El bucle **`for`** se utiliza para repetir una sección de código un número fijo de veces:

```c
for (inicialización; condición; incremento) {
    // Código a repetir
}
```

La inicialización se realiza antes de que comience el bucle y se utiliza para declarar e inicializar variables. La condición se evalúa antes de cada iteración del bucle y si es verdadera, el código dentro del bucle se ejecuta. El incremento se realiza después de cada iteración del bucle.

A continuación te proporciono un ejemplo de código para imprimir los números del 1 al 10 utilizando un bucle **`for`**:

```c
for (int i = 1; i <= 10; i++) {
    printf("%d\n", i);
}
```

El bucle **`while`** se utiliza para repetir una sección de código mientras una condición sea verdadera:

```c
while (condición) {
    // Código a repetir
}
```

La condición se evalúa antes de cada iteración del bucle y si es verdadera, el código dentro del bucle se ejecuta.

A continuación te proporciono un ejemplo de código para imprimir los números del 1 al 10 utilizando un bucle **`while`**:

```c
int i = 1;
while (i <= 10) {
    printf("%d\n", i);
    i++;
}
```

El bucle **`do-while`** es similar al bucle **`while`**, pero la condición se evalúa después de cada iteración del bucle:

```c
do {
    // Código a repetir
} while (condición);
```

A continuación te proporciono un ejemplo de código para imprimir los números del 1 al 10 utilizando un bucle **`do-while`**:

```c
int i = 1;
do {
    printf("%d\n", i);
    i++;
} while (i <= 10);
```

> Es importante tener en cuenta que los bucles pueden ser peligrosos si no se utilizan correctamente. Es importante asegurarse de que la condición de salida sea alcanzable y que el bucle no se ejecute indefinidamente.

## Operadores lógicos

En C existen varios operadores lógicos que se utilizan para evaluar expresiones booleanas y producir un resultado verdadero o falso.

Los operadores lógicos más comunes son:

- Operador AND (&&): Evalúa dos o más condiciones y devuelve verdadero si todas las condiciones son verdaderas.
- Operador OR (||): Evalúa dos o más condiciones y devuelve verdadero si al menos una de las condiciones es verdadera.
- Operador NOT (!): Invierte el valor de una expresión booleana.

Por ejemplo:

```c
int a = 10;
int b = 20;

if(a == 10 && b == 20) {
    printf("Ambas condiciones se cumplen\\n");
}

if(a == 10 || b == 30) {
    printf("Al menos una condición se cumple\\n");
}

if(!(a == 20)) {
    printf("La condición no se cumple\\n");
}
```

> Es importante tener en cuenta que los operadores lógicos se evalúan de izquierda a derecha y que la evaluación se detiene tan pronto como se conoce el resultado final. Por ejemplo, si la primera condición en una expresión AND es falsa, no se evaluarán las condiciones restantes ya que el resultado final será falso.

## Operaciones básicas

C cuenta con operadores básicos para realizar operaciones matemáticas como suma, resta, multiplicación y división. Además, también cuenta con operadores de comparación como menor que, mayor que y igual. Por ejemplo:

```c
int a = 10;
int b = 20;

int suma = a + b;
int resta = b - a;
int multiplicacion = a * b;
int division = b / a;

if(a < b) {
    printf("a es menor que b\\n");
}

if(b > a) {
    printf("b es mayor que a\\n");
}

if(a == 10) {
    printf("a es igual a 10\\n");
}
```

¡Y eso es todo! Esperamos que este documento te haya ayudado a entender mejor la sintaxis de C y cómo utilizar diferentes conceptos en este lenguaje de programación.

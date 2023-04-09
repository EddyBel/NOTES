---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Basico, C++, Sintaxis
Fecha: January 11, 2023
---

# Sintaxis de C++

## Variables y tipos de datos

En C++, las variables son lugares de almacenamiento en la memoria del computador que pueden contener un valor o una referencia a un objeto. Para declarar una variable en C++, se usa la palabra clave "int", "float", "double", "bool", "char" seguida del nombre de la variable. El tipo de datos determina qué tipo de valores puede almacenar la variable. Algunos tipos de datos comunes en C++ son:

- int: para números enteros, como -1, 0, 1, 2, etc.
- float: para números con punto flotante, como 1.23, 3.14, etc.
- double: para números con punto flotante de precisión doble, como 1.23, 3.14, etc.
- bool: para valores booleanos, true o false.
- char: para caracteres, como 'a', 'b', 'c', etc.

```cpp
int numeroEntero = 5;
float numeroPuntoFlotante = 3.14;
double numeroPuntoFlotanteDoble = 2.718281828;
bool variableBooleana = true;
char caracter = 'a';
```

## Variables dinámicas

En C++, se puede declarar una variable sin especificar su tipo de dato utilizando la palabra clave "auto". El compilador de C++ determinará automáticamente el tipo de dato de la variable en base al valor asignado.

```cpp
auto numero = 5; // numero es de tipo int
auto numeroFlotante = 3.14; // numeroFlotante es de tipo double
auto caracter = 'a'; // caracter es de tipo char
```

También se puede usar "decltype" para determinar el tipo de dato de una expresión existente.

```cpp
int numero = 5;
decltype(numero) numero2 = 10; // numero2 es de tipo int
```

> Es importante mencionar que el uso de "auto" y "decltype" se recomienda solo en casos específicos, ya que puede dificultar la lectura y la comprensión del código, además de poder generar confusiones, ya que no se sabe con certeza el tipo de dato de la variable.

## Operadores matemáticos

C++ tiene un conjunto de operadores que se utilizan para realizar operaciones matemáticas y lógicas. Los operadores más comunes son +, -, \*, / y % (módulo).

```cpp
int a = 5, b = 2;
cout << a + b << endl;   // imprime 7
cout << a - b << endl;   // imprime 3
cout << a * b << endl;   // imprime 10
cout << a / b << endl;   // imprime 2
cout << a % b << endl;   // imprime 1
```

## Operadores lógicos

Claro, los operadores lógicos en C++ son utilizados para realizar operaciones lógicas y comparaciones en expresiones. Los operadores lógicos más comunes en C++ son && (and), || (or) y ! (not).

- El operador && (and) compara dos expresiones lógicas y devuelve verdadero si ambas son verdaderas. Si alguna de las expresiones es falsa, devuelve falso.
  ```cpp
  bool expresion1 = true, expresion2 = false;
  cout << (expresion1 && expresion2) << endl; // imprime 0 (false)
  ```
- El operador || (or) compara dos expresiones lógicas y devuelve verdadero si al menos una de las expresiones es verdadera. Si ambas expresiones son falsas, devuelve falso.
  ```cpp
  bool expresion1 = true, expresion2 = false;
  cout << (expresion1 || expresion2) << endl; // imprime 1 (true)
  ```
- l operador ! (not) invierte el valor de una expresión lógica. Si la expresión es verdadera, devuelve falso, y si la expresión es falsa, devuelve verdadero.
  ```cpp
  bool expresion = true;
  cout << (!expresion) <<endl; // imprime 0 (false)
  ```
  ## Funciones
  En C++, una función es un bloque de código que se puede llamar desde otro lugar del programa para realizar una tarea específica. Las funciones tienen un nombre, un conjunto de parámetros de entrada (opcionales) y un valor de retorno (opcional).
  Una función se declara con la palabra clave "void" o el tipo de retorno seguido del nombre de la función y una lista de parámetros entre paréntesis.
  ```cpp
  void imprimirMensaje() {
      std::cout << "Hola, mundo!" << std::endl;
  }
  ```
  La función anterior no tiene parámetros de entrada ni valor de retorno. La función simplemente imprime un mensaje en pantalla.
  ```cpp
  int sumar(int a, int b) {
      return a + b;
  }
  ```
  La función anterior tiene dos parámetros de entrada de tipo entero y retorna un valor entero. La función simplemente suma dos números y retorna el resultado.
  Una vez que se ha definido una función, se puede llamar a ella desde otro lugar del programa proporcionando los argumentos necesarios (si se requieren) entre paréntesis.
  ```cpp
  int main() {
      imprimirMensaje();
      int resultado = sumar(3, 4);
      std::cout << "El resultado es: " << resultado << std::endl;
      return 0;
  }
  ```
  En el ejemplo anterior se llama a las dos funciones declaradas anteriormente. La primera función no requiere argumentos, mientras que la segunda requiere dos argumentos de tipo entero.
  En C++, se pueden declarar funciones con valores por defecto para algunos o todos sus parámetros de entrada. Esto significa que si no se proporciona un valor para ese parámetro cuando se llama a la función, se usará el valor por defecto especificado en su declaración.
  Para especificar un valor por defecto para un parámetro, se coloca el operador "=" seguido del valor deseado después del tipo de dato y el nombre del parámetro en la lista de parámetros de la función.
  ```cpp
  void imprimirMensaje(std::string mensaje, int veces = 1) {
      for (int i = 0; i < veces; i++) {
          std::cout << mensaje << std::endl;
      }
  }
  ```
  En el ejemplo anterior, se declara una función "imprimirMensaje" que tiene dos parámetros: "mensaje" y "veces". El parámetro "mensaje" no tiene un valor por defecto, por lo que debe proporcionarse un valor cuando se llama a la función. El parámetro "veces" tiene un valor por defecto de 1, por lo que si no se proporciona un valor para este parámetro cuando se llama a la función, se usará el valor 1.
  En cuanto a las funciones que no se sabe que valor retornaran se puede declarar como "void" para indicar que no retorna ningún valor, o se puede utilizar la palabra "auto" para que el compilador determine el tipo de dato de retorno en base al valor que retorna la función.
  ```cpp
  auto funcionDesconocida() {
      if (algunaCondicion) {
          return "Hola";
      } else {
          return 3.14;
      }
  }
  ```
  En el ejemplo anterior, se declara una función "funcionDesconocida" que no tiene un tipo de retorno especificado. El compilador determinará automáticamente el tipo de retorno en base al valor que retorna la función en cada rama del condicional.
  > Es importante mencionar que el uso de "auto" para el retorno de una función se recomienda solo en casos específicos, ya que puede dificultar la lectura y la comprensión del código, además de poder generar confusiones, ya que no se sabe con certeza el tipo de dato de retorno de la función.
  ## Condicionales
  En C++, las condicionales son estructuras de control de flujo que permiten ejecutar diferentes bloques de código dependiendo de si se cumple o no una determinada condición. Las condicionales más comunes son "if", "if-else" y "switch-case".
  - "if" se utiliza para ejecutar un bloque de código solo si se cumple una condición dada. La sintaxis es la siguiente:
    ```cpp
    int numero = 5;
    if (numero > 0) {
        std::cout << "El número es positivo" << std::endl;
    }
    ```
  - "if-else" se utiliza para ejecutar un bloque de código si se cumple una condición y otro bloque de código si no se cumple. La sintaxis es la siguiente:
    ```cpp
    int numero = -5;
    if (numero > 0) {
        std::cout << "El número es positivo" << std::endl;
    } else {
        std::cout << "El número es negativo" << std::endl;
    }
    ```
  - "switch-case" se utiliza para ejecutar un bloque de código específico dependiendo del valor de una variable. La sintaxis es la siguiente:
    ```cpp
    char opcion = 'b';
    switch (opcion) {
        case 'a':
            std::cout << "Opción A seleccionada" << std::endl;
            break;
        case 'b':
            std::cout << "Opción B seleccionada" << std::endl;
            break;
        case 'c':
            std::cout << "Opción C seleccionada" << std::endl;
            break;
        default:
            std::cout << "Opción inválida" << std::endl;
    }
    ```
  En C++, "else if" es una extensión del "if-else" que permite comprobar varias condiciones de manera encadenada. Es útil cuando se quieren comprobar varias condiciones y ejecutar diferentes bloques de código dependiendo de la primera condición que se cumpla.
  ```cpp
  int numero = 5;
  if (numero > 0) {
      std::cout << "El número es positivo" << std::endl;
  } else if (numero < 0) {
      std::cout << "El número es negativo" << std::endl;
  } else {
      std::cout << "El número es cero" << std::endl;
  }
  ```
  En este ejemplo se comprueban tres condiciones diferentes y se ejecuta un bloque de código diferente dependiendo de la primera condición que se cumpla.
  > Es importante mencionar que se pueden agregar tantos "else if" como sea necesario para cubrir todos los casos posibles. También es importante mencionar que al usar varios else if se evita tener una gran cantidad de if anidados lo cual hace mas legible y entendible el código.
  ## Bucles
  En C++, los bucles son estructuras de control de flujo que permiten ejecutar un bloque de código varias veces de manera automatizada. Los bucles más comunes son "while", "do-while" y "for".
  - "while" se utiliza para ejecutar un bloque de código mientras se cumpla una condición dada. La sintaxis es la siguiente:
    ```cpp
    int numero = 5;
    while (numero > 0) {
        std::cout << numero << std::endl;
        numero--;
    }
    ```
  - "do-while" es similar al "while" pero la condición se comprueba al final de cada iteración. Esto significa que el código dentro del bucle se ejecutará al menos una vez, independientemente de si se cumple o no la condición. La sintaxis es la siguiente:
    ```cpp
    int numero = 5;
    do {
        std::cout << numero << std::endl;
        numero--;
    } while (numero > 0);
    ```
  - "for" se utiliza para ejecutar un bloque de código un número determinado de veces o mientras se cumpla una condición. La sintaxis es la siguiente:
  ```cpp
  for (int i = 1; i <= 10; i++) {
      std::cout << i << std::endl;
  }
  ```

En todos estos ejemplos se esta haciendo uso de una variable de control (numero, i) para controlar cuando se debe dejar de ejecutar el bloque de código del bucle.

En general los bucles son muy útiles para automatizar tareas y procesos repetitivos en un programa, también para recorrer estructuras de datos como arreglos y listas.

> Es importante mencionar que es importante tener cuidado al usar bucles ya que un bucle infinito o una mala condición de parada pueden causar que el programa se quede en un bucle interminable.

---
Completado: Yes
Dificultad: ⭐
Etiquetas: Bases, Basico, C, Conceptos
Fecha: February 16, 2023
---

# Conceptos de C

C es un lenguaje de programación creado en 1972 por Dennis M. [Ritchie en los Laboratorios Bell como evolución del anterior lenguaje B, a su vez basado en BCPL](https://www.ecured.cu/Historia_del_Lenguaje_C). [Al igual que B, es un lenguaje orientado a la implementación de Sistemas Operativos, concretamente Unix](https://www.ecured.cu/Historia_del_Lenguaje_C). [C es un lenguaje de programación de bajo nivel que permite una gran flexibilidad y control sobre el hardware](https://es.wikipedia.org/wiki/Historia_de_los_lenguajes_de_programaci%C3%B3n).

[C es uno de los lenguajes de programación más populares y se utiliza para desarrollar sistemas operativos, compiladores y otros programas de sistema](https://computerhoy.com/reportajes/tecnologia/historia-lenguajes-programacion-428041). [Además, C ha sido muy influyente en el desarrollo de otros lenguajes de programación como C++, Java y Python](https://es.wikipedia.org/wiki/Historia_de_los_lenguajes_de_programaci%C3%B3n).

## Estructura de un archivo de C

Un archivo de C típicamente comienza con la inclusión de librerías, seguido de la definición de variables globales y la declaración de funciones. Por ejemplo:

```c
#include <stdio.h>

int edad;

void saludo() {
    printf("Hola, ¿cómo estás?\\n");
}

int main() {
    saludo();
    return 0;
}

```

La estructura de un archivo C se compone de tres partes principales:

- La declaración de las bibliotecas necesarias para el programa.
- La declaración de las variables globales y funciones.
- La función principal del programa.

En el código la primera parte se cumple con la inclusión de la biblioteca stdio.h que es la biblioteca estándar de entrada y salida de datos en C. Esta biblioteca contiene funciones para leer y escribir archivos.

La segunda parte se cumple con la declaración de la variable global “edad” y la función “saludo”. La variable global “edad” es una variable entera que no tiene un valor asignado en este caso. La función “saludo” es una función que imprime en pantalla el mensaje “Hola, ¿cómo estás?”.

La tercera parte se cumple con la función principal “main” que es el punto de entrada del programa. En este caso, la función “main” llama a la función “saludo” y luego retorna 0.

## Ejecución de un archivo C

Para ejecutar un código de C necesitas un compilador de C instalado en tu computadora. [Un compilador es un programa que traduce código escrito en un lenguaje de programación (llamado fuente) a otro lenguaje (conocido como objeto)](https://es.wikipedia.org/wiki/Compilador). [En este tipo de traductor el lenguaje fuente es generalmente un lenguaje de alto nivel y el objeto un lenguaje de bajo nivel, como assembly o código máquina](https://es.wikipedia.org/wiki/Compilador). Uno de los compiladores más populares es GCC (Colección de compiladores GNU).

Algunos otros de los compiladores de C más populares son:

- MinGW
- Visual Studio
- Code::Blocks
- Dev-C++
- Borland C++

Una vez que hayas compilado tu programa con el compilador de tu preferencia, puedes ejecutar el binario resultante y listo puedes ver la ejecución de tu programa.

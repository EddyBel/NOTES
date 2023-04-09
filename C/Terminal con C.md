---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: C, Funciones, Shell, Terminal
Fecha: March 18, 2023
---

# Integración del lenguaje C en la terminal

En este documento se explicará cómo se integra el lenguaje C en la terminal, cómo imprimir datos en la misma y cómo solicitar datos al usuario desde la terminal.

## Imprimir datos en la terminal

Para imprimir datos en la terminal en C, se utiliza la función "printf". Esta función se encarga de imprimir texto en la pantalla. Por ejemplo, para imprimir el mensaje "Hola mundo" en la terminal, se puede utilizar el siguiente código:

```c
#include <stdio.h>

int main() {
    printf("Hola mundo\\n");
    return 0;
}

```

La salida de este programa será:

```bash
Hola mundo
```

La función "printf" puede imprimir variables también. Para imprimir una variable entera, se utiliza el formato "%d". Por ejemplo:

```c
#include <stdio.h>

int main() {
    int num = 10;
    printf("El número es: %d\\n", num);
    return 0;
}
```

La salida de este programa será:

```bash
El número es: 10
```

## Solicitar datos al usuario desde la terminal

Para solicitar datos al usuario desde la terminal en C, se utiliza la función "scanf". Esta función se encarga de leer datos desde la entrada estándar (la terminal en este caso). Por ejemplo, para solicitar un número al usuario y luego imprimirlo en la terminal, se puede utilizar el siguiente código:

```c
#include <stdio.h>

int main() {
    int num;
    printf("Ingrese un número: ");
    scanf("%d", &num);
    printf("El número ingresado es: %d\\n", num);
    return 0;
}

```

La salida de este programa será:

```bash
Ingrese un número: 5
El número ingresado es: 5
```

## Solicitar una contraseña al usuario

Para solicitar una contraseña de usuario desde la terminal con C, puedes utilizar la función **`getpass()`** que se encuentra en la biblioteca **`conio.h`**. Esta función permite que el usuario ingrese una contraseña sin que se muestre en la pantalla. Aquí hay un ejemplo de cómo usarlo:

```c
#include <stdio.h>#include <conio.h>int main() {
    char password[20];
    printf("Ingrese su contraseña: ");
    getpass(password);
    printf("Su contraseña es: %s", password);
    return 0;
}
```

Este programa le pedirá al usuario que ingrese su contraseña y luego la imprimirá en la pantalla sin mostrarla.

## Solicitar un numero al usuario

Para solicitar un número en la terminal y utilizarlo para sumar y restar en C, puedes usar la función **`scanf()`** que se encuentra en la biblioteca **`stdio.h`**. Aquí hay un ejemplo de cómo usarlo:

```c
#include <stdio.h>int main() {
    int num1, num2;
    printf("Ingrese el primer número: ");
    scanf("%d", &num1);
    printf("Ingrese el segundo número: ");
    scanf("%d", &num2);
    printf("La suma de %d y %d es %d\n", num1, num2, num1 + num2);
    printf("La resta de %d y %d es %d\n", num1, num2, num1 - num2);
    return 0;
}
```

Este programa le pedirá al usuario que ingrese dos números y luego imprimirá la suma y la resta de los dos números en la pantalla.

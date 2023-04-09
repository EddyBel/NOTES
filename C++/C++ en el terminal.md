---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Basico, C++, Terminal
Fecha: January 15, 2023
---

# C++ en el terminal

Puedes interactuar con la terminal en C++ utilizando las funciones de biblioteca estándar de entrada y salida (I/O) del lenguaje.

**`#include <iostream>`**es la directiva de preprocesamiento que incluye las funciones de entrada y salida de C++. Estas funciones son proporcionadas por la biblioteca estándar de C++.

**`using namespace std;`**es una directiva que permite utilizar las funciones de la biblioteca estándar de C++ sin necesidad de escribir el nombre completo del espacio de nombres. Por ejemplo, en lugar de escribir **`std::cout`**, solo puedes escribir **`cout`**

**`int main()`**es la función principal del programa. Todo programa en C++ debe tener una función _main_.

### Cout

**`cout << "Hola mundo!" << endl;`** es una instrucción de salida que muestra el texto "Hola mundo!" en la terminal. El operador **`<<`** es el operador de inserción, que se utiliza para insertar el valor de una variable o una cadena de caracteres en el flujo de salida (stdout).El **`endl`**es un caracter especial que indica un salto de línea.

Para mostrar una salida en la terminal, puedes utilizar la función _cout_:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hola mundo!" << endl;
    return 0;
}
```

### Cin

**`cin >> input;`**es una instrucción de entrada que recibe un valor desde el usuario y lo almacena en la variable **`input`**.El operador **`>>`** es el operador de extracción, que se utiliza para extraer un valor desde el flujo de entrada (stdin).

Por ejemplo, para recibir una entrada del usuario desde la terminal, puedes utilizar la función `cin` :

```cpp
#include <iostream>
using namespace std;

int main() {
    int input;
    cout << "Ingresa un número: ";
    cin >> input;
    cout << "El número ingresado es: " << input << endl;
    return 0;
}
```

### Printft y scanf

**`printf()`** y **`scanf()`**son funciones similares a **`cout`** y **`cin`**respectivamente, pero se utilizan para mostrar o recibir datos en un formato específico. El formato se especifica mediante una cadena de formato y los valores se pasan como argumentos adicionales. Por ejemplo, para mostrar un número con dos decimales, podrías usar **`printf("%.2f", num);`**.El scanf permite algo parecido pero para la entrada de datos.

```cpp
#include <cstdio>

int main() {
    int num1, num2;
    printf("Ingresa dos numeros: ");
    scanf("%d %d", &num1, &num2);
    printf("La suma de %d y %d es %d\n", num1, num2, num1 + num2);
    return 0;
}
```

En este caso se utiliza **`printf`** para mostrar una pregunta al usuario y **`scanf`** para recibir dos números enteros y almacenarlos en variables num1 y num2, para luego sumarlos y mostrar el resultado con **`printf`** nuevamente.

### Ingresar una contraseña en la terminal.

Hay varias formas de ingresar un contraseña en C++, pero una de las formas más comunes es utilizar la función **`getch()`** de la biblioteca **`conio.h`** para recibir caracteres de entrada de forma oculta. Sin embargo, esta biblioteca solo está disponible en sistemas Windows y no es parte de la biblioteca estándar de C++.

```cpp
#include <iostream>
#include <conio.h>
using namespace std;

int main() {
    char password[100];
    int i = 0;

    cout << "Ingresa tu contraseña: ";
    while (1) {
        char ch = getch();
        if (ch == 13) {
            password[i] = '\0';
            break;
        }
        else if (ch == 8) {
            if (i > 0) {
                i--;
                cout << "\b \b";
            }
        }
        else {
            password[i++] = ch;
            cout << "*";
        }
    }

    cout << endl << "Tu contraseña es: " << password << endl;
    return 0;
}
```

Este código utiliza un bucle while para recibir caracteres de entrada hasta que se presione la tecla "Enter". Cada carácter ingresado es almacenado en un arreglo de caracteres **`password`**, y se muestra un carácter "\*" en lugar del carácter ingresado para ocultarlo. Si se presiona la tecla "Backspace", el último caracter ingresado será eliminado.

Otra forma de hacerlo es utilizando la librería <termios.h> para ocultar la contraseña, pero esta solo esta disponible en sistemas Unix.

```cpp
#include <iostream>
#include <termios.h>
#include <unistd.h>
using namespace std;

int main() {
    string password;
    termios oldt;
    tcgetattr(STDIN_FILENO, &oldt);
    termios newt = oldt;
    newt.c_lflag &= ~ECHO;

    cout << "Ingresa tu contraseña: ";
    tcsetattr(STDIN_FILENO, TCSANOW, &newt);
    getline(cin, password);
    tcsetattr(STDIN_FILENO, TCSANOW, &oldt);

    cout << endl << "Tu contraseña es: " << password << endl;
    return 0;
}
```

Este código desactiva el "echo" de la terminal para ocultar la contraseña ingresada, y luego la guarda en una variable de tipo string.

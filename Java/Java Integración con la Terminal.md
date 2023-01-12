---
Completado: Yes
Dificultad: ⭐⭐⭐
Etiquetas: Interaccion, Java, Terminal
Fecha: January 3, 2023
Fuentes: https://ifgeekthen.nttdata.com/es/que-es-y-como-usar-la-clase-scanner-en-java#:~:text=Dentro%20del%20paquete%20java.,%2C%20double%2C%20string%20y%20etc.
---

# Java Integración con la Terminal

Java proporciona varias formas de interactuar con la terminal, una de las más comunes es utilizando la clase "Scanner" para recibir datos de entrada del usuario y la clase "System" y sus métodos "out" y "err" para mostrar datos en la terminal.

La clase "Scanner" se utiliza para recibir datos de entrada del usuario a través de la terminal, puede recibir diferentes tipos de datos como números, cadenas, etc.

```java
Scanner scanner = new Scanner(System.in);
System.out.print("Ingresa tu nombre: ");
String nombre = scanner.nextLine();
System.out.print("Ingresa tu edad: ");
int edad = scanner.nextInt();
```

La clase "System" proporciona una serie de métodos para mostrar información en la terminal como "out" y "err", los cuales permiten imprimir información en la consola.

```java
System.out.println("Hola " + nombre + ", tu edad es " + edad);
System.err.println("Error inesperado");
```

Para solicitar contraseñas o información sensible se recomienda utilizar la clase "Console" la cual tiene el método "readPassword()" para solicitar al usuario que ingrese una contraseña.

```java
Console console = System.console();
char[] password = console.readPassword("Ingresa tu contraseña: ");
```

> Ten en cuenta que para que estos métodos funcionen correctamente es necesario estar en un ambiente donde exista una terminal, ya que no funcionarán correctamente cuando se ejecuta en un ambiente sin una terminal como un servidor o un IDE.

## Ejemplo de script

Este script se encarga de pedir al usuario que ingrese su nombre y edad utilizando un objeto Scanner, luego muestra un saludo al usuario con la información ingresada, para finalizar se utiliza el método readPassword de la clase Console para ocultar la contraseña ingresada y luego se muestra en la terminal.

```java
import java.util.Scanner;

public class TerminalExample {
    public static void main(String[] args) {
        // Se crea un nuevo objeto Scanner para leer datos de entrada del usuario
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingresa tu nombre: ");
        // Se guarda el valor ingresado por el usuario en una variable
        String nombre = scanner.nextLine();

        System.out.print("Ingresa tu edad: ");
        // Se guarda el valor ingresado por el usuario en una variable
        int edad = scanner.nextInt();

        System.out.println("Hola " + nombre + ", tu edad es " + edad);

        // Se crea una nueva variable password para guardar la contraseña ingresada
        char[] password;

        // Utilizando el método readPassword de la clase Console para ocultar la contraseña ingresada
        password = System.console().readPassword("Ingresa tu contraseña: ");
        System.out.println("Tu contraseña es: " + new String(password));
    }
}
```

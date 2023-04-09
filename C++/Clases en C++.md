---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: C++, Clases, OOP, Objetos, Sintaxis
Fecha: January 12, 2023
---

# Clases en C++

En C++, las clases son una característica de programación orientada a objetos que permite crear tipos de datos personalizados. Las clases se utilizan para modelar entidades del mundo real en el código, y proporcionan una forma de encapsular datos y comportamientos relacionados.

Una clase se define con la palabra clave "class" seguida del nombre de la clase. Dentro de la clase se pueden declarar variables miembro (también conocidas como atributos o campos) y funciones miembro (también conocidas como métodos).

```cpp
class Persona {
public:
    std::string nombre;
    int edad;

    void imprimirDatos() {
        std::cout << "Nombre: " << nombre << std::endl;
        std::cout << "Edad: " << edad << std::endl;
    }
};
```

En el ejemplo anterior, se define una clase "Persona" que tiene dos variables miembro: "nombre" y "edad", y una función miembro "imprimirDatos" que imprime los valores de las variables miembro en pantalla.

Para utilizar una clase, se crea un objeto de esa clase asignando espacio en memoria para almacenar los datos. El espacio se puede asignar utilizando el operador "new" o directamente en una variable.

```cpp
int main() {
    Persona persona1;
    persona1.nombre
```

Para utilizar una clase, se crea un objeto de esa clase asignando espacio en memoria para almacenar los datos. En el ejemplo anterior, se crea un objeto "persona1" de la clase "Persona" y se accede a las variables miembro "nombre" y "edad" para asignarles valores. También se llama a la función miembro "imprimirDatos" para imprimir los valores de las variables miembro en pantalla.

```cpp
int main() {
    Persona persona1;
    persona1.nombre = "Juan";
    persona1.edad = 30;
    persona1.imprimirDatos();

    return 0;
}
```

## Constructores

Además, las clases también pueden tener constructores, los cuales son funciones especiales que se ejecutan automáticamente cuando se crea un objeto de esa clase, y permiten inicializar los datos miembro de la clase de manera automatizada.

```cpp
class Persona {
public:
    std::string nombre;
    int edad;

    Persona(std::string nombre, int edad) {
        this->nombre = nombre;
        this->edad = edad;
    }

    void imprimirDatos() {
        std::cout << "Nombre: " << nombre << std::endl;
        std::cout << "Edad: " << edad << std::endl;
    }
};
```

En este ejemplo se agrega un constructor ala clase "Persona" que recibe dos parámetros "nombre" y "edad" y los asigna a las variables miembro correspondientes. Ahora al crear un objeto de la clase "Persona" se pueden pasar los valores para inicializar las variables miembro de manera automatizada.

```cpp
int main() {
    Persona persona1("Juan",30);
    persona1.imprimirDatos();

    return 0;
}
```

## Herencia

Claro, la herencia es un mecanismo de la programación orientada a objetos que permite crear una nueva clase a partir de una existente, permitiendo así reutilizar código y organizar de manera jerárquica las clases.

La clase existente se conoce como clase base o superclase y la clase nueva se conoce como clase derivada o subclase. La clase derivada hereda todas las propiedades y comportamientos de la clase base, es decir, adquiere todos los atributos y métodos de la clase base, y puede también añadir o redefinir atributos y métodos.

La sintaxis para crear una clase derivada es la siguiente:

```cpp
class NombreClaseDerivada : tipoDeHerencia NombreClaseBase{
    //atributos y métodos de la clase derivada
};
```

Donde el "tipoDeHerencia" especifica el modo en que se heredan los miembros de la clase base, puede ser "public", "protected" o "private". La herencia public significa que los miembros de la clase base serán accesibles desde la clase derivada y desde cualquier otra parte del programa, la herencia protected significa que los miembros de la clase base serán accesibles solo desde la clase derivada y las clases que hereden de ella, y la herencia private significa que los miembros de la clase base serán accesibles solo desde la clase derivada.

```cpp
class Persona {
  public:
    std::string nombre;
    int edad;
    void imprimirDatos() {
        cout << "Nombre: " << nombre << endl;
        cout << "Edad: " << edad << endl;
    }
};

class Empleado : public Persona {
  public:
    std::string cargo;
    double salario;
    void imprimirDatos() {
        Persona::imprimirDatos();
        cout << "Cargo: " << cargo << endl;
        cout << "Salario: " << salario << endl;
    }
};
```

En el ejemplo anterior, la clase "Empleado" es una clase derivada de la clase "Persona", utilizando herencia pública, por lo tanto, la clase "Empleado" adquiere todas las propiedades y comportamientos de la clase "Persona" incluyendo las variables miembro "nombre" y "edad" y la función miembro "imprimirDatos". Además, la clase "Empleado" tiene dos variables miembro adicionales "cargo" y "salario" y una función miembro "imprimirDatos" redefinida para imprimir los valores de las variables miembro de la clase "Empleado".

Al crear un objeto de la clase "Empleado" tendremos acceso a todos los atributos y métodos de la clase "Persona" y los de la clase "Empleado" esto se debe a que la clase "Empleado" hereda de "Persona".

```cpp
int main() {
    Empleado empleado1;
    empleado1.nombre = "Juan";
    empleado1.edad = 25;
    empleado1.cargo = "
```

El ejemplo anterior, en el cuerpo principal del programa se crea un objeto "empleado1" de la clase "Empleado" y se accede a las variables miembro "nombre", "edad", "cargo" y "salario" para asignarles valores. También se llama a la función miembro "imprimirDatos" para imprimir los valores de las variables miembro en pantalla.

```cpp
int main() {
    Empleado empleado1;
    empleado1.nombre = "Juan";
    empleado1.edad = 25;
    empleado1.cargo = "Programador";
    empleado1.salario = 6000.0;
    empleado1.imprimirDatos();

    return 0;
}
```

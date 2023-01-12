---
Completado: Yes
Dificultad: ⭐⭐⭐
Etiquetas: Clases, Java, OOP, Objetos
Fecha: January 5, 2023
Fuentes: https://docs.oracle.com/javase/8/docs/api/java/lang/Class.html
---

# Java orientado a objetos

Java es un lenguaje de programación orientado a objetos, lo que significa que se basa en el concepto de objetos y clases. Una clase es una plantilla o molde para crear objetos, y un objeto es una instancia de una clase. Cada objeto tiene sus propios atributos (variables de instancia) y comportamientos (métodos).

## Crear una clase

Para crear una clase en Java se utiliza la palabra clave "class" seguida del nombre de la clase, el nombre de las clases suelen empezar con mayúscula. El cuerpo de la clase se encuentra dentro de llaves "{}".

```java
class NombreClase {
    // Atributos y métodos de la clase
}
```

Por ejemplo, si queremos crear una clase "Auto" con atributos como "marca" y "color" y métodos como "encender" y "apagar", el código podría verse así:

```java
class Auto {
    // Atributos de la clase
    String marca;
    String color;

    // Métodos de la clase
    void encender() {
        System.out.println("El auto está encendido");
    }
    void apagar() {
        System.out.println("El auto está apagado");
    }
}
```

Para crear un objeto de una clase se utiliza la palabra clave "new" seguida del nombre de la clase y paréntesis.

```java
Auto miAuto = new Auto();
```

Luego se puede acceder a los atributos y métodos de la clase utilizando el operador punto ".”

```java
miAuto.marca = "Toyota";
miAuto.color = "Rojo";
miAuto.encender();
```

## Constructores

Las clases también pueden tener constructores, los cuales son métodos especiales que se utilizan para inicializar un objeto de una clase. Por ejemplo, podríamos crear un constructor para nuestra clase "Auto" que asigne valores iniciales a los atributos "marca" y "color".

La sintaxis para crear un constructor es utilizar el nombre de la clase, seguido de paréntesis, y el cuerpo del método, dentro de las llaves {}.

```java
class Auto {
    // Atributos de la clase
    String marca;
    String color;

    // Constructor
    Auto(String marca, String color) {
        this.marca = marca;
        this.color = color;
    }
    // Métodos de la clase
    void encender() {
        System.out.println("El auto está encendido");
    }
    void apagar() {
        System.out.println("El auto está apagado");
    }
}
```

Y para utilizar el constructor se crea un objeto y se utilizan los parámetros que se espera recibir.

```java
Auto miAuto = new Auto("Toyota","Rojo");
```

## Encapsulamiento

El encapsulamiento se refiere a la ocultación de los detalles de implementación de una clase, es decir, los atributos y métodos de una clase deben ser declarados con modificadores de acceso para controlar quién tiene acceso a ellos. Los modificadores más comunes son "_public_", "_private_" y "_protected_".

- El modificador "public" permite que cualquier clase acceda a un atributo o método.
- El modificador "private" solo permite que la propia clase acceda a un atributo o método.
- El modificador "protected" permite que cualquier clase que herede de esta clase acceda a un atributo o método.

Un ejemplo de esto sería el siguiente:

```java
class Auto {
    // Atributos privados
    private String marca;
    private String color;
    private int velocidad;

    // Constructor
    public Auto(String marca, String color) {
        this.marca = marca;
        this.color = color;
        this.velocidad = 0;
    }

    // Métodos públicos
    public void encender() {
        System.out.println("El auto está encendido");
    }

    public void acelerar(int aumentoVelocidad) {
        this.velocidad += aumentoVelocidad;
    }

    public void frenar(int disminucionVelocidad) {
        this.velocidad -= disminucionVelocidad;
    }

    public void apagar() {
        System.out.println("El auto está apagado");
    }
    // getters y setters
    public String getMarca() {
        return marca;
    }
    public void setMarca(String marca) {
        this.marca = marca;
    }
    public String getColor() {
        return color;
    }
    public void setColor(String color) {
        this.color = color;
    }
    public int getVelocidad() {
        return velocidad;
    }
}
```

En este ejemplo, la clase "Auto" tiene tres atributos: "marca", "color" y "velocidad", los cuales son declarados como privados, lo que significa que solo pueden ser accedidos desde dentro de la clase.

Los métodos "encender", "acelerar", "frenar", "apagar" son públicos y pueden ser accedidos desde cualquier otra clase.

Y por ultimo se proporciona los métodos Getters y Setters para acceder a los atributos privados de forma segura

Los métodos getters y setters, también conocidos como accesores y mutadores, son utilizados para obtener y establecer los valores de los atributos privados de una clase. En este caso, se han definido los métodos getMarca(), setMarca(String marca), getColor(), setColor(String color) y getVelocidad() para obtener y establecer los valores de los atributos "marca", "color" y "velocidad".

La ventaja de utilizar estos métodos para acceder a los atributos privados es que permite tener un mayor control sobre cómo se utilizan los atributos de una clase. Por ejemplo, en el método setMarca(String marca) se podría incluir una validación para asegurar que la marca asignada sea válida antes de establecer el valor del atributo.

Asimismo, encapsulamiento permite a los desarrolladores modificar la implementación de una clase sin afectar a las otras clases que la utilizan, ya que solo se expone la interfaz pública de la clase. Esto mejora la seguridad y facilita el mantenimiento del código.

## Herencia

La herencia en Java permite que una clase herede las propiedades y comportamientos de otra clase. La clase que hereda se conoce como subclase o clase hija, y la clase de la que se hereda se conoce como superclase o clase padre.

La sintaxis para especificar una clase como subclase es utilizar la palabra clave "extends" seguida del nombre de la superclase.

```java
class SubClase extends SuperClase {
    // Atributos y métodos de la subclase
}
```

Por ejemplo, si queremos crear una subclase "AutoDeportivo" que herede de la clase "Auto", el código podría verse así:

```java
class AutoDeportivo extends Auto {
    private int caballosDeFuerza;
    // constructor
    public AutoDeportivo(String marca, String color, int caballosDeFuerza) {
        super(marca, color);
        this.caballosDeFuerza = caballosDeFuerza;
    }
    public int getCaballosDeFuerza() {
        return caballosDeFuerza;
    }
}
```

En este ejemplo, la clase "AutoDeportivo" hereda los atributos "marca" y "color" y los métodos "encender" y "apagar" de la clase "Auto". Además, tiene un nuevo atributo "caballosDeFuerza" y un nuevo método "getCaballosDeFuerza()" propio. Al utilizar la palabra super en el constructor se esta llamando al constructor de la clase padre "Auto”.

La herencia permite crear jerarquías de clases, donde una clase puede heredar de otra, y esta a su vez heredar de otra, y así sucesivamente. Esto permite reutilizar código y organizar el código de una manera lógica y estructurada.

## Polimorfismo

El polimorfismo es una característica de la programación orientada a objetos que permite que una clase tenga varias formas de ser implementada. En otras palabras, permite que un objeto tenga distintos comportamientos dependiendo del contexto en el que se encuentra. En Java, el polimorfismo se logra mediante la creación de una interfaz común para varias clases.

Una de las formas de implementar el polimorfismo en Java es mediante el uso de interfaces. Una interfaz es un conjunto de métodos que deben ser implementados por las clases que la implementan. Una clase puede implementar varias interfaces.

Por ejemplo, si queremos crear una interfaz "Movil" que contenga el método "mover()" que debe ser implementado por cualquier clase que quiera ser considerada como "Movil", el código podría verse así:

```java
interface Movil {
    void mover();
}
class Auto implements Movil {
    @Override
    public void mover() {
        System.out.println("El auto esta avanzando");
    }
}
class Bicicleta implements Movil {
    @Override
    public void mover() {
        System.out.println("La bicicleta esta avanzando");
    }
}
class Patineta implements Movil {
    @Override
    public void mover() {
        System.out.println("La patineta esta avanzando");
    }
}
```

En este caso cada una de las clases Auto, Bicicleta y Patineta implementa el método mover() de forma distinta, pero gracias a que todas implementan la interfaz Movil, se puede tratarlas de forma genérica como objetos que implementan la interfaz y así aplicar el polimorfismo.

```java
public static void moverVehiculo(Movil vehiculo){
        vehiculo.mover();
}
```

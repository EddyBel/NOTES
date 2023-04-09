---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Clases, Conceptos, JavaScript, OOP
Fecha: November 7, 2022
---

# JavaScript orientado a objetos

La programación orientada a objetos (OOP) es un paradigma de programación que se basa en la idea de que todo en el mundo es un objeto con propiedades y comportamientos asociados. En JavaScript, podemos implementar la OOP utilizando clases.

## Clases en JavaScript

Una clase es una plantilla para crear objetos. En JavaScript, podemos definir una clase utilizando la palabra clave 'class'. Por ejemplo, podemos definir una clase 'Persona' de la siguiente manera:

```js
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}.`);
  }
}
```

La clase 'Persona' tiene dos propiedades: 'nombre' y 'edad'. Además, tiene un método 'saludar' que muestra un mensaje en la consola.

Para crear un objeto a partir de una clase, podemos utilizar la palabra clave 'new'. Por ejemplo, podemos crear un objeto 'persona1' a partir de la clase 'Persona':

```js
const persona1 = new Persona("John", 30);
persona1.saludar();
```

Este código muestra el mensaje "Hola, soy John." en la consola.

## Herencia en JavaScript

La herencia es un mecanismo mediante el cual una clase puede heredar propiedades y métodos de otra clase. En JavaScript, podemos implementar la herencia utilizando la palabra clave 'extends'. Por ejemplo, podemos definir una clase 'Estudiante' que hereda de la clase 'Persona':

```js
class Estudiante extends Persona {
  constructor(nombre, edad, carrera) {
    super(nombre, edad);
    this.carrera = carrera;
  }

  estudiar() {
    console.log(`${this.nombre} está estudiando ${this.carrera}.`);
  }
}
```

La clase 'Estudiante' tiene tres propiedades: 'nombre', 'edad' y 'carrera'. Además, tiene un método 'estudiar' que muestra un mensaje en la consola.

Para crear un objeto a partir de la clase 'Estudiante', podemos utilizar la palabra clave 'new'. Por ejemplo, podemos crear un objeto 'estudiante1' a partir de la clase 'Estudiante':

```js
const estudiante1 = new Estudiante("Mary", 20, "Ingeniería");
estudiante1.saludar();
estudiante1.estudiar();
```

Este código muestra el mensaje "Hola, soy Mary." y "Mary está estudiando Ingeniería." en la consola.

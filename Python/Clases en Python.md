---
Completado: Yes
Dificultad: ⭐
Etiquetas: Conceptos, Programación, Python
Fecha: March 16, 2023
---

# Clases en Python

Python es un lenguaje de programación orientado a objetos. Esto significa que todo lo que se puede hacer en Python es un objeto, con sus propiedades y métodos. Para crear nuestros propios objetos, podemos usar las clases.

## ¿Qué es una clase?

Una clase es un tipo de datos personalizado que define un conjunto de propiedades y métodos. Las propiedades son variables que contienen datos, mientras que los métodos son funciones que realizan acciones en esos datos.

## Sintaxis de la clase

La sintaxis para crear una clase en Python es la siguiente:

```python
class NombreDeLaClase:
    def __init__(self, propiedades):
        self.propiedad1 = propiedades[0]
        self.propiedad2 = propiedades[1]

    def metodo1(self):
        # código del método1

    def metodo2(self):
        # código del método2

```

- La palabra clave `class` indica que estamos creando una clase.
- `NombreDeLaClase` es el nombre que le damos a nuestra clase. Sigue las mismas reglas que cualquier otro nombre de variable en Python.
- `__init__` es un método especial que se llama cuando se crea una nueva instancia de la clase. Es aquí donde se definen las propiedades de la clase.
- `self` es una referencia al objeto actual. Se utiliza para acceder a las propiedades y métodos de la clase.
- `propiedad1` y `propiedad2` son dos propiedades de ejemplo que se definen en el constructor de la clase.
- `metodo1` y `metodo2` son dos métodos de ejemplo que se definen en la clase.

## Crear una instancia de la clase

Para crear una instancia de la clase, simplemente llamamos al nombre de la clase como si fuera una función:

```python
mi_objeto = NombreDeLaClase([valor1, valor2])

```

Esto creará un nuevo objeto de la clase `NombreDeLaClase`, con las propiedades `propiedad1` y `propiedad2` inicializadas con `valor1` y `valor2`.

## Acceder a las propiedades y métodos de la clase

Para acceder a las propiedades y métodos de la clase, utilizamos la sintaxis de punto:

```python
mi_objeto.propiedad1
mi_objeto.metodo1()

```

## Ejemplo completo

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def saludar(self):
        print("Hola, mi nombre es", self.nombre)

# Crear una instancia de la clase Persona
persona1 = Persona("Juan", 30)

# Acceder a las propiedades y métodos de la clase Persona
print(persona1.nombre)  # Juan
print(persona1.edad)  # 30
persona1.saludar()  # Hola, mi nombre es Juan

```

En este ejemplo, creamos una clase `Persona` con dos propiedades (`nombre` y `edad`) y un método (`saludar`). Luego, creamos una instancia de la clase `Persona` llamada `persona1` y accedemos a sus propiedades y métodos.

# Conclusión

Las clases son una herramienta poderosa en Python que nos permiten crear nuestros propios objetos con propiedades y métodos personalizados. A medida que vayamos avanzando en la programación orientada a objetos, veremos cómo las clases pueden ayudarnos a crear código más modular y reutilizable.

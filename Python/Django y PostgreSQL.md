---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Backend, Django, Python, SQL
Fecha: November 7, 2022
Fuentes: https://www.youtube.com/watch?v=T1intZyhXDU&t=1s
---

# Django y PostgreSQL

## Conexión a una base de datos en Django

Para conectarse a una base de datos en Django, primero se debe configurar la base de datos en el archivo `settings.py`. En este archivo se encuentran las configuraciones del proyecto, incluyendo la configuración de la base de datos.

### Configuración de la base de datos en `settings.py`

En el archivo `settings.py`, se debe definir la base de datos que se utilizará, así como la información necesaria para conectarse a ella. Para esto, se utiliza la sección `DATABASES`. Dentro de esta sección, se debe especificar el motor de la base de datos, el nombre de la base de datos, el usuario y la contraseña.

Por ejemplo, si se desea utilizar PostgreSQL como motor de base de datos, se debe definir la configuración de la siguiente manera:

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'nombre_de_la_base_de_datos',
        'USER': 'usuario',
        'PASSWORD': 'contraseña',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

```

En este ejemplo, el motor de la base de datos es `postgresql`, el nombre de la base de datos es `nombre_de_la_base_de_datos`, el usuario es `usuario`, la contraseña es `contraseña`, el host es `localhost` y el puerto es `5432`.

### Creación de modelos

Una vez que se ha configurado la base de datos en `settings.py`, se deben crear los modelos que representarán las tablas de la base de datos.

Para crear un modelo, se debe definir una clase que herede de `django.db.models.Model`. En esta clase, se definen los campos que tendrán las tablas de la base de datos. Por ejemplo, si se desea crear una tabla de usuarios, se puede definir el modelo de la siguiente manera:

```
from django.db import models

class User(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField()
    password = models.CharField(max_length=100)

```

En este ejemplo, se define una clase `User` que hereda de `models.Model`. Dentro de la clase, se definen los campos `name`, `email` y `password`, los cuales corresponden a los campos de la tabla de usuarios.

### Creación de tablas en la base de datos

Una vez que se han definido los modelos, se deben crear las tablas correspondientes en la base de datos. Para hacer esto, se debe ejecutar el siguiente comando en la terminal:

```
python manage.py migrate

```

Este comando creará las tablas correspondientes en la base de datos, utilizando la información definida en los modelos.

### Consultas a la base de datos

Una vez que se han creado las tablas en la base de datos, se pueden realizar consultas utilizando el ORM de Django. El ORM permite realizar consultas utilizando objetos de Python, sin tener que escribir sentencias SQL directamente.

Por ejemplo, si se desea obtener todos los usuarios de la base de datos, se puede utilizar el siguiente código:

```
from myapp.models import User

users = User.objects.all()

```

En este ejemplo, se importa el modelo `User` de la aplicación `myapp`, y se obtienen todos los usuarios utilizando el método `all()`.

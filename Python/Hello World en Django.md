---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Backend, Django, Framework, HTML, Hello World, Python
Fecha: November 17, 2022
Fuentes: https://www.youtube.com/watch?v=T1intZyhXDU&t=2608s
---

# Hello World en Django

## Instalar Django

Antes de comenzar, asegúrate de tener Python instalado en tu computadora. Luego, abre tu terminal y ejecuta el siguiente comando para instalar Django:

```bash
pip install Django
```

## Crear un proyecto Django

Para crear un proyecto Django, sigue los siguientes pasos:

1. Abre tu terminal y navega hasta el directorio donde deseas crear el proyecto.
2. Ejecuta el siguiente comando:

```bash
django-admin startproject {nombre_proyecto}
```

Donde `{nombre_proyecto}` es el nombre que le quieras dar a tu proyecto.

## Paso 3: Crear una aplicación Django

Una vez que tengas el proyecto creado, es hora de crear una aplicación dentro del proyecto. Para hacer esto, sigue los siguientes pasos:

1. Navega hasta el directorio del proyecto creado en el paso anterior.
2. Ejecuta el siguiente comando:

```bash
python manage.py startapp {nombre_app}
```

Donde `{nombre_app}` es el nombre que le quieras dar a tu aplicación.

## Crear una vista

Una vista en Django es una función que maneja una petición HTTP y devuelve una respuesta. En nuestro caso, queremos crear una vista que devuelva un mensaje de "Hello World". Para hacer esto, abre el archivo `{nombre_app}/views.py` y agrega el siguiente código:

```python
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse('Hello World!')
```

## Crear una URL para la vista

Para que la vista sea accesible desde el navegador, necesitamos crear una URL para ella. Para hacer esto, abre el archivo `{nombre_proyecto}/urls.py` y agrega el siguiente código:

```python
from django.urls import path
from {nombre_app} import views

urlpatterns = [
    path('hello-world/', views.hello_world),
]
```

## Iniciar el servidor

Finalmente, es hora de iniciar el servidor y ver nuestro "Hello World" en acción. Para hacer esto, ejecuta el siguiente comando en tu terminal:

```bash
python manage.py runserver
```

Luego, abre tu navegador y visita la siguiente URL: `http://localhost:8000/hello-world/`. Deberías ver el mensaje de "Hello World" en tu navegador.

¡Felicidades! Has creado tu primer "Hello World" con Django.

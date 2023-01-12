---
Blog: No
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Backend, Django, Framework, Inicio, Python
Fecha: November 7, 2022
Fuentes: https://www.youtube.com/watch?v=T1intZyhXDU&t=1s
---

# Como crear un proyecto en Django

# Que es django ?

Django es un framework de python que permite construir una pagina web de manera sencilla con dicho lenguaje, ademas de ser un proyecto open-source.

Algunas cosas que django nos permite son:

- Crear autenticaciones
- Comunicar tu aplicación con una base de datos
- Crear formularios
- Proteger cada ruta de la pagina

# Inicia una aplicación

Para poder iniciar una aplicación web con django de preferencia debemos crear un entorno virtual para dicho proyecto, esto se puede hacer con el modulo 🔗 **virtualenv** [https://virtualenv.pypa.io/en/latest/](https://virtualenv.pypa.io/en/latest/).

## Instalación

Una vez dentro del entorno virtual podemos instalar los módulos que necesitamos en nuestro caso sera django con el siguiente comando.

```bash
pip install django
```

Si queremos comprobar que se haya instalado correctamente, podemos verlo con el siguiente comando.

```bash
python -m django --version
```

La cual nos dará una salida con la versión del modulo como esta.

![Captura de pantalla 2022-11-07 092538.png](Como%20crear%20un%20proyecto%20en%20Django/Captura_de_pantalla_2022-11-07_092538.png)

## Creando un nuevo proyecto.

Para poder crear un nuevo proyecto con django podemos utilizar su comando _start proyect_ que traerá toda una aplicación base para trabajar.

```bash
django-admin startproject Nombre_del_proyecto
```

> **Nota**
>
> El comando anterior genera una nueva carpeta con el nombre del proyecto pero si no queremos generar una nueva carpeta, podemos _agregar un punto ( . ) al final_.

```bash
django-admin startproject Nombre_del_proyecto .
```

## Inicializando proyecto

Una vez creado el proyecto notaremos que se generaron múltiples archivos, donde el archivo _[manage.py](http://manage.py)_ es el archivo principal de la web, lo ejecutaremos con el parámetro _runserver_.

```bash
python manage.py runserver
```

Lo cual nos dará una salida como esta.

![capture.png](Como%20crear%20un%20proyecto%20en%20Django/capture.png)

Los aspectos mas importantes para resaltar es que nos dará una dirección , esa dirección hace referencia al puerto de tu maquina donde esta corriendo tu aplicación web. Si en este caso nos conectamos al puerto _127.0.0.1:8000_ o _[localhost:8000](http://localhost:8000)_ veremos lo siguiente en el navegador.

![capture2.png](Como%20crear%20un%20proyecto%20en%20Django/capture2.png)

> **NOTA**
>
> Si por alguna razón el puerto 8000 no se encuentra disponible, la web no arrancara por ello podemos configurar a la hora de iniciar el servidor el puerto que utilizara. Por ejemplo si queremos correr el servidor en el puerto 3000 lo haríamos de la siguiente manera.

```bash
python manage.py runserver 3000
```

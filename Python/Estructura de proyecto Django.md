---
Blog: No
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Backend, Django, Files, Folders, Framework, Proyect, Python
Fecha: November 17, 2022
Fuentes: https://www.youtube.com/watch?v=T1intZyhXDU&t=1s
---

# Estructura de proyecto Django

## Como se estructura un proyecto en Django ?

Después de crear una base de proyecto en Django con sus respectivo comando, podremos ver una estructura como la siguiente.

```bash
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d----     07/11/2022  08:56 a. m.                  Dev
d----     07/11/2022  09:40 a. m.                  Proyecto
-a---     07/11/2022  09:40 a. m.              0   db.sqlite3
-a---     07/11/2022  09:06 a. m.            686   manage.py
-a---     07/11/2022  09:17 a. m.             64   requeriments.txt
```

> **Dev**
>
> Esta carpeta hace referencia al _entorno virtual_ en el que estemos trabajando y tenemos instaladas las respectivas dependencias.

---

> **Proyecto**
>
> Es la carpeta del _proyecto principal_, En mi caso se llama _Proyecto_ pero esta adquirirá el nombre que le hayas dado a tu proyecto.

---

> **db.sqlite3**
>
> Este archivo es la _base de dados_ con la que podemos iniciar a trabajar, Normalmente este archivo se usa como _base de datos de desarrollo_.

---

> **manage.py**
>
> Este archivo es el script principal que se encargara de correr nuestra aplicación con sus respectivos comandos, nos permite ejecutar \*comandos administrativos\*.

---

> **requeriments.txt**
>
> Este es un simple archivo de texto plano que cuenta con las dependencias que vamos a utilizar en nuestro proyecto, se usa para poder replicar nuestro entorno de desarrollo con las _dependencias exactas_ que necesitamos para que funcione.

## Estructura del proyecto principal

Dentro de la carpeta con el nombre del proyecto ( En nuestro caso “Proyecto” ) se encuentran los archivos principales de la aplicación .

```bash
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---     07/11/2022  09:06 a. m.              0   __init__.py
-a---     07/11/2022  09:06 a. m.            409   asgi.py
-a---     07/11/2022  09:06 a. m.           3350   settings.py
-a---     07/11/2022  09:06 a. m.            771   urls.py
-a---     07/11/2022  09:06 a. m.            409   wsgi.py
```

> **init.py**
>
> Este archivo no es tan importante ya que define si el proyecto es un modulo.

> **settings.py**
> Este archivo es el mas importante de la aplicación debido a que guarda la _configuración del proyecto_.

> **urls.py**
>
> Define que _rutas_ pueden ser accedidas por el usuario. Por ejemplo si queremos una ruta “/Home” o “/Login” se definirá en este archivo.

> **asgi.py & wsgi.py**
>
> Estos archivos definen la configuración de la \*aplicación para producción\*, debido a que Django es un framework de desarrollo y no de producción, utiliza módulos externos para poder servir esa aplicación y estos archivos se encargan de esa configuración.

## Construcción de un proyecto en Django.

La forma en la que Django trabaja es separando las partes del proyecto. A cada parte Django le llama aplicación.

Esto seria que cuando creamos un proyecto en Django, este contiene sub proyectos llamados apps dentro del proyecto principal, esto nos permite desarrollar cada parte de manera independiente y conectar o desconectar cada parte del proyecto si así lo necesitamos.

![Captura de pantalla_20221117_071825.png](Estructura%20de%20proyecto%20Django/Captura_de_pantalla_20221117_071825.png)

Django tiene un comando para crear una app de manera sencilla el cual es el siguiente.

```bash
python manage.py startapp nombre_de_la_app
```

Por ejemplo:

```bash
python manage.py startapp Home
```

Este comando nos creara una app llamada Home. Esta carpeta o app aparecerá en nuestro carpeta de trabajo.

```bash
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d----     07/11/2022  08:56 a. m.                  Dev
d----     17/11/2022  07:26 p. m.                  Home
d----     07/11/2022  09:40 a. m.                  Proyecto
-a---     07/11/2022  09:40 a. m.              0   db.sqlite3
-a---     07/11/2022  09:06 a. m.            686   manage.py
-a---     07/11/2022  09:17 a. m.             64   requeriments.txt
```

> NOTA
>
> La carpeta principal en nuestro caso ( Proyecto ) es la encargada de gestionar las apps, esto significa que para poder utilizar una app debemos vincularla en nuestro proyecto principal ( Proyecto )

## Como se estructura una app ?

Cuando creamos una app para el proyecto esta nos viene con sus respectivos archivos de configuración y desarrollo.

```bash
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d----     17/11/2022  07:26 p. m.                  migrations
-a---     17/11/2022  07:26 p. m.              0   __init__.py
-a---     17/11/2022  07:26 p. m.             66   admin.py
-a---     17/11/2022  07:26 p. m.            146   apps.py
-a---     17/11/2022  07:26 p. m.             60   models.py
-a---     17/11/2022  07:26 p. m.             63   tests.py
-a---     17/11/2022  07:26 p. m.             66   views.py
```

> **migrations**
>
> Esta carpeta contendrá los cambios que se harán a la base de datos. contiene un archivo bacio llamado **init**.py.

> **init.py**
>
> Este archivo define si se comportara el proyecto como un modulo de python.

> **admin.py**
>
> Este archivo es un panel de administrador, lo que nos permite es poder crear datos, usuarios o si el usuario tiene algún privilegio se definirá en este archivo.

> apps.py
>
> Es el archivo de configuración de la aplicación, es su equivalente al archivo settings del proyecto principal.

> models.py
>
> En este archivo se pueden crear clases, y al final estas clases creadas se convertirán en tablas de SQL, de esto se encargara Django y las actualizaciones de esta base de datos se guardaran en la carpeta _migrations._

> tests.py
>
> Este archivo nos permite hacer testing de nuestra apps, nos permite poder verificar la lógica de nuestra app.

> views.py
>
> Este archivo es de los mas importantes debido a que ahí es donde se cargara lo que mostraremos en el navegador ( HTML ).

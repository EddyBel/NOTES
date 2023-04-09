---
Completado: Yes
Dificultad: ⭐⭐
Etiquetas: Backend, Express, JavaScript, Server
Fecha: February 2, 2023
---

# Servidor con JavaScript

En este documento se explicará detalladamente cómo montar un servidor con JavaScript. El servidor tendrá una ruta que retorne ciertos datos y mensajes.

## Instalación de Node.js

Lo primero que debemos hacer es instalar [Node.js](https://nodejs.org/es/), el cual es un entorno de ejecución para JavaScript que nos permitirá crear nuestro servidor.

Node.js es un entorno de tiempo de ejecución de JavaScript que se utiliza para construir aplicaciones de servidor. Para instalar Node.js en Windows, macOS y Linux, puedes seguir los siguientes pasos:

- Ve al sitio https://nodejs.org/en/download/ y descarga los archivos binarios necesarios.
- Busca en tu carpeta de descargas el archivo de instalación y haz clic en él para iniciar el proceso de instalación.
- El instalador de Node.js lleva el archivo del núcleo de Node.js y, en consecuencia, el proceso de instalación instala tanto Node.js como npm desde el archivo instalador.
- Haz clic en el botón Instalar para comenzar el proceso de instalación.
- El sistema completará la instalación en unos segundos o minutos y te mostrará un mensaje de éxito.

Una vez descargado e instalado en nuestro equipo, podremos continuar con el siguiente paso.

## Creación del proyecto

Para crear nuestro servidor, debemos crear un nuevo proyecto de Node.js. Para ello, abrimos una terminal y nos ubicamos en la carpeta donde queremos crear el proyecto. Luego, ingresamos el siguiente comando:

```bash
npm init
```

Este comando nos permitirá crear un archivo `package.json`, el cual contendrá la información del proyecto y sus dependencias.

## Instalación de Express

Express es un framework de Node.js que nos permitirá crear nuestro servidor de manera sencilla. Para instalarlo, ingresamos el siguiente comando en la terminal:

```bash
npm install express
```

Este comando instalará Express y lo agregará como una dependencia en nuestro archivo `package.json`.

> Existen varios paquetes similares a Express que puedes utilizar para montar un servidor con JavaScript. Algunos de ellos son:
>
> - Koa.js
> - Hapi.js
> - Restify.js
> - Sails.js
>
> Estos paquetes son frameworks de JavaScript que te permiten crear aplicaciones web y servidores de manera rápida y sencilla, pero lo habitual es usar Express.

## Creación del servidor

Una vez instalado Express, debemos crear nuestro servidor. Para ello, creamos un archivo `server.js` en la raíz del proyecto y agregamos el siguiente código:

```jsx
const express = require("express");
const app = express();

app.get("/api", (req, res) => {
  res.json({ msg: "Hello World" });
});

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
```

Este código importa Express, crea una instancia de la aplicación y define una ruta llamada /api que retorna un JSON con los datos msg: "Hello World". Además, se define el puerto en el que se ejecutará el servidor (5000 en este caso).

- En la primera línea se importa el paquete Express y se guarda en la constante **`express`**.
- En la segunda línea se crea una instancia de Express y se guarda en la constante **`app`**.
- En la tercera línea se define una ruta para el método HTTP GET en la ruta **`/api`**. Cuando un usuario visite esta ruta en el servidor, se ejecutará la función que se encuentra como segundo argumento de **`app.get()`**. Esta función recibe dos argumentos: **`req`** (la solicitud HTTP) y **`res`** (la respuesta HTTP). En este caso, la función simplemente envía una respuesta JSON con el mensaje “Hello World”.
- En la cuarta línea se define una constante llamada **`PORT`** que obtiene su valor de la variable de entorno **`process.env.PORT`**, o 5000 si no hay ninguna variable de entorno definida.
- En la quinta línea se inicia el servidor en el puerto especificado en la constante **`PORT`**. Cuando el servidor esté listo para recibir solicitudes, se ejecutará la función que se encuentra como segundo argumento de **`app.listen()`**. Esta función simplemente imprime un mensaje en la consola indicando que el servidor está corriendo.

## Ejecución del servidor

Para ejecutar el servidor, nos ubicamos en la terminal en la carpeta del proyecto y ingresamos el siguiente comando:

```bash
node server.js
```

Esto iniciará el servidor y nos mostrará en la terminal el mensaje "Server running on port 5000", indicando que el servidor está corriendo en el puerto 5000.

## Prueba del servidor

Para probar nuestro servidor, abrimos un navegador y accedemos a la siguiente dirección `http://localhost:5000/api`.

Esto debería retornarnos un JSON con los datos msg: "Hello World", indicando que nuestro servidor está funcionando correctamente.

¡Listo! Ahora tienes un servidor con JavaScript que tiene una ruta llamada /api que retorna un JSON con los datos msg: "Hello World".

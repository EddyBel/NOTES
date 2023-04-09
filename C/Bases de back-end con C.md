---
Completado: Yes
Dificultad: ⭐⭐⭐
Etiquetas: Backend, C, Conceptos, Rutas, Servidor
Fecha: February 17, 2023
---

# Bases de back-end con C

## Que es el back-end

[El back-end es la parte de una web que no es visible para el usuario y que se encarga de la lógica, la función y el procesamiento de datos](https://devcamp.es/que-es-backend/). [El back-end se ejecuta en el servidor y permite la comunicación con la capa de acceso de datos](https://devcamp.es/que-es-backend/).

## **Seleccione un marco de trabajo (Framework) o biblioteca**

Escribir un back-end completamente desde cero puede ser una tarea muy desalentadora, por lo que es una buena idea usar una biblioteca o un marco de trabajo para ayudar a manejar la mayor parte del trabajo pesado. Algunas opciones populares incluyen:

- **PicoHTTPServer:** Una biblioteca de servidor HTTP en C fácil de usar y rápida.
- **libmicrohttpd:** Una biblioteca de servidor HTTP en C completa y de alto rendimiento.
- **libevent:** Una biblioteca de E/S de red escalable que puede usarse para construir servidores web.
- **mongoose:** Una biblioteca de servidor HTTP en C pequeña y fácil de usar que también es compatible con WebSocket.

En este ejemplo, usaremos PicoHTTPServer para nuestro backend.

## **Crea un archivo principal**

A continuación, crearemos un archivo principal para nuestro servidor web. Este archivo contendrá nuestro punto de entrada y configuración para nuestro servidor web. Aquí hay un ejemplo:

```c

#include "http.h"

static int handle_request(struct http_request *request, struct http_response *response) {
  // Aquí es donde manejará las solicitudes entrantes
}

int main() {
  struct http_server server = {
    .bind_address = "0.0.0.0",
    .port = 8080,
    .handler = handle_request,
  };

  if (http_server_start(&server) != 0) {
    fprintf(stderr, "Error starting HTTP server\n");
    exit(EXIT_FAILURE);
  }

  fprintf(stdout, "HTTP server listening on %s:%d\n", server.bind_address, server.port);
  while (1) {}

  return 0;
}
```

Este código define una función **`handle_request`** que procesa las solicitudes HTTP entrantes y devuelve una respuesta apropiada. La función **`main`** inicializa un servidor HTTP utilizando la biblioteca PicoHTTPServer, establece la dirección de escucha y el puerto, y especifica la función de manejo de solicitudes. Luego, inicia el servidor HTTP y se queda en un ciclo infinito para mantener el servidor en ejecución.

## **Implementa el manejo de solicitudes**

Ahora que hemos configurado nuestro servidor HTTP, necesitamos implementar el manejo de solicitudes en la función **`handle_request`**. Esta función se llamará cada vez que llegue una solicitud a nuestro servidor. Aquí hay un ejemplo simple que responde con un mensaje de texto plano:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#include "http.h"

static int handle_request(struct http_request *request, struct http_response *response) {
  response->status = HTTP_STATUS_OK;
  response->body = strdup("¡Hola desde el servidor!");
  response->body_length = strlen(response->body);

  return 0;
}
```

Este código configura la respuesta con un código de estado HTTP 200 (OK) y un mensaje simple de "¡Hola desde el servidor!".

## **Compila y ejecuta el back-end**

Finalmente, compilamos y ejecutamos nuestro back-end. En este ejemplo, asumimos que el archivo principal se llama **`main.c`** y que estamos usando GCC para compilar:

```bash

gcc -o main main.c http.c
./main
```

Ahora, si abres tu navegador y accedes a **[`http://localhost](http://localhost/):8080`** podrás ver el mensaje ¡Hola desde el servidor!.

Este es un ejemplo rápido de un back-end con C pero puedes desarrollar servidores mas complejos e interesantes.

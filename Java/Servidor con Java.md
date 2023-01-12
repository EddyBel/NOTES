---
Completado: Yes
Dificultad: ⭐⭐⭐
Etiquetas: Ejemplo basico, Intermedio, Java, Server, Servidor, TCP
Fecha: January 7, 2023
---

# Servidor con Java

Para crear un servidor en Java, primero deberá elegir qué protocolo desea utilizar. El protocolo más comúnmente utilizado en aplicaciones de servidor Java es TCP, pero también puede utilizar UDP si es más adecuado para su aplicación.

## Servidor TCP

Para crear un servidor TCP en Java, puede utilizar la clase ServerSocket de la biblioteca estándar de Java. El siguiente es un ejemplo básico de cómo puede utilizar la clase ServerSocket para crear un servidor TCP que escucha en el puerto especificado:

```java
import java.io.*;
import java.net.*;

public class TCPServer {
    public static void main(String[] args) throws IOException {
        // El puerto en el que el servidor escuchará se obtiene del primer argumento de la línea de comando
        int port = Integer.parseInt(args[0]);

        // Creamos un nuevo objeto ServerSocket, especificando el puerto en el que escuchará
        ServerSocket serverSocket = new ServerSocket(port);

        while (true) {
            // El método accept() espera a que se conecte un cliente.
            // Cuando se conecta un cliente, devuelve un nuevo socket para manejar la conexión.
            Socket clientSocket = serverSocket.accept();

            // Aquí deberías escribir el código para manejar la conexión con el cliente
            // Por ejemplo, crear un hilo para manejar la conexión y realizar la lectura y escritura de datos en el socket del cliente
        }
    }
}
```

En este ejemplo, el servidor escucha en el puerto especificado en el primer argumento de la línea de comando y, cuando se conecta un cliente, crea un nuevo socket (clientSocket) para manejar la conexión. El código que se encarga de manejar la conexión del cliente (leer y escribir datos) se encuentra dentro del cuerpo del bucle while (true)

> Es importante tener en cuenta que el código en el bucle while(true) se ejecutará de manera continua, aceptando nuevas conexiones de clientes y manejando cada una de ellas de manera independiente. Es posible que desees agregar mecanismos de control de concurrencia, dependiendo de las necesidades de tu aplicación.

## Servidor UDP

Para un servidor UDP, se utiliza el paquete [java.net](http://java.net/) y la clase DatagramSocket, El siguiente es un ejemplo simple de cómo crear un servidor UDP que escucha en el puerto especificado:

```java
import java.io.*;
import java.net.*;

public class UDPServer {
    public static void main(String[] args) throws IOException {
        int port = Integer.parseInt(args[0]);
        byte[] buffer = new byte[1024];
        DatagramPacket packet = new DatagramPacket(buffer, buffer.length);
        DatagramSocket socket = new DatagramSocket(port);

        while (true) {
            socket.receive(packet);
            // handle packet
        }
    }
}
```

En este ejemplo, el servidor escucha en el puerto especificado en el primer argumento de la línea de comando y, cuando se recibe un paquete, maneja el paquete en el cuerpo del bucle while (true).

---
title: "Test de archivo de markdown"
description: "prueba de mardown"
date: "8/16/2022"
tags: "Test, Markdown, Documento, Prueba"
front: "https://images.pexels.com/photos/12663061/pexels-photo-12663061.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
level: "Medio"
important: true
---

# prueba de contenido

## prueba de contenido

### prueba de contenido

#### prueba de contenido

##### prueba de contenido

###### prueba de contenido

Prueba de textos

lista

- prueba
- prueba dos
- prueba 3

<Underlined words={["texto", "subrallado"]}>
Prueba de texto subrallado
</Underlined>

<Underlined words={["Este es un mensaje subrallado"]}>
Este es un mensaje subrallado
</Underlined>

Texto tachado **EWER**

Prueba de **contenido**

Prueba de _contenido_

prueba de _contenido_

> Primera cita, principal
>
> > Segunda cita anidada
> >
> > > Tercera cita anidada
> > >
> > > > Cuarta cita anidada
>
> Continuacion de la primera cita
>
> > Segunda cita independiente

_Este es un texto subrallado_

```js
const { app, BrowserWindow } = require("electron");
const path = require("path");

function createWindow() {
  const win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      preload: path.join(__dirname, "preload.js"),
    },
  });

  win.loadFile("index.html");
}

app.whenReady().then(() => {
  createWindow();

  app.on("activate", () => {
    if (BrowserWindow.getAllWindows().length === 0) {
      createWindow();
    }
  });
});

app.on("window-all-closed", () => {
  if (process.platform !== "darwin") {
    app.quit();
  }
});
```

![Preview de imagen](https://images.pexels.com/photos/2246476/pexels-photo-2246476.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1)

![Preview imgagen 2](test-document/testIMG.jpg)

```python
import pytube

yt = pytube.YouTube(url)
data = yt.strams.filter(type='video')

console.log(data)

if data:
  print('Hello world')
```

```json
"Main": "main.js",
"Prueba": "prueba"
```

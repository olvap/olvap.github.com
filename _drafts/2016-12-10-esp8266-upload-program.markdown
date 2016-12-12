---
layout: post
title: "Comandos AT Esp8266"
date: 2016-12-10T20:03:13-03:00
category: electrónica
serie: Esp8266
tags:
  - electrónica
  - programables
  - esp8266
---

El esp8266 es un compontente programable que permite la comunicacion
inalambrica. Es un modulo muy barato, cuesta enter 1 y 3 dolares.
Existen varios modelos, pero voy a describir el esp8266-01

![divisor de voltaje](/assets/img/posts/esp8266.jpg)

## Bajando la tarjeta

Manejar los comando AT, puede ser util, pero tambien se puede cambiar
el firmware y usarlo junta al IDE de arduino para tener un mejor
control del modulo.

Para eso hay que agregar las librerias al IDE, y en el menu

archivos -> preferencias

dentro de Gestor de URL de tarjetal hay que agregar:

```
http://arduino.esp8266.com/stable/package_esp8266com_index.json
```

y luego agregar la tarjeta en el gestor de tarjetas.

## Grabando un nuevo firmware

Una vez que la tarjeta esta en el IDE de arduino, podemos grabar casi
cualquier programa de la misma forma que con un arduino cualquiera.

Para esto hay que configurar el ESP en modo grabacion, y esto se
consigue colocando el pin 0 en GRN y el pin 2 a HIGH

![divisor de voltaje](/assets/img/posts/help-esp8266-firmware-update-usbuart.png)

[0]: https://room-15.github.io/blog/2015/03/26/esp8266-at-command-reference/#at-commands 'at commands'

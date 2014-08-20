---
layout: post
title: "Arduino ISP"
date: 2014-05-12 19:59
comments: true
categories: [Arduino, ISP]
published: false
---

Vamos a ver como programar un microcontrolador AtTiny, más precisamente [AtTiny85], usando el IDE de Arduino para escribir el programa y el Arduino como grabador. Esto nos va a permitir guardar progrmas des hasta 6k en el microcotrolador.

Procedimiento

### Grabar el arduino como isp

- Primero tenemos que grabar dentro del Arduino el programa ISP. para eso tenemos que descargar el IDE de arduino y abrirlo(fijate que sea 1.0.4 o superior).
- Seleccionar el programa ArduinoISP de la lista de ejemplos.
- Seleccioná la tarjeta que estás usando, en mi caso, "Arduino Diecimila or Duemilanove w/Atmega168 "
- Seleccioná el programador AVRISPMKII
- Subí el programa en el arduino.

### Hacer las conecciones

![Alt text](http://highlowtech.org/wp-content/uploads/2011/06/Screen-shot-2011-06-06-at-1.46.39-PM.png)

- Pin 2 del ATtiny al Pin 13 del Arduino (o al SCK en otro programador)
- Pin 1 del ATtiny al Pin 12 del Arduino (o al MISO en otro programador)
- Pin 0 del ATtiny al del Pin 11 Arduino (o al MOSI en otro programador)
- Pin de del Reset ATtiny al del Pin 10 Arduino (o al RESET en otro programador)
- Pin 8 del ATtiny a 5v del Arduino
- Pin 4 del ATtiny a tierra del arduino
- Por último poné ucapacitor entre reset y tierra del arduino.

### Copiá el modulo para ATtiny

- Bajate este archivo [atmaster]
- Creá una carpeta "harware" dentro de la carpeta "sketchbook" sino existe.
- Descomprimí el archivo y copiá la carpeta que dice "attiny"
- Si está bien hecho cuando reinicies el arduino vas a ver una serie de tarjetas nuevos en Herramientas > Tarjeta >

### Programa de prueba.
Abrí el ejemplo de Blink, cambiá donde dice que el que pin es el que va a parpadear

Cambía esto
```c++

pinMode(13, OUTPUT);

```

por esto

```c++

pinMode(0, OUTPUT);

```

- Conectá un led con una resisteancia de ~100 oms al pin 5 (PB0) del y tierra
- Cambiá el programador a ArduinoISP
- Cambia la tarjeta por ATtiny85
- Subí el programa.

SI hiciste todo bien, deberías ver como parpadea el led.

Referencias: [http://highlowtech.org/?p=1695](http://highlowtech.org/?p=1695)

[AtTiny85]: http://www.atmel.com/Images/Atmel-2586-AVR-8-bit-Microcontroller-ATtiny25-ATtiny45-ATtiny85_Datasheet.pdf "AtTiny85"

[atmaster]: https://github.com/damellis/attiny/archive/master.zip "attiny master"

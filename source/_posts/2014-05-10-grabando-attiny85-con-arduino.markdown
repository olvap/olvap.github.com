---
layout: post
title: "Grabando AtTiny85 con Arduino"
date: 2014-05-10 16:51
comments: true
categories: Arduino ISP AtTiny85
---

Pasos
------

1. Grabar el arduino como isp
2. Hacer las conecciones
3. Grabar el bootloader en el tiny85
4. Armar el paperduino
5. Programa de prueba

Componentes
- 1 Protoboard
- 1 capacitor de 10 uf
- 1 led rojo
- 1 Arduino due
- 1 Micro AtTiny85
- Cables.

Procedimiento
1. Grabar el arduino como isp

- Run the Arduino development environment.
- Open the ArduinoISP sketch from the examples menu.
- Note for Arduino 1.0: you need to make a small change to the ArduinoISP sketch before uploading it. Find the line in the heartbeat() function that says “delay(40);” and change it to “delay(20);”.
- Select the board and serial port that correspond to your Arduino board.
- Upload the ArduinoISP sketch.

2. Hacer las conecciones

![Alt text](http://highlowtech.org/wp-content/uploads/2011/06/Screen-shot-2011-06-06-at-1.46.39-PM.png)

- ATtiny Pin 2 to Arduino Pin 13 (or SCK of another programmer)
- ATtiny Pin 1 to Arduino Pin 12 (or MISO of another programmer)
- ATtiny Pin 0 to Arduino Pin 11 (or MOSI of another programmer)
- ATtiny Reset Pin to Arduino Pin 10 (or RESET of another programmer)
- 5v
- tierra
- capacitor entre reset y ground

3. Grabar el bootloader en el tiny85

usando avrdude y descargando el archivo.

avrdude -P /dev/ttyUSB0 -c avrisp -b 19200 -p t85 -U flash:w:micronucleus-1.06-upgrade.hex -U lfuse:w:0xe1:m -U hfuse:w:0x5d:m -U efuse:w:0xfe:m

4. armar el paperduino

5. Programa de prueba
bajate el digispark de arduino
(opciones)
pasale el programa de blink

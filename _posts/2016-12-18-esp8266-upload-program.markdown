---
layout: post
title: "Grabando un programa en el Esp8266"
date: 2016-12-18
category: electrónica
serie: Esp8266
tags:
  - electrónica
  - programables
  - esp8266
---

El esp8266 es un componente programable que permite la comunicación
inalámbrica. Es un modulo muy barato, cuesta entre 1 y 3 dolares.
Existen varios modelos, pero voy a describir el esp8266-01

![divisor de voltaje](/assets/img/posts/esp8266.jpg)

## Bajando la tarjeta

Manejar los comando AT es útil, pero a veces es necesario tener un
mayor control de lo que hace el modulo y con los comandos no es suficiente.
Para esto, se puede al igual que con arduino, grabar un nuevo firmware
que haga casi cualquier cosa que se puede hacer con un arduino ademas de
conectarse o generar redes wifi.

Para eso hay que agregar las bibliotecas al IDE, y en el menú

Archivos -> preferencias

Dentro de Gestor de URL de tarjeta hay que agregar:

```
http://arduino.esp8266.com/stable/package_esp8266com_index.json
```

Y luego agregar la tarjeta en el gestor de tarjetas.

## Grabando un nuevo firmware

Una vez que la tarjeta esta en el IDE de arduino, podemos grabar casi
cualquier programa de la misma forma que con un arduino cualquiera.

Para esto hay que configurar el ESP en modo grabación, y esto se
consigue colocando el pin 0 en GRD y el pin 2 a HIGH

![divisor de voltaje](/assets/img/posts/help-esp8266-firmware-update-usbuart.png)

Como ejemplo se puede usar el programa blink, que prende y apaga un pin
cada cierto intervalo. El ejemplo viene preparado para usar el pin13,
pero con el esp, que solo tiene 8 pines, hay que cambiarlo por un numero menor,
como 0.

{% highlight c++ %}
void setup() {
  pinMode(0, OUTPUT);
}

void loop() {
  digitalWrite(0, HIGH);
  delay(1000);
  digitalWrite(0, LOW);
  delay(1000);
}
{% endhighlight %}

Una vez grabado el programa, se desconecta el pin0 a GND y se lo conecta a una
resistencia (220 oms) y a un led. Si todo ha salido bien el pin debería
prenderse y apagarse cada segundo.

![divisor de voltaje](/assets/img/posts/blink_esp.png)

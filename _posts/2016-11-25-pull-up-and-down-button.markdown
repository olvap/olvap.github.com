---
layout: post
title: "Pull Up and Down"
date: 2016-12-01
category: electrónica
tags:
  - electrónica
  - básico
---

Cuando se quiere conectar un botón a un pin de un arduino o un raspberry, un simple switch no es suficiente.
El switch tiene dos estados, cerrado, que deja pasar la corriente y abierto, que no. Se podría pensar que esto es suficiente
para saber si el botón está o no apretado, pero el problema es que cuando está abierto, en realidad el circuito no esta conectado a nada
y queda "flotando". Esto se puede ver como un tercer estado y para el arduino/raspberry podría ser tanto abierto como cerrado.
Para solucionar esto, lo que se puede hacer es forzar que el pin este siempre conectado a Vcc o GND y para esto se pueden usar dos
circuitos llamados, pull up y pull down.

Un circuito pull up se hace conectando uno de los lados del switch a GND y dividiendo el otro lado en dos partes.
Una parte se conecta al pin y la otra se conecta con una resistencia muy grande (10k oms) a Vcc. En su estado normal (cuando no esta apretado)
El pin recibe un estado lógico de HIGH y cuando se oprime el switch, el circuito se cierra a GND y se cambia el estado lógico a LOW.

Un circuito pull down es igual que el pull up, pero se intercambian las posiciones de GND y Vcc, haciendo que el estado normal sea el de LOW.

![voltage regulator](/assets/img/posts/pullupdown.png)

Referencias:

  * [Pull up&down][0]

[0]: https://en.wikipedia.org/wiki/Pull-up_resistor 'pull up&down'

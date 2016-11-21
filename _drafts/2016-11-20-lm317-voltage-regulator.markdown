---
layout: post
title: "Lm317 Voltage Regulator"
date: 2016-11-20T19:22:45-03:00
---

Cuando se tienen dos dispositivos que necesitan distintas cantidades de voltaje, un divisor de voltaje no es suficiente por dos motivos.

Primero cada dispositovo es como una gran resistencia, que afecta el comportamiento del divisor.

Y por otro lado, el voltaje de cada dispositivo puede ser variable.

para solucionar el problema se puede usar un integrado LM317, que es un regulador lineal. El regulador, devuelve una cantidad fija de voltaje aun ucando su entra sea variable.

{% img /images/LM317T.JPG "LM317" %}

En el esquema R2 es una resistencia variable y su valor cambia el valor del voltaje de salida (de 1.2v a 25v).

Para obtener 3.3v en la salida, R2 tiene que valer 340 oms

Nota: mientras mas diferencia alla entre el voltaje de entrada y salida, mayor sera la cantidad de calor que genere el LM317. Si la diferencia es muy grande, se puede llegar a quemar el circuito. Para evitar esto hay que colocar un disipador de calor en el LM317.

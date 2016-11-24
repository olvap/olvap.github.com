---
layout: post
title: "Regulador de voltaje Lm317"
date: 2016-11-24
category: electrónica
tags:
  - electrónica
  - básico
---

Cuando se tienen dos dispositivos que necesitan distintas cantidades de voltaje, un
[divisor de voltaje][0] no es suficiente por dos motivos.

Primero cada dispositivo es como una gran resistencia, que afecta el comportamiento del divisor.

Y por otro lado, el voltaje de cada dispositivo puede ser variable.

Para solucionar el problema se puede usar un integrado [LM317][1], que es un regulador lineal. El regulador, devuelve una cantidad constante de voltaje aun cuando su entrada sea variable.

![voltage regulator](/assets/img/posts/LM317T.JPG)

En el esquema, R2 es una resistencia variable y su valor cambia el valor del voltaje de salida (de 1.2v a 25v).

El cálculo para obtener el voltaje de salida variando las resistencias es:

$$ Vout = 1.25(1 + R1 * R2) + Iadj * R2 $$

> **Ejemplo**
>
> Para obtener 3.3v en la salida, R2 tiene que valer 340 oms

> **Nota:** mientras más diferencia halla entre el voltaje de entrada y salida, mayor será la cantidad de calor que genere el LM317. Si la diferencia es muy grande, se puede llegar a quemar el circuito. Para evitar esto hay que colocar un disipador de calor en el LM317.
{:.note.yellow}

Referencias:

  * [LM317 datasheet][1]

[0]: /electrónica/2016/11/19/divisor-de-voltaje.html 'divisor de voltaje'
[1]: http://www.ti.com/lit/ds/symlink/lm117.pdf 'LM317 datasheet'


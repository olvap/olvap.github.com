---
layout: post
title: "Divisor de Voltaje"
date: 2016-11-19 14:50
comments: true
category: electronica
tags:
  - electronica
  - basico
---

Un divisor de voltaje divide en dos parte el voltaje de una fuente.

Se arma con dos resistencias en serie de Vcc a GND y el voltaje deseado sale en la junta de las resistencias.

El valor de las resistencias regula el valor de salida.

Se puede calcular usando

$$ Vout = V1*R2/(R1+R2) $$

![divisor de voltaje](/assets/img/posts/voltaje_divider.png)

> **Ejemplo:** Obtener 3.3v de una fuente de 5v, R1 = 1000 oms, R2 = 2000 oms.
>
> **Respuesta:**
>
> $$ V1*R2/(R1+R2) = Vout $$
>
> $$ 5*2000/(1000 + 2000) = Vout $$
>
> $$ 10000/3000 = 3.3v $$
{:.paper}

> **Nota:** si las dos resistencias tienen el mismo valor, el voltaje de salida sera la mitad que el voltaje de entrada
{:.note.yellow}

referencias:
* [http://hyperphysics.phy-astr.gsu.edu/hbasees/electric/voldiv.html](http://hyperphysics.phy-astr.gsu.edu/hbasees/electric/voldiv.html)


---
layout: post
title: "Divisor de Voltaje"
date: 2016-11-19 14:50
comments: true
categories: [electronic, pasive]
---

Un divisor de voltaje divide en dos parte el voltaje de una fuente.

Se arma con dos resistencias en serie de Vcc a GND y el voltaje deseado sale en la junta de las resistencias.

El valor de las resistencias regula el valor de salida.

Se puede calcular usando

Vout = V1*R2/(R1+R2)

{% img /images/voltaje_divider.png "Divisor de voltaje" %}

Ejemplo: para obtener 3.3v de una fuente de 5v, R1 = 1000 oms, R2 = 2000 oms.

V1*R2/(R1+R2) = 5*2000/(1000 + 2000) = 10000/3000 = 3.3v


referencias: [voldiv](http://hyperphysics.phy-astr.gsu.edu/hbasees/electric/voldiv.html)


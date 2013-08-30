---
layout: post
title: "Agregando un Disco"
date: 2013-08-29 15:16
comments: true
categories: [basic, HD]
---

Vamos a agregar un disco a nuestro Raspberry, a decir verdad, no es distinto a agregar un disco en cualquier linux, pero con pequeñas diferencias.
Lo primero que tenemos que saber es que al conectar cualquier dispositivo USB al Raspberry, tenemos que saber cuantos ampers va a consumir. El Raspberry necesita 500 ma y dependiendo del disco probablemente necesites otros 500 para este.
Para solucinar esto tenes varias opciones, la más simple, es tener el suficiente amperaje en el transformador del Raspberry, pero tambien, podemos conectar el disco rígido con su propia fuente de energía.
La solución que más me gusto, dado que mi disco rígido no tiene para conectar fuentes de energía, fué comprar un Power Usb, que no es mas que un hub que se enchufa a la red eléctrica y se encarga de proveer a cada puerto con 5V y 500ma.

**Nota:** Si cada tanto el disco rígido se "desconecta" sobre todo cuando tenés conectado más de un puerto USB, es muy probable que no estés usando suficiente amperaje.

Repasado todo esto, conectamos el disco al raspberry en lo encendemos.

link a la [ip estatica](/blog/2013/08/29/ip-estatica/)

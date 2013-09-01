---
layout: post
title: "Agregando un Disco"
date: 2013-09-01 15:16
comments: true
categories: [básico, HD]
published: true
---

Vamos a agregar un disco a nuestro Raspberry, a decir verdad, no es distinto a agregar un disco en cualquier linux, pero con pequeñas diferencias.
Lo primero que tenemos que saber es que al conectar cualquier dispositivo USB al Raspberry, tenemos que saber cuantos amperes va a consumir. El Raspberry necesita 500 ma y dependiendo del disco probablemente necesites otros 500 para este.
Para solucionar esto tenemos varias opciones, la más simple, es tener el suficiente amperaje en el transformador del Raspberry, pero también, podemos conectar el disco rígido con su propia fuente de energía.
La solución que más me gusto, dado que mi disco rígido no tiene para conectar fuentes de energía, fué comprar un Power Usb, que no es más que un hub que se conecta a la red eléctrica y se encarga de proveer a cada puerto con 5V y 500ma.

**Nota:** Si cada tanto el disco rígido se "desconecta" sobre todo cuando tenés conectado más de un puerto USB, es muy probable que no estés usando suficiente amperaje.

Repasado todo esto, conectamos el disco al raspberry en lo encendemos.

creamos un directorio para montar el disco

```
cd /media/
sudo mkdir usbhdd
```

Ahora editamos el archivo fstab y le agregamos un línea para que monte el disco en el inicio.

```
sudo nano /etc/fstab
```

agregamos al final.

```
/dev/sda1    /media/usbhdd    ext4    defaults      0      0
```

Al reiniciar el Raspberry el disco debería estar montado.

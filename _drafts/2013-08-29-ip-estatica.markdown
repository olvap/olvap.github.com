---
layout: post
title: "IP Estática"
date: 2013-08-29 11:24
comments: true
share: true
categories: [básico]
---

Hacer que el Raspberry tenga un IP estática, es igual que con cualquier otro linux, así que los pasos vas a ser similares.

Lo primero que tenemos que hacer es abrir el archivo de interfaces, usando nano.(nano viene instalado, pero es lo mismo cualquier editor.)

```
$ sudo nano /etc/network/interfaces
```

cambia esta linea.

```
iface eth0 inet dhcp
```

Por esta otra.

```
iface eth0 inet static
```

Debajo escribimos la dirección que queremos ponerle.

```
address 192.168.0.100
netmask 255.255.255.0
network 192.168.100.0
broadcast 192.168.0.255
gateway 192.168.0.254
```

Ahora reiniciamos, para que los cambios se apliquen

```
$ sudo reboot
```

Cuando inicie miramos en el ifconfig

```
$ ifconfig
```

Tenemos que ver algo como esto

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.0.0.10
netmask 255.255.255.0
gateway 10.0.0.1
```

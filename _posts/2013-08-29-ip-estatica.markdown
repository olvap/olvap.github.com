---
layout: post
title: "IP Estática"
date: 2013-08-29 11:24
category: linux
serie: Raspberry
tags:
  - linux
  - IP
---

Quiero emular el uso de un servicio como dropbox usando el raspberry y poder
acceder del mismo modo que cualquier otra carpeta de la computadora. Normalmente
el raspberry mantiene la misma IP, pero al no tener una IP fija, puede que
ocasionalmente cambie y buscar cada vez la IP cuando lo que querés es bajar o
subir un archivo es un poco molesto.

Mantener el raspberry con una IP estática, es igual que con cualquier otra
distribución de Linux.

Para saber cual es la configuración actual podemos usar

{% highlight bash %}
$ ifconfig
{% endhighlight %}

Dentro de la salida se vera algo como

{% highlight bash %}
eth0      Link encap:Ethernet  HWaddr b8:27:eb:f0:0b:62
          inet addr:192.168.0.6  Bcast:192.168.0.255  Mask:255.255.255.0
          inet6 addr: fe80::ba27:ebff:fef0:b62/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:1165 errors:0 dropped:0 overruns:0 frame:0
          TX packets:480 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:97054 (94.7 KiB)  TX bytes:52170 (50.9 KiB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

{% endhighlight %}

La primera parte:

eth0      Link encap:Ethernet  HWaddr b8:27:eb:f0:0b:62
          inet addr:192.168.0.6  Bcast:192.168.0.255  Mask:255.255.255.0

Nos dice lo siguiente:

{% highlight bash %}
inet addr – 192.168.0.6 (la IP del raspberry)

Bcast –  192.168.0.255 (El rango de Broadcast)

Mask –  255.255.255.0 (La direccion de mascara de Subnet)
{% endhighlight %}

Y también necesitamos otra información con este otro comando

{% highlight bash %}
$ netstat -nr
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
0.0.0.0         192.168.0.1     0.0.0.0         UG        0 0          0 eth0
0.0.0.0         192.168.0.1     0.0.0.0         UG        0 0          0 eth0
192.168.0.0     0.0.0.0         255.255.255.0   U         0 0          0 eth0
{% endhighlight %}

De acá necesitamos

'Gateway' – 192.168.0.1

'Destination' – 192.168.0.0

Una vez que tenemos toda esta información necesitamos editar el archivo de
interfaces

{% highlight bash %}
$ sudo vim /etc/network/interfaces
{% endhighlight %}

Cambia esta linea.

{% highlight bash %}
iface eth0 inet dhcp
{% endhighlight %}

Por esta otra.

{% highlight bash %}
iface eth0 inet static
{% endhighlight %}

Debajo escribimos la dirección que queremos ponerle. En este caso estoy seteando
la IP fija en 192.168.0.100

{% highlight bash %}
address 192.168.0.100
netmask 255.255.255.0
network 192.168.100.0
broadcast 192.168.0.255
gateway 192.168.0.254
{% endhighlight %}
Mi configuración que da de esta forma

{% highlight bash %}
auto lo
iface lo inet loopback

auto eth0
allow-hotplug eth0
iface eth0 inet static
address 192.168.0.100
gateway 192.168.0.1
netmask 255.255.255.0
network 192.168.0.0
broadcast 192.168.0.255

auto wlan0
allow-hotplug wlan0
iface wlan0 inet manual
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf

auto wlan1
allow-hotplug wlan1
iface wlan1 inet manual
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
{% endhighlight %}

Ahora reiniciamos, para que los cambios se apliquen

{% highlight bash %}
$ sudo reboot
{% endhighlight %}

Cuando inicie miramos en el ifconfig tiene que mostrar la IP que habíamos fijado.

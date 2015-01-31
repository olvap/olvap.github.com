---
layout: post
title: "Instalando Ruby"
date: 2014-01-02 09:11
comments: true
categories: [ruby, rvm]
published: true
---

La mayoría de los sistemas operativos para raspberry, vienen con python instalado, por lo que a la hora de ponernos a programar, saber python es una ventaja. Pero si te gusta ruby acá te explico como hacer.

**Nota:**  si vas a instalar rails, asegurate que la tarjeta SD que estés usando tengas al menos 8 gigas, con 4 te vas a quedar muy corto.

Primero vamos a instalar [RVM][rvm], que es un manejador de versiones para ruby.

```
\curl -sSL https://get.rvm.io | bash -s stable
```

Dependiendo que es lo que necesitas en particular tenés que agregar distintas opciones.
--rails, --ruby o --ruby=1.9.3

Esto nos va a permitir instalar y tener distintas instancias de ruby y si tenemos multiples aplicaciones, podemos tener un set de gemas distintos para cada una.
Podría instalar la última version de ruby agregando la opción --ruby=2.1.0, pero me gusta correrlo por separado, así que en el consola escribo.

```
rvm install 2.1.0
```

Y lo marco para que se use por defecto.

```
rvm --default use 2.1.0
```

Ahora cada ves que abra una terminal se usará la versión 2.1.0.


[rvm]: https://rvm.io/ "RVM"
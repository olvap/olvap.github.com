---
layout: post
title: "Una simple app en Cuba"
date: 2015-02-08 18:48
finished: 2015-02-08 20:26
comments: true
categories: cuba
---

[Cuba] es un mini framework para Ruby. El principal objetivo es mantener el código lo más simple posible.
Otras alternativas como Rails o Sinatra tienden a sobre cargar la aplicación con muchas funcionalidades que no siempre
vamos a usar y por el hecho de tener estás funcionalidades que resuelven muchos problemas que podríamos tener,
estamos contrayendo una **deuda técnica** que nos llena de código innecesario nuestra aplicación.

Por suerte crear una aplicación desde cero en [Cuba] es muy simple y vamos a ver como.

Para comenzar creamos una carpeta para contener nuestra app

```
mkdir app_name
cd app_name
```

Creamos un gemset.
> Hay muchas alternativas para eso, yo estoy usando [RVM], pero es similar en
otras aplicaciones.

Para esto creamos un archivo oculto dentro de la carpeta de la aplicación .ruby-gemset

> el 'punto' al principio del nombre del archivo es importante

[Cuba] no solo es minimalista, sino que también, te alienta serlo. Lo primero que vamos a instalar es [dep].
[Dep][dep] es una gema del mismo creador de Cuba, [soveran] y el objetivo de la gema es administrar las dependencias.

``` ruby
gem install dep
```

Agregamos las dependencias que vamos a usar

```
dep add cuba

```

Una vez que todas las dependencias estén cargadas, podemos decirle a dep que descargue e instale las gemas

```
dep install
```

Suficiente de configuración, ¡vamos a escribir código!.

Como toda primera aplicación vamos a comenzar con un "Hola Mundo"

En el archivo, hola_mundo.rb, escribimos

``` ruby
require 'cuba'               # requerimos la gema cuba

Cuba.define do               # Iniciamos una app Cuba
  on get do                  # pasamos por bloque lo que la app debe hacer con los GET
    on root do               # pasamos otro bloque para definir que hacer en '/'
      res.write 'Hola Mundo' # escribimos el string 'Hola Mundo' es el objecto que vamos a devolver
    end
  end
end
```

Creamos un config.ru para correr la app

``` ruby
require "./hola_mundo"

run Cuba
```

Luego para probarlo corremos

```
rackup config.ru
```
Con tu browser favorito (firefox), entramos a http://localhost:9292, si todo ha salido bien deberías leer 'Hola Mundo'
en la pantalla.

[Cuba]: https://github.com/soveran/cuba
[RVM]: https://rvm.io
[Dep]: https://github.com/cyx/depa
[Soveran]: https://github.com/soveran

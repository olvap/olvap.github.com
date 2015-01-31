---
layout: post
title: "decorator"
date: 2015-01-31 08:57
comments: true
categories: %w(Ruby MVC OOP)
published: false
---

Hace unos días estaba en una entrevista a un aspirante a trabajar en la empresa. Durante la entrevista hacemos
preguntas técnicas y charlamos un rato. Durante la charla le preguntamos sobre el patrón MVC, y si bien la respuesta
no fue, el modelo modela el controlador controla, no me terminó de convencer y entonces le pregunte. ¿Dónde pondrías
un método que modifica un atributo del modelo?. Antes de que me dijeran que me estaba yendo por las ramas, alguien dijo "en un helper"

## Patrón Decorator

Supongamos un modelo simple de una persona

``` ruby

class Persona

  attr_accessor: nombre

end

```

Si queremos mostrar el nombre de la persona, queda claro en MVC que en la vista habría que poner


``` ruby

@persona.nombre

```



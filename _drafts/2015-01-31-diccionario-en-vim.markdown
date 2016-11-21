---
layout: post
title: "Diccionario en vim"
date: 2015-01-31 12:10
comments: true
categories: vim
---

La creatividad a la hora de inventar nuevas formas de escribir una palabra está muy poco valorada estos días.
Como yo soy de lo más creativo, necesito una herramienta que me haga parar un poco.

Para mi sorpresa, vim ya trae un diccionario incluido y es de lo más simple de usar.

Para prender el corrector

```
:set spell

```

Por supuesto para apagarlo.

```
:set nospell

```

Como mucho de lo que escribo está en español, también se puede cambiar el idioma con

```
:set spelllang=es
```
Cuando una palabra no se encuentra en el diccionario, vim, la seleccionará y a partir de ahí, podemos, corregirla, ignorarla
o incluirla en el diccionario (zg).

Para ver la lista de palabras sugeridas basta con usar el comando z= sobre la palabra resaltada.

Para más detalles:

```
:help spell
```

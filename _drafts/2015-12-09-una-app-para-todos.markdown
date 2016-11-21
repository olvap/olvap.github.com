---
layout: post
title: "Una app para todos"
date: 2015-12-09 20:32
comments: true
published: false
categories: TODO
---

Hace mucho tiempo estoy buscando una app para manejar las tareas que se me van ocurriendo. He probado muchas y ninguna
me terminó de convenser así que me decidí hacer una. Si, ya se. Vos también hiciste una o usaste miles de app y no te
acostumbraste a ninguna, así que porque esta seria diferente?

Lo primero que quiero de una todo app es que sea simple, simple de usar, escribir y mantener.

Probé una app en ruby con una base de datos en redis, pero cada vez que quería agregar una nueva funcionalidad, esto se
convertía en un sin fin de espesificaciones innecesarias.

En definitiva lo que quería era una app de consola que me permitiera en cualquier momento invocar a la app y guardar la tarea.
Algo como

$ todo 'leer fundación'

o

$ todo leer_fundación

Y luego algo para listar todas las tareas como:

$ todos
  leer_fundación
  estudiar_inglés
  pasear_al_perro

Y porsupuesto algo para borrarlas o marcarlas como terminadas

Así que pensé en una de las funcionalidades más viejas que conosco de linux. Pensé en el File System.
Cada tarea puede ser un archivo. Si cada tarea está en una carpeta, listar todas las tareas se convierte en listar todos los archivos
de una carpeta. Crear o borrar tareas, significa crear o borrar archivos. Incluso puedo agregar una descripción
simplemente editando el contenido del archivo.

De esta forma

touch aprender_ember # crea una tarea
vim aprender_ember   # agrega una descripción
rm aprender_ember    # termina la tarea
cat aprender_ember   # muestra la descripción
ls                   # Lista todas las tareas

Ahora envolvemos todo esto en una funcion, digamos 't' y usando algunos parametros podemos convertir esto en

t aprender_ember    # crea una tarea si no existe y si existe la muestra
t -e aprender_ember # agrega una descripción y si no existe la crea
t -d aprender_ember # termina la tarea
t                   # Lista todas las tareas

Para hacer categorias imagino que ya te diste cuenta que solo tenés que crear carpetas.

Acá hay una imagen de como se ve.



Y acá está el link de donde bajarlo.

https://github.com/olvap/todos

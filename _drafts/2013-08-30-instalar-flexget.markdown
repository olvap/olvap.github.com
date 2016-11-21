---
layout: post
title: "Instalar Flexget"
date: 2013-09-07 21:27
comments: true
categories: ["Media center", Felxget]
published: true
---

Si necesitas armar un media center, es probable que en algún momento tengas la necesidad de automatizar la descarga de torrents. Para eso vamos a utilizar [FlexGet][flexget].

[FlexGet][flexget] es una herramienta de automatización multipropósito para contenidos tipo torrents, nzbs, podcasts, comics, series, películas, etc.
Puede ser usado con distintos tipos de fuentes tipo RSS-feeds, páginas html, archivos csv, motores de búsqueda e incluso hay plugins para sitios que ni siquiera proveen ninguna clase de feed. Es extremadamente útil en conjunto con aplicaciones que tiene la capacidad de observar un directorio.

Para poder hacer la instalación, necesitamos pip, y para eso escribimos

```
sudo apt-get install python-pip

sudo pip install flexget

```

Para funcionar es necesario escribir un archivo de configuración donde básicamente informamos la url del feed junto con algunas configuraciones extras que queramos adquirir.

Acá hay un ejemplo.


``` yml

tasks:
  rlslog_yify:
    rss: http://yify-torrents.com/rss/0/1080p/All/0
    imdb:
      min_score: 6.1
    download: ~/torrents/

  rlslog_dvdrips:
    rlslog: http://www.rlslog.net/category/movies/dvdrip/
    imdb:
      min_score: 6.1
      min_votes: 5000
      min_year: 2006
      reject_genres:
        - documentary
        - musical
        - music
        - biography
    download: ~/torrents/

  show_rss:
    rss: http://showrss.karmorra.info/rss.php?user_id=136117
    all_series: yes
    download: ~/torrents

```

Para asegurar que el archivo de configuración no tiene ningún problema, podemos correr

```
flexget --test
```

Si estamos usando transmission, podemos cambiar estas propiedades para que miren en el mismo directorio donde flexget baja los torrents

Abrimos la configuración de transmission

```
sudo nano settings.json
```

Cambiamos las propiedades.

```
"watch-dir": "/home/pi/torrents",
"watch-dir-enabled": true
```

Por último podemos agregar el comando de flexget al crontab para que ejecute una vez por hora la búsqueda. No es aconsejable hacerlo más seguido que eso, porque algunos sitios te pueden bloquear la ip si detectan mucho tráfico.

para saber la dirección donde está instalado flexget escribimos

```
which flexget
```

Luego abrimos el crontab

```
crontab -e
```

y agregamos la instrucción.

```
@hourly /usr/local/bin/flexget --cron
```

salvamos y salimos.
[flexget]: http://flexget.com "Flexget"

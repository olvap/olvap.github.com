---
layout: post
title: "Instalar Flexget"
date: 2013-08-30 21:27
comments: true
categories:
published: false
---

python 2.7

If you do not have pip already available, you need to install it.

With Debian based distributions you can simply run with root privileges:

sudo apt-get install python-pip

sudo pip install flexget

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

  iso_hunt:
    rss: http://isohunt.com/js/rss/family+guy+show?iht=
    series:
      - family
    download: ~/torrents

  show_rss:
    rss: http://showrss.karmorra.info/rss.php?user_id=136117&hd=null&proper=1
    all_series: yes
    download: ~/torrents

"watch-dir": "/home/pi/torrents",
"watch-dir-enabled": true

which flexget

crontab -e

@hourly /usr/local/bin/flexget --cron

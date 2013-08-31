---
layout: post
title: "Clinte torrent"
date: 2013-08-30 20:06
comments: true
categories:
published: false
---

sudp apt-get update
sudo apt-get -y install transmission-daemon

cd /etc/transmission-daemon
sudo nano settings.json

“download-dir”: “/media/pendrive/torrents/finish”
“incomplete-dir-enabled”: true
“incomplete-dir”: “/media/pendrive/torrents/tmp”
“rpc-enabled”: true
“rpc-whitelist-enabled”: false,

permisos
sudo nano /etc/init.d/transmission-daemon

sudo service transmission-daemon stop
sudo service transmission-daemon start
sudo service transmission-daemon restart

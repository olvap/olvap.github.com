---
layout: post
title: "IP estatica en Raspbmc"
date: 2013-08-30 19:14
comments: true
categories:
published: false
---


In XBMC, go to Programs → Raspbmc settings → Wired network configuration.
Uncheck the Automatic DHCP option.
Provide a static IP address. Make sure the IP address is far away from the IP addresses typically assigned by the router to the networked devices at home. For example, if a router assigns addresses starting from 192.168.0.10, then pick a static IP like 192.168.0.50
Scroll down and check the Update Now option. Raspbmc will take a few seconds to apply the new configuration.
Make sure you can ping the static IP address you assigned. Voila, your Raspbmc now has a fixed IP address!

---
id: 247
title: Blue smile
date: 2010-07-28T11:57:36+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=247

dsq_thread_id:
  - "1301904241"
categories:
  - KDE Development
---
Yeah ! It is now for real ! We have an integrated Bluetooth system with our desktop. BlueDevil (the new bluetooth stack for KDE) consists of several key features:

  * libbluedevil: a Qt-only based library to handle almost everything Bluetooth related. It contains lots of functionality. It deserves a post for itself 🙂

  * 2 KIOs: bluetooth and obexftp. Former for discovering devices and services. Latter for browsing and doing typical operations over a remote device.

  * 3 KCMs: Devices, Adapters and File Transfer. First one will allow you to configure everything related to your known remote devices. Second one for configuring your adapters (usually you will only have one, but having several adapters is supported here). Third one for configuring where the files being sent over bluetooth will be saved, and to globally enable/disable file transfer.

  * Monolithic application: ala KBluetooth.

It has been a pretty intense work, but it has been fun, and I am really glad of having contributed heavily to this technology. Working in UFO Coders is being a pretty great experience and while being fun and letting me develop for KDE it is also helping out in the task of finishing the University as a grant holder. Spare time now really reduced to -24 hours.

We expect bugs, and that is pretty much the point of the RC1. We want to fix &#8217;em all !
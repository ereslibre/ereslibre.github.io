---
id: 45
title: New shiny features for KPluginSelector
date: 2007-05-14T02:38:45+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=45

enclosure:
  - |
    http://media.ereslibre.es/2007/05/kpluginselector3.mpeg
    20666022
    video/mpeg

dsq_thread_id:
  - "1301901406"
categories:
  - archived
  - kde
---
Yay !! I <a href="http://media.ereslibre.es/2007/05/kpluginselector3.mpeg" target="_blank">recorded another video to show how KPluginSelector tells the user about automatically (un)checked items because of dependencies</a>, as some people suggested me. It was really needed.

KPluginSelector base features are almost finished, and ready-to-commit, despite the KStyle based code to draw categories. That&#8217;s a minor thing, since I can comment it and draw categories as normal items for now, or whatever. It seems there is a better way to implement the category drawing on KStyle (through a static method), after a talk with SadEagle and fredrikh. That solutions seems pretty nice, and I really like it, since the fallback (on the case we have a QStyle) is on that method.

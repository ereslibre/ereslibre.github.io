---
title: New shiny features for KPluginSelector
author: ereslibre
layout: post
enclosure:
  - |
    |
        http://media.ereslibre.es/2007/05/kpluginselector3.mpeg
        20666022
        video/mpeg
        
categories: kde
---
Yay !! I [recorded another video to show how KPluginSelector tells the user about automatically (un)checked items because of dependencies][1], as some people suggested me. It was really needed.

 [1]: http://media.ereslibre.es/2007/05/kpluginselector3.mpeg

KPluginSelector base features are almost finished, and ready-to-commit, despite the KStyle based code to draw categories. That’s a minor thing, since I can comment it and draw categories as normal items for now, or whatever. It seems there is a better way to implement the category drawing on KStyle (through a static method), after a talk with SadEagle and fredrikh. That solutions seems pretty nice, and I really like it, since the fallback (on the case we have a QStyle) is on that method.

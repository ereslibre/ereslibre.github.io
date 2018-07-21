---
id: 152
title: Fixing is not everything
date: 2008-08-28T01:33:36+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=152

dsq_thread_id:
  - "1301904045"
categories:
  - archived
  - kde
---
I have just committed a speed fix for KFadeWidgetEffect. We do use very often the method setOpacity() which results to be really slow on current QPainter (we really hope this will be fixed on new versions of Qt). You can read <a href="http://techbase.kde.org/Development/Tutorials/Graphics/Performance" target="_blank">this techbase tutorial</a>, written by <a href="http://fredrikh.blogspot.com/" target="_blank">Fredrik Höglund</a>, you will learn a lot about the dark side of QPainter, and how to avoid the more general cases that we usually face.

I opposed of adding this fade in / fade out effect to page dialogs when this class was introduced because when the screen was maximized the performance was plain painful. Now that this code from KFileItemDelegate has been borrowed by KFadeWidgetEffect we can do fast blending, and I made the page dialogs blend their pages.

The <a href="http://media.ereslibre.es/2008/08/paged-blending.ogg" target="_blank">resulting video is the next one</a>.

PS: This is not in KDE 4.1.

PS2: It will be possible to disable this effect from the style (probably) KCM from SystemSettings.

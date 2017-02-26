---
id: 103
title: KPluginSelector internally renewed
date: 2008-05-15T15:59:27+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=103

dsq_thread_id:
  - "1301902556"
categories:
  - KDE Development
---
After having ported KPluginSelector to use Goya for showing the widgets it needs to show on the item view, I have worked on removing all unneeded stuff. The code is amazingly more clear now and it now sorts plugins alphabetically. Less code lines, and more features: it can search through the search box on the top. Nowadays this is a must, since it seems plugins are going to appear everywhere 🙂 KWin, Kopete, Konqueror have a good number of plugins. And more to come&#8230;

Since lots of users suggested before that rows were very high, now I made them be less tall. I guess this improves visibility, since you can see more plugins with a fast sight.

So, you can [find the patch here](http://media.ereslibre.es/2008/05/kdelibs-kpluginselector.diff). Some screenshots:

<p align="center">
  <a href="http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite.png" target="_blank"><img src="http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite.png" width="320" border="0" height="240" /></a>
</p>

<p align="center">
  <a href="http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite1.png" target="_blank"><img src="http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite1.png" width="320" border="0" height="240" /></a>
</p>

<p align="center">
  <a href="http://media.ereslibre.es/2008/05/kpluginselector-new-kopete.png" target="_blank"><img src="http://media.ereslibre.es/2008/05/kpluginselector-new-kopete.png" width="320" border="0" height="240" /></a>
</p>

<p align="left">
  This is very probably (almost for sure) going for 4.2 series.
</p>
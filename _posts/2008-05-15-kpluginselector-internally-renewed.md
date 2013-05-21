---
title: KPluginSelector internally renewed
author: ereslibre
layout: post
categories: kde
---
After having ported KPluginSelector to use Goya for showing the widgets it needs to show on the item view, I have worked on removing all unneeded stuff. The code is amazingly more clear now and it now sorts plugins alphabetically. Less code lines, and more features: it can search through the search box on the top. Nowadays this is a must, since it seems plugins are going to appear everywhere ![:)][1] KWin, Kopete, Konqueror have a good number of plugins. And more to come…

 [1]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

Since lots of users suggested before that rows were very high, now I made them be less tall. I guess this improves visibility, since you can see more plugins with a fast sight.

So, you can [find the patch here][2]. Some screenshots:

 [2]: http://media.ereslibre.es/2008/05/kdelibs-kpluginselector.diff

[![][4]][4]

 []: http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite.png
 [4]: http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite.png

[![][6]][6]

 []: http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite1.png
 [6]: http://media.ereslibre.es/2008/05/kpluginselector-new-kwrite1.png

[![][8]][8]

 []: http://media.ereslibre.es/2008/05/kpluginselector-new-kopete.png
 [8]: http://media.ereslibre.es/2008/05/kpluginselector-new-kopete.png

This is very probably (almost for sure) going for 4.2 series.

---
id: 134
title: Hover it, my friend !
date: 2008-08-03T14:39:56+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=134

dsq_thread_id:
  - "1301904069"
categories:
  - KDE Development
---
So as some of you suggested (and the maintainer of the places view Kévin) I am giving a try to the show-capacity-bar-on-hover approach, and I really like it, for being honest.

It is great to see that discoverability is not a problem anymore, since you always need to click on the device, so if it is mounted and you are going to click, you will see very fast the capacity bar.

Plus, this also makes it possible to only poll if one device is hovered and only that device (I will have to also check for keyboard navigation, so probably we will have to show it too when it has the keyboard focus, but that are minor improvements that can be easily done).

Also, I modified the capacitybar for having less rounded borders. I really believe now it behaves really well when it is big and small, but still rounded borders.

<a href="http://media.ereslibre.es/2008/08/capacitybarfileplaces.ogg" target="_blank">I recorded a small video of making use of the show the bar on hover</a>, just to let you know how this is progressing.

<a href="http://media.ereslibre.es/2008/08/kdelibs-fileplaces.diff" target="_blank">You can try the patch here too</a>&#8230;

Comments ? Suggestions ?
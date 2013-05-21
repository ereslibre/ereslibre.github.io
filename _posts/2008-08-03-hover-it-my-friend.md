---
title: Hover it, my friend !
author: ereslibre
layout: post
categories: kde
---
So as some of you suggested (and the maintainer of the places view Kévin) I am giving a try to the show-capacity-bar-on-hover approach, and I really like it, for being honest.

It is great to see that discoverability is not a problem anymore, since you always need to click on the device, so if it is mounted and you are going to click, you will see very fast the capacity bar.

Plus, this also makes it possible to only poll if one device is hovered and only that device (I will have to also check for keyboard navigation, so probably we will have to show it too when it has the keyboard focus, but that are minor improvements that can be easily done).

Also, I modified the capacitybar for having less rounded borders. I really believe now it behaves really well when it is big and small, but still rounded borders.

[I recorded a small video of making use of the show the bar on hover][1], just to let you know how this is progressing.

 [1]: http://media.ereslibre.es/2008/08/capacitybarfileplaces.ogg

[You can try the patch here too][2]…

 [2]: http://media.ereslibre.es/2008/08/kdelibs-fileplaces.diff

Comments ? Suggestions ?

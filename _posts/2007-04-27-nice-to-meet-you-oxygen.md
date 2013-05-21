---
title: Nice to meet you Oxygen
author: ereslibre
layout: post
categories: kde
---
I have had some hack at Oxygen style. This all was for allowing Oxygen draw custom categories at KListView. My proposal is this one:

[![][2]][2]

 []: http://media.ereslibre.es/2007/04/klistview.png
 [2]: http://media.ereslibre.es/2007/04/klistview.png

Of course, here you can find the patches for [kdelibs][3], and for [oxygen style][4].

 [3]: http://media.ereslibre.es/2007/04/kdelibs1.diff
 [4]: http://media.ereslibre.es/2007/04/oxygen.diff

I removed some hard coded values that had the previous version and that were just for testing reasons. I still need to handle properly the sizeFromContents method.

If you have any comments or suggestions feel free to contact me.

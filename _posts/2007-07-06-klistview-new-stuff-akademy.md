---
title: KListView new stuff
author: ereslibre
layout: post
categories: kde
---
This took me sooooo long. I thought I was going to finish this much faster, but is OK now, and working pretty nice.

I managed to make KListView being capable of drawing categories as we want (so you can override how categories are drawn depending on which role is being used and so on…). That was on Monday.

From monday till now I have been in some kind of hell with the keyboard navigation, but is just now finished. It took me so much long than expected because of the three indexes involved (source, general sorting and category sorting).

[![][2]][2]

 []: http://media.ereslibre.es/2007/07/klistviewsortbytype.png
 [2]: http://media.ereslibre.es/2007/07/klistviewsortbytype.png

[![][4]][4]

 []: http://media.ereslibre.es/2007/07/klistviewsortbyowner.png
 [4]: http://media.ereslibre.es/2007/07/klistviewsortbyowner.png

[![][6]][6]

 []: http://media.ereslibre.es/2007/07/klistviewsortbyrating.png
 [6]: http://media.ereslibre.es/2007/07/klistviewsortbyrating.png

Now I’m going to name this class KCategorizedView. It seems a good name. If you propose better names, we can always study the possibility of changing it, since it is not on kdelibs yet (and won’t be on a short time I think), so is worth to think about the best name for it.

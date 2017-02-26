---
id: 54
title: KListView new stuff
date: 2007-07-06T19:03:05+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=54

dsq_thread_id:
  - "1301901981"
categories:
  - KDE Development
---
This took me sooooo long. I thought I was going to finish this much faster, but is OK now, and working pretty nice.

I managed to make KListView being capable of drawing categories as we want (so you can override how categories are drawn depending on which role is being used and so on&#8230;). That was on Monday.

From monday till now I have been in some kind of hell with the keyboard navigation, but is just now finished. It took me so much long than expected because of the three indexes involved (source, general sorting and category sorting).

<p align="center">
  <a href="http://media.ereslibre.es/2007/07/klistviewsortbytype.png" target="_blank"><img src="http://media.ereslibre.es/2007/07/klistviewsortbytype.png" border="0" height="240" width="320" /></a>
</p>

<p align="center">
  <a href="http://media.ereslibre.es/2007/07/klistviewsortbyowner.png" target="_blank"><img src="http://media.ereslibre.es/2007/07/klistviewsortbyowner.png" border="0" height="240" width="320" /></a>
</p>

<p align="center">
  <a href="http://media.ereslibre.es/2007/07/klistviewsortbyrating.png" target="_blank"><img src="http://media.ereslibre.es/2007/07/klistviewsortbyrating.png" border="0" height="240" width="320" /></a>
</p>

Now I&#8217;m going to name this class KCategorizedView. It seems a good name. If you propose better names, we can always study the possibility of changing it, since it is not on kdelibs yet (and won&#8217;t be on a short time I think), so is worth to think about the best name for it.
---
id: 35
title: Nice to meet you Oxygen
date: 2007-04-27T21:09:25+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=35

dsq_thread_id:
  - "1301901194"
categories:
  - KDE Development
---
I have had some hack at Oxygen style. This all was for allowing Oxygen draw custom categories at KListView. My proposal is this one:

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/klistview.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/klistview.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

Of course, here you can find the patches for <a target="_blank" href="http://media.ereslibre.es/2007/04/kdelibs1.diff">kdelibs</a>, and for <a target="_blank" href="http://media.ereslibre.es/2007/04/oxygen.diff">oxygen style</a>.

I removed some hard coded values that had the previous version and that were just for testing reasons. I still need to handle properly the sizeFromContents method.

If you have any comments or suggestions feel free to contact me.
---
id: 100
title: Final approach ?
date: 2008-04-29T02:49:53+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=100

dsq_thread_id:
  - "1301903413"
categories:
  - KDE Development
---
On the very previous post I was suggested to create a dot story and poll there people with this question. Well, I don&#8217;t know if this could be a &#8220;dot story&#8221; 🙂

I guess this time I got to a final approach (on what the &#8220;continuous bar&#8221; is concerned). I added another gradient (vertical) so it doesn&#8217;t look so 90&#8217;s. I used KColorScheme and QPalette to correctly use colors, and it seems I get good results with all the color schemes I have on KDE 4.

Maybe a border to clearly mark where the widget starts and where ends.

Nuno Pinheiro had given me some input on how to draw a nicer approach. This is the one I like most 🙂 He told me to use a solid color for the capability bar itself, but after trying the green-to-red gradient I just couldn&#8217;t resist to it.

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog17.png" width="390" border="0" height="497" />
</p>

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog18.png" width="390" border="0" height="497" />
</p>

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog19.png" width="390" border="0" height="497" />
</p>

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog20.png" width="390" border="0" height="497" />
</p>

<p align="left">
  The widget design is based (really, fast based) <a href="http://media.ereslibre.es/2008/04/progresscontinuous.svg" target="_blank">on the mockup Nuno did tonight for me</a> :). Thank you very much Nuno. I really like the shape this widget is taking. 🙂
</p>
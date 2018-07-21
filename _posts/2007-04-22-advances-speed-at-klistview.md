---
id: 31
title: 'Advances: speed at KListView'
date: 2007-04-22T06:38:54+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=31

dsq_thread_id:
  - "1301900942"
categories:
  - archived
  - kde
---
After couple weeks with no time for KDE, I have been able to do some work at KListView (or however it will be called at the end). You can check this screenshot to see how it goes:

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/categorization4.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/categorization4.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

I have increased the speed of the math that looks for each item place. There is still lots of work needed, but I think with some time it is going the right way.

I would really like to see if we can have some kind of &#8220;integration&#8221; with KStyle. It would be really nice to see how the categorization drawing changes if you have this or that style on KDE, and it would be really nice to see item joinings, since is the view the one that checks all that&#8230; and is what I&#8217;m writing&#8230; so we have some help on that. I will have to give a look to KStyle when improving some things that still need to&#8230; the intersectionSet method still stinks, but what I have seen is that it is fast for models > 500 elements, but I need to write a test to really check when it gets slow. I think it will &#8220;fly-off the road&#8221; when having a fast implementation of intersectionSet.

**Update:**

After the strong critic at comment #3, I want to point out something. Probably having ellipses is totally ugly, but my point was only to show that a category is not only a text, that if we make it come with the style, it can be fully customizable by the style. For that reason I have been told on IRC how to make a better screenshot, so there you go:

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/categorization5.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/categorization5.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

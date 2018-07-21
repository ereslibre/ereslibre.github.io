---
id: 98
title: Capacity bars in properties dialogs
date: 2008-04-28T02:17:49+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=98

dsq_thread_id:
  - "1301903116"
categories:
  - archived
  - kde
---
Hi all,

I have been hacking on the ideas I got from people on the previous post + mailing lists. I am pretty happy with the results I have got so far:

This is how my properties dialog looks showing the actual device usage level:

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog12.png" width="446" border="0" height="500" />
</p>

Since I have a pretty small amount of hard disk used, I have taken some shots with the percent hardcoded at 95%. I only have one problem at the moment: I need to think (ideas are welcome) how text can be drawn to correctly be seen even when the capacity bar is below the text:

The first screenshot shows the capacity bar with &#8220;fill full blocks&#8221; enabled, while on the second it is disabled. When disabled, this property would let the last block to have a different width than the rest if the percent is a certain one.

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog13.png" width="448" border="0" height="500" />
</p>

<p align="center">
  <img src="http://media.ereslibre.es/2008/04/kpropertiesdialog14.png" width="448" border="0" height="500" />
</p>

<p align="left">
  Apart  from improving the general appearance of the capacity bar, I think it would be great to make each block that goes to a higher percent more red. Maybe starting on green, and going through yellow. I will play with that tomorrow, I guess 🙂
</p>

<p align="left">
  Comments ? Ideas ? Suggestions ?
</p>

<p align="center">
  &nbsp;
</p>

---
id: 130
title: Capacity bars on places view
date: 2008-07-31T11:30:15+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=130

dsq_thread_id:
  - "1301903843"
categories:
  - KDE Development
---
I am working on making a cool way of notifying the user about the external devices usage in a very slight way. Note that this screenshots are a work in progress, and can change to what we will have in trunk (nothing is committed yet).

The idea is to show the user the disk usage for external devices implicitly into the places view (so it is shown on Dolphin, open/save dialogs&#8230;). Also, a tooltip with further information and numbers will be provided where a capacity bar is shown (in this example, if you held your mouse on the &#8220;ERESLIBRE&#8221; row, which is how my pendrive is called).

We have to discuss yet if the capacity bar should be always shown or it should be shown only on hover, or even only on the tooltip and never be drawn on the places view.

Here are the screenshots of what I have at the moment:

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/07/dolphinPlacesView.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/07/dolphinPlacesView.png" alt="" width="320" height="200" /></a>
</p>

<p style="text-align: center;">
  (Dolphin with the places view at the left)
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/07/kwritePlacesView.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/07/kwritePlacesView.png" alt="" width="320" height="200" /></a>
</p>

<p style="text-align: center;">
  (KWrite showing the open/save dialog with the places view at the left)
</p>

<p style="text-align: left;">
  So, what do you think ? 😉
</p>
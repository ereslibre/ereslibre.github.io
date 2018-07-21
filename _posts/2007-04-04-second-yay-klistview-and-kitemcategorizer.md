---
id: 24
title: 'Second YAY ! [KListView and KItemCategorizer]'
date: 2007-04-04T07:21:16+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=24

dsq_thread_id:
  - "1301900784"
categories:
  - archived
  - kde
---
I have been hacking at night to write two new classes, that I hope will be useful to users, since I know from various users that this was a missed feature on our KDE file managers.

The idea is having QListView categorized, so having a model that allows sorting, KListView will categorize items. Everything is up to the developer, since the categorizing is done by a class named KItemCategorizer, what is an interface really.

The current patch I have is <a target="_blank" href="http://media.ereslibre.es/2007/04/kdelibs.diff">this one</a>, but I&#8217;m still hacking on it, so it is nothing &#8220;for sure&#8221;. I know there are lots of things that can be polished, and the most important ones that I want to are: (a) Speeding-up of some methods, I think some of them are not good in time (b) Giving support for right-to-left languages.

I hope (a) won&#8217;t become a hell, but needs some thinking, and I really think (b) is trivial.

If you are curious you just can try to apply the patch, since it works pretty nice until you try to select a set of items, that is something in what I have to work right now 🙂

My first try (just for testing) was this screenshot:

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/categorization.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/categorization.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

The patch that you can read on this entry blog goes with this screenshot (with few changes on Dolphin&#8217;s code, maybe 5 lines or so):

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/categorization2.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/categorization2.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

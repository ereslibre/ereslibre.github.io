---
title: 'Second YAY ! [KListView and KItemCategorizer]'
author: ereslibre
layout: post
categories: kde
---
I have been hacking at night to write two new classes, that I hope will be useful to users, since I know from various users that this was a missed feature on our KDE file managers.

The idea is having QListView categorized, so having a model that allows sorting, KListView will categorize items. Everything is up to the developer, since the categorizing is done by a class named KItemCategorizer, what is an interface really.

The current patch I have is [this one][1], but I’m still hacking on it, so it is nothing “for sure”. I know there are lots of things that can be polished, and the most important ones that I want to are: (a) Speeding-up of some methods, I think some of them are not good in time (b) Giving support for right-to-left languages.

 [1]: http://media.ereslibre.es/2007/04/kdelibs.diff

I hope (a) won’t become a hell, but needs some thinking, and I really think (b) is trivial.

If you are curious you just can try to apply the patch, since it works pretty nice until you try to select a set of items, that is something in what I have to work right now ![:)][2] 

 [2]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

My first try (just for testing) was this screenshot:

[![][4]][4]

 []: http://media.ereslibre.es/2007/04/categorization.png
 [4]: http://media.ereslibre.es/2007/04/categorization.png

The patch that you can read on this entry blog goes with this screenshot (with few changes on Dolphin’s code, maybe 5 lines or so):

[![][6]][6]

 []: http://media.ereslibre.es/2007/04/categorization2.png
 [6]: http://media.ereslibre.es/2007/04/categorization2.png

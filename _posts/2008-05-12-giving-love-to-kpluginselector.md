---
title: Giving love to KPluginSelector
author: ereslibre
layout: post
categories: kde
---
There was a TODO on KPluginSelector. Internally is a beautiful mess. Is where you had to add some widgets inside itemviews and there was no “right way” of doing it. Since Goya will be probably moved to kdelibs this friday if everything goes OK, I recalled this TODO and have started to rewrite it. Very few code has been saved from the old version. Right now this has a very more useful face: plugins are sorted by title name, and you can actually filter with the search box that is above the list view. It also uses KCategorizedView. After Goya is moved into kdelibs, I will make the buttons come again, but using this library. This is all in my hard disk yet… so there is no public place where you can see it, but is amazing how the code has become this simple… You can take a look at couple shots:

Here you can see how plugins are automatically sorted by name:

[![][2]][2]

 []: http://media.ereslibre.es/2008/05/kpluginselector-kwrite.png
 [2]: http://media.ereslibre.es/2008/05/kpluginselector-kwrite.png

And in this screenshot you can see the filtering working:

 [![][4]][4]

 []: http://media.ereslibre.es/2008/05/kpluginselector-kopete.png
 [4]: http://media.ereslibre.es/2008/05/kpluginselector-kopete.png

I hope this change will come for 4.2 version. There are no chances of 4.1 can come with this improvement before you ask me =)

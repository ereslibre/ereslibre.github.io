---
id: 102
title: Giving love to KPluginSelector
date: 2008-05-12T00:05:28+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=102

dsq_thread_id:
  - "1301900877"
categories:
  - Archived
  - KDE Development
---
There was a TODO on KPluginSelector. Internally is a beautiful mess. Is where you had to add some widgets inside itemviews and there was no &#8220;right way&#8221; of doing it. Since Goya will be probably moved to kdelibs this friday if everything goes OK, I recalled this TODO and have started to rewrite it. Very few code has been saved from the old version. Right now this has a very more useful face: plugins are sorted by title name, and you can actually filter with the search box that is above the list view. It also uses KCategorizedView. After Goya is moved into kdelibs, I will make the buttons come again, but using this library. This is all in my hard disk yet&#8230; so there is no public place where you can see it, but is amazing how the code has become this simple&#8230; You can take a look at couple shots:

Here you can see how plugins are automatically sorted by name:

<p style="text-align: center">
  <a href="http://media.ereslibre.es/2008/05/kpluginselector-kwrite.png" target="_blank"><img src="http://media.ereslibre.es/2008/05/kpluginselector-kwrite.png" width="320" border="0" height="240" /></a>
</p>

<p align="left">
  And in this screenshot you can see the filtering working:
</p>

<p align="center">
   <a href="http://media.ereslibre.es/2008/05/kpluginselector-kopete.png" target="_blank"><img src="http://media.ereslibre.es/2008/05/kpluginselector-kopete.png" width="320" border="0" height="240" /></a>
</p>

<p align="left">
  I hope this change will come for 4.2 version. There are no chances of 4.1 can come with this improvement before you ask me =)
</p>

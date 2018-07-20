---
id: 63
title: 'KCategorizedView: ready, set, GO !!'
date: 2007-09-17T08:34:32+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=63

dsq_thread_id:
  - "1301902458"
categories:
  - Archived
  - KDE Development
---
Finally&#8230; after all the related stuff that needed to be reworked I applied the huge patch to Dolphin that made KCategorizedView cleaner, as well as in general how data is treated on Dolphin. Now categories are asked to the model (a new model created for that purpose: DolphinModel, inheriting KDirModel).

In theory no visual stuff has been affected in any way, but I wanted to add a small jewel with this commits&#8230; a visual feedback when the user clicks on a category for selecting the items.

As usual, I have recorded a [small video that shows the behaviour](http://media.ereslibre.es/2007/09/dolphin.ogg).

As a TODO for KCategorizedView I only have the keyboard navigation (and that should be really really easy in comparation with the old implementation).

When this TODO is completed there are lots of work to do yet&#8230; a small surprise on the properties dialog of Dolphin, some Kopete config dialog plugins reworking (hey ! I saw lots of them were pretty fixed, you guys rock :P), the work on Plasma I still want to do&#8230; So many things and days still with 24 hours.

I will also work on the permissions sorting as well as drawing. I think I have the idea of how to do this&#8230; and I will wait for your feedback when blogging about it 🙂

I also want to investigate on how could we create a common accesibility as well as &#8220;widgeting&#8221; on delegates. If you have worked with delegates you will have found that introducing user interaction is just hell&#8230; There is more&#8230; when talking about visually handicapped people or other problems, they are not very good for applications that will try to read the screen. That added to the problem of the interaction with controls itself. I will try to investigate in this direction, and see if we could create some kind of layer between the delegate and the view, that makes this interaction / accesibility issues very easy.

To sum up, I&#8217;m hell glad of seeing this on SVN instead of only on my local copy. This has been a lot of work, but of course, it was worth it. Happiness 🙂

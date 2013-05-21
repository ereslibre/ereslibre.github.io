---
title: 'Concurrent programming&#8230; err&#8230; thinking'
author: ereslibre
layout: post
categories: kde
---
I guess all of us have felt this thing at some point. We have tons of projects, we want all them become true, and days are still having 24 hours. Apart from the typical bugfixing where we see bugs and we try to fix them (what also takes time), I am working on several things at the moment:

*   KUIServer (what will be hopefully called JobViewServer): I have this interface and implementation finished [thanks to everybody that made suggestions, specially to Kevin for his tips]. The idea is to get this feature into KDE 4.1, have it well tested, and afterwards, write a paper to freedesktop to see if we can make it standard. I really bet for this to become standard because of several reasons, one of the most important: simplicity.
*   Goya: I would love to get this into KDE 4.1 also. Right now a branch has been created to go deeper into the strategy that WoC (Widgets on Canvas) uses on QGraphicsView, but applied to MVC. This way we would expose less API, and it would be simpler to use, and what is more important, you would be able to add the widget that you want. It wouldn’t be necessary to code widgets again for Goya explicitly.
*   Graphic effects: still several places to adapt (like the small “mark” that is shown on items when hovered in Dolphin for them being [un]selected, and other small stuff), and something more important: work on the style KCM to have this ready for 4.1.

Too much work and efforts are going into KDE 4.1, no less efforts that what went into 4.0 really, but I really see how we are stepping forward, and how we are making this dream a reality. Just wanted to keep you updated, since it has been some time without blogging.
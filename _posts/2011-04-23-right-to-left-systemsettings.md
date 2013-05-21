---
title: Right to Left Systemsettings
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=310
categories: kde
---
It has been a while since my last blog post, but I hope to blog more regularly from now on. I have been looking at my todo list at KDE, and I have some necessary things to do, and others that are just ideas and need to be developed.

For now, I have been hacking today on the Right to Left support on the categorized view. It was on my todo since the big refactor that I made long time ago. It is indeed very well structured in the inside, but was missing this important piece for Right to Left users.

So, [I have fixed this bug on master and backported it to the 4.6 branch][1]. I have also adapted in this case the category drawer of Systemsettings, which was kind of special because of the neat gradients. So, here is the mandatory screenshot:

 [1]: https://bugs.kde.org/show_bug.cgi?id=238508

Left to Right:

[![][3]][3]

 []: http://media.ereslibre.es/2011/04/systemsettings-ltr.png
 [3]: http://media.ereslibre.es/2011/04/systemsettings-ltr.png

Right to Left:

[![][5]][5]

 []: http://media.ereslibre.es/2011/04/systemsettings-rtl.png
 [5]: http://media.ereslibre.es/2011/04/systemsettings-rtl.png

Next stop: [keyboard navigation][6].

 [6]: https://bugs.kde.org/show_bug.cgi?id=237553

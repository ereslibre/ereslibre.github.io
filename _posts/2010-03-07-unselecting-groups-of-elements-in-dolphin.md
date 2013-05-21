---
title: (Un)Selecting groups of elements in Dolphin
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=208
enclosure:
  - |
    |
        http://media.ereslibre.es/2010/03/selection.mpeg
        3330080
        video/mpeg
        
categories: kde
---
I am very happy to blog again about KDE. Here I come with an old feature with a new face. I will hopefully come soon also with some Bluetooth updates, since I am working on a KCM for it, but it deserves another post entry when it is in shape and happy with it.

In KDE SC 4.3 I did some work for KCategorizedView to select several items by clicking on the header of the group. You could also unselect items, but that wasn’t so easy to discover. I later rewrote KCategorizedView internally to have a much better and clear structure. It was missing one feature: this kind of “grouping” selection. [Todd wrote a patch][1] for not losing this feature for KDE SC 4.4, which got into the review board and got into trunk. Nowadays KDE SC 4.4 has this patch.

 [1]: http://websvn.kde.org/trunk/KDE/kdelibs/kdeui/itemviews/kcategorizedview.cpp?r1=1075987&r2=1082876

I really had no time to review this patch, and I am the only guilty for this patch not being ‘so good’. And I say this because of two main reasons:

1. It does not check whether the model allows multiple selections or not. You can check this problem by clicking on System Settings group headers.

2. There is no indicator that “something is going to happen if you click here” to the user, what can feel like kind of magic if you click on the view randomly and suddenly all those items become selected, when you really wanted to clear your selection.

Actually, this feature and collapsing and expanding blocks was somehow in shape with the rewriting. I had that thought, and some pieces of the puzzle were there, but I was missing the actual time that took writing it.

So, I got hands to work today that I had “some free time”. [Here is the video result][2]:

 [2]: http://media.ereslibre.es/2010/03/selection.mpeg

[![][4]][4]

 []: http://media.ereslibre.es/2010/03/selection.mpeg

PS: This is still not in trunk. Finishing it and I hope very soon it will be all yours ![:)][4] 

 [4]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

PS2: If you feel curious about it, give it a try locally ([kdelibs][5], and [kdebase][6] patches).

 [5]: http://media.ereslibre.es/2010/03/selection-kdelibs.diff
 [6]: http://media.ereslibre.es/2010/03/selection-kdebase.diff

PS3: Do not misunderstand my words please, I deeply thank Todd for the patch since he introduced a feature that was lost.

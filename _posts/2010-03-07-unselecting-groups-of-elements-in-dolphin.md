---
id: 208
title: (Un)Selecting groups of elements in Dolphin
date: 2010-03-07T11:19:16+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=208

enclosure:
  - |
    http://media.ereslibre.es/2010/03/selection.mpeg
    3330080
    video/mpeg

dsq_thread_id:
  - "1301903549"
categories:
  - Archived
  - KDE Development
---
I am very happy to blog again about KDE. Here I come with an old feature with a new face. I will hopefully come soon also with some Bluetooth updates, since I am working on a KCM for it, but it deserves another post entry when it is in shape and happy with it.

In KDE SC 4.3 I did some work for KCategorizedView to select several items by clicking on the header of the group. You could also unselect items, but that wasn&#8217;t so easy to discover. I later rewrote KCategorizedView internally to have a much better and clear structure. It was missing one feature: this kind of &#8220;grouping&#8221; selection. <a href="http://websvn.kde.org/trunk/KDE/kdelibs/kdeui/itemviews/kcategorizedview.cpp?r1=1075987&r2=1082876" target="_blank">Todd wrote a patch</a> for not losing this feature for KDE SC 4.4, which got into the review board and got into trunk. Nowadays KDE SC 4.4 has this patch.

I really had no time to review this patch, and I am the only guilty for this patch not being &#8216;so good&#8217;. And I say this because of two main reasons:

1. It does not check whether the model allows multiple selections or not. You can check this problem by clicking on System Settings group headers.

2. There is no indicator that &#8220;something is going to happen if you click here&#8221; to the user, what can feel like kind of magic if you click on the view randomly and suddenly all those items become selected, when you really wanted to clear your selection.

Actually, this feature and collapsing and expanding blocks was somehow in shape with the rewriting. I had that thought, and some pieces of the puzzle were there, but I was missing the actual time that took writing it.

So, I got hands to work today that I had &#8220;some free time&#8221;. <a href="http://media.ereslibre.es/2010/03/selection.mpeg" target="_blank">Here is the video result</a>:

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2010/03/selection.mpeg" target="_blank"><img class="aligncenter" title="Selection" src="http://media.ereslibre.es/2010/03/selection.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: left;">
  PS: This is still not in trunk. Finishing it and I hope very soon it will be all yours 🙂
</p>

<p style="text-align: left;">
  PS2: If you feel curious about it, give it a try locally (<a href="http://media.ereslibre.es/2010/03/selection-kdelibs.diff" target="_blank">kdelibs</a>, and <a href="http://media.ereslibre.es/2010/03/selection-kdebase.diff" target="_blank">kdebase</a> patches).
</p>

<p style="text-align: left;">
  PS3: Do not misunderstand my words please, I deeply thank Todd for the patch since he introduced a feature that was lost.
</p>

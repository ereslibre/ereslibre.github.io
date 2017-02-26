---
id: 214
title: (Un)Selecting groups of elements in Dolphin (Part II)
date: 2010-03-08T10:08:33+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=214

enclosure:
  - |
    http://media.ereslibre.es/2010/03/selection2.mpeg
    2445708
    video/mpeg
    
dsq_thread_id:
  - "1301904184"
categories:
  - KDE Development
---
/me loves constructive criticism and nice ideas. I think I have several times guided some development through my blog in order to try to accomplish the maximum number of people ideas and suggestions.

This time is not an exception. Eike put onto the table something I was already aware, and something I wanted to fix, so his comment just pushed me what needed.

However I feel the need to explain why I won&#8217;t make headers clickable as before (unless you have a very good reason that will convince me :).

1. On the rewriting of KCategorizedView now the &#8220;header&#8221; is &#8220;everything&#8221;. Have  a look at System Settings. You will notice the &#8220;header&#8221; is covering the whole area of elements in that block. In case we have such a &#8220;category drawer&#8221; (as it is called in the code itself), how can we &#8220;draw&#8221; it to say &#8220;hey you are going to select the whole group&#8221;. Imagine you could select several items in System Settings (you shouldn&#8217;t, despite in 4.4 SC it is possible), how could you notify that in a visible way to the user ?

2. I felt showing the same icons as Dolphin does was a nice idea. Dolphin has this icons for individual selection of items, and I think that was the best way to go.

3. For this improvement (still not in trunk) I have gone through the path of &#8220;disabling&#8221; plus and minus signs, instead of making them disappear. From some UI classes taken I have learnt sudden visibility changes on elements are not good for the average user.

So <a href="http://media.ereslibre.es/2010/03/selection2.mpeg" target="_blank">here you have got the video</a>. As always, please feel free to comment, give ideas, suggestions&#8230;
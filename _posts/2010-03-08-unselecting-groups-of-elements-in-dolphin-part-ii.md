---
title: (Un)Selecting groups of elements in Dolphin (Part II)
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=214
enclosure:
  - |
    |
        http://media.ereslibre.es/2010/03/selection2.mpeg
        2445708
        video/mpeg
        
categories: kde
---
/me loves constructive criticism and nice ideas. I think I have several times guided some development through my blog in order to try to accomplish the maximum number of people ideas and suggestions.

This time is not an exception. Eike put onto the table something I was already aware, and something I wanted to fix, so his comment just pushed me what needed.

However I feel the need to explain why I won’t make headers clickable as before (unless you have a very good reason that will convince me ![:)][1] .

 [1]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

1. On the rewriting of KCategorizedView now the “header” is “everything”. Have  a look at System Settings. You will notice the “header” is covering the whole area of elements in that block. In case we have such a “category drawer” (as it is called in the code itself), how can we “draw” it to say “hey you are going to select the whole group”. Imagine you could select several items in System Settings (you shouldn’t, despite in 4.4 SC it is possible), how could you notify that in a visible way to the user ?

2. I felt showing the same icons as Dolphin does was a nice idea. Dolphin has this icons for individual selection of items, and I think that was the best way to go.

3. For this improvement (still not in trunk) I have gone through the path of “disabling” plus and minus signs, instead of making them disappear. From some UI classes taken I have learnt sudden visibility changes on elements are not good for the average user.

So [here you have got the video][2]. As always, please feel free to comment, give ideas, suggestions…

 [2]: http://media.ereslibre.es/2010/03/selection2.mpeg

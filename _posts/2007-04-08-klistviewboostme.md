---
title: KListView::boostMe()
author: ereslibre
layout: post
categories: kde
---
Nice !! I have boosted KListView, and now seems to be pretty fast, near to QListView (with some QTime benchmarks) when there are not lots of elements (approx. less than 500), because as you can see in the patch intersectionSet method still sucks, and it is very frequently called. There are some improvements needed (the one I have just said, right to left languages, drag & drop, and probably more), and if you [check the patch][1], there are some hard-coded values, just for testing reasons.

 [1]: http://media.ereslibre.es/2007/04/klistview.diff

I still have to to adjust scrollbars to real height, and I came with a small problem on Dolphin’s model. The model has a “naturalCompare”, so when you have items like “10-picture”, “08-picture” and “12-picture” it sorts them correctly. Another thing that the model does is showing first directories, and then files. This two behaviors leads KListView to problems. Why ? Well, since we have a QSortFilterProxyModel, KListView assumes element ‘n’ is bigger than element ‘n-1′. And of course, if ‘n’ is in category ‘k’, and ‘n 1′ is at category ‘l’, ‘n 2′ \*CAN’T\* be at category ‘k’. This is what exactly happens here: If you have a folder named “kde” and a picture named “kde.jpg”, sorted by Name and with some files and dirs between them, KListView will attempt to create two ‘K’ categories, and since they two aren’t next-to-other KListView will have a strange behavior at drawing. Same problem with the natural comparing at dolphin’s model. If you want to test KListView, and you don’t like this problems, just [apply this patch][2] and you’re done (for now), because we are going to fix these problems, without any doubt.

 [2]: http://media.ereslibre.es/2007/04/dolphinsortfilterproxymodel.diff

You can check out a screenshot, I know there is no significant visual improving from the anothers, but the fact that has been really boosted, makes me glad:

[![][4]][4]

 []: http://media.ereslibre.es/2007/04/categorization3.png
 [4]: http://media.ereslibre.es/2007/04/categorization3.png

Nice to meet you, fast KListView.

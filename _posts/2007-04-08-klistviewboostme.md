---
id: 25
title: KListView::boostMe()
date: 2007-04-08T05:50:55+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=25

dsq_thread_id:
  - "1301901003"
categories:
  - KDE Development
---
Nice !! I have boosted KListView, and now seems to be pretty fast, near to QListView (with some QTime benchmarks) when there are not lots of elements (approx. less than 500), because as you can see in the patch intersectionSet method still sucks, and it is very frequently called. There are some improvements needed (the one I have just said, right to left languages, drag & drop, and probably more), and if you <a target="_blank" href="http://media.ereslibre.es/2007/04/klistview.diff">check the patch</a>, there are some hard-coded values, just for testing reasons.

I still have to to adjust scrollbars to real height, and I came with a small problem on Dolphin&#8217;s model. The model has a &#8220;naturalCompare&#8221;, so when you have items like &#8220;10-picture&#8221;, &#8220;08-picture&#8221; and &#8220;12-picture&#8221; it sorts them correctly. Another thing that the model does is showing first directories, and then files. This two behaviors leads KListView to problems. Why ? Well, since we have a QSortFilterProxyModel, KListView assumes element &#8216;n&#8217; is bigger than element &#8216;n-1&#8217;. And of course, if &#8216;n&#8217; is in category &#8216;k&#8217;, and &#8216;n+1&#8217; is at category &#8216;l&#8217;, &#8216;n+2&#8217; \*CAN&#8217;T\* be at category &#8216;k&#8217;. This is what exactly happens here: If you have a folder named &#8220;kde&#8221; and a picture named &#8220;kde.jpg&#8221;, sorted by Name and with some files and dirs between them, KListView will attempt to create two &#8216;K&#8217; categories, and since they two aren&#8217;t next-to-other KListView will have a strange behavior at drawing. Same problem with the natural comparing at dolphin&#8217;s model. If you want to test KListView, and you don&#8217;t like this problems, just <a target="_blank" href="http://media.ereslibre.es/2007/04/dolphinsortfilterproxymodel.diff">apply this patch</a> and you&#8217;re done (for now), because we are going to fix these problems, without any doubt.

You can check out a screenshot, I know there is no significant visual improving from the anothers, but the fact that has been really boosted, makes me glad:

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/04/categorization3.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/04/categorization3.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

Nice to meet you, fast KListView.
---
id: 164
title: 'QTreeView fixing rampage &#8211; KDirOperator'
date: 2008-10-25T21:25:41+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=164

dsq_thread_id:
  - "1301903770"
categories:
  - KDE Development
---
I have submitted 3 new reports to qt-bugs&#8230; One of them affecting <a href="http://bugs.kde.org/171436" target="_blank">bug 171436</a>. This is a general bug that affects all applications (not only Amarok). Let&#8217;s go by parts on the submitted bugs to Trolltech:

  * Calling to selection() from the selection model contains duplicate ranges. Why ? This is easy: if you have a detailed view (or the tree detailed view), there are hidden columns (like owner, group and permissions). When there are hidden columns, the ranges are wrongly calculated (I <a href="http://media.ereslibre.es/2008/10/qtreeview-selection-columns-hidden.diff" target="_blank">proposed a fix</a>). (selection mode ExtendedSelection)

  * When clicking down on the blank viewport and dragging for selecting several items you expect the rubberband to be drawn. It isn&#8217;t. (selection mode ExtendedSelection)

  * When you click on the blank viewport you expect the current selection to be cleared. It isn&#8217;t. (selection mode ExtendedSelection).

The cool thing is that for those three issues I a Qt example and adapted it a bit. So, those three issues can be experimented with the <a href="http://media.ereslibre.es/2008/10/qtreeview-bugcase/" target="_blank">same test case</a>.

Note: tomorrow I will move the proposed fix to qt-copy patches&#8230; now I have to leave =)
---
title: 'QTreeView fixing rampage &#8211; KDirOperator'
author: ereslibre
layout: post
categories: kde
---
I have submitted 3 new reports to qt-bugs… One of them affecting [bug 171436][1]. This is a general bug that affects all applications (not only Amarok). Let’s go by parts on the submitted bugs to Trolltech:

 [1]: http://bugs.kde.org/171436

*   Calling to selection() from the selection model contains duplicate ranges. Why ? This is easy: if you have a detailed view (or the tree detailed view), there are hidden columns (like owner, group and permissions). When there are hidden columns, the ranges are wrongly calculated (I [proposed a fix][2]). (selection mode ExtendedSelection)

 [2]: http://media.ereslibre.es/2008/10/qtreeview-selection-columns-hidden.diff




*   When clicking down on the blank viewport and dragging for selecting several items you expect the rubberband to be drawn. It isn’t. (selection mode ExtendedSelection)




*   When you click on the blank viewport you expect the current selection to be cleared. It isn’t. (selection mode ExtendedSelection).

The cool thing is that for those three issues I a Qt example and adapted it a bit. So, those three issues can be experimented with the [same test case][3].

 [3]: http://media.ereslibre.es/2008/10/qtreeview-bugcase/

Note: tomorrow I will move the proposed fix to qt-copy patches… now I have to leave =)

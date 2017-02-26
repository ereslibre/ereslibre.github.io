---
id: 68
title: 'Qt working day&#8230;'
date: 2007-10-04T19:12:47+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=68

dsq_thread_id:
  - "1301902528"
categories:
  - KDE Development
---
Today it has been a Qt hacking day as well as TT notifying.

The first task sent was about the smooth scrolling at Qt on itemviews. You can find the code <a href="http://media.ereslibre.es/2007/10/SmoothScrollProblem/main.cpp" target="_blank">here</a>. Basically, run &#8220;qmake -project; qmake; make&#8221; and try to scroll with your mouse wheel&#8230; you will find that it goes pixel by pixel&#8230; oh man&#8230; no !! Now, try to modify the created &#8220;Makefile&#8221; and add the flag -DMOUSE\_BETTER\_SCROLLING. We need to do that workaround where you set the &#8220;smooth scrolling&#8221;, and we would like Qt to do it without any external help 🙂

The other task is about drag & drop. nefertum gave it a try some days ago in another approach of creating an ARGB window, but I also have given it a try. Right now, there are two given problems, mainly:

  * ListViews won&#8217;t set a pixmap to the cursor, so when you start a drag from a listview and go outside of the window, it seems &#8220;lost&#8221;. This is a problem on QListView&#8217;s code, and my fix also includes that.
  * The rest of the views are creating a pixmap filled with the background color, so when you start a drag with random items selected you can end up with stuff like <a href="http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop.png" target="_blank">this</a>. When working on it, and removing the special case of the listview (that makes Qt inconsistent also), you see that you can get really bad cases like <a href="http://media.ereslibre.es/2007/10/dolphindraggingiconmode.png" target="_blank">this one</a>.

Now with the <a href="http://media.ereslibre.es/2007/10/DragAndDropProblem/qt-copy.diff" target="_blank">fix that you can see here</a>, you can get results as <a href="http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop-fixed.png" target="_blank">this one</a>. There is still a remaining case&#8230; the pixmap created is the size of the viewport, so we still have corner cases that should be taken in count, like <a href="http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop-elementcut.png" target="_blank">this example</a>. Qt should check if the elements that are on the viewport are completely shown or not, and in that case, forcing the pixmap set to the drag operation bigger to make every item fit in there.

The test case for the drag & drop is public <a href="http://media.ereslibre.es/2007/10/DragAndDropProblem/main.cpp" target="_blank">here</a>.

After bug looking and busting&#8230; I am going to have some rest 🙂 Oh, forgot I have to do some BIC changes for Friday ! 🙂
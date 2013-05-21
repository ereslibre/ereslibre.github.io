---
title: 'Qt working day&#8230;'
author: ereslibre
layout: post
categories: kde
---
Today it has been a Qt hacking day as well as TT notifying.

The first task sent was about the smooth scrolling at Qt on itemviews. You can find the code [here][1]. Basically, run “qmake -project; qmake; make” and try to scroll with your mouse wheel… you will find that it goes pixel by pixel… oh man… no !! Now, try to modify the created “Makefile” and add the flag -DMOUSE\_BETTER\_SCROLLING. We need to do that workaround where you set the “smooth scrolling”, and we would like Qt to do it without any external help ![:)][2] 

 [1]: http://media.ereslibre.es/2007/10/SmoothScrollProblem/main.cpp
 [2]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

The other task is about drag & drop. nefertum gave it a try some days ago in another approach of creating an ARGB window, but I also have given it a try. Right now, there are two given problems, mainly:

*   ListViews won’t set a pixmap to the cursor, so when you start a drag from a listview and go outside of the window, it seems “lost”. This is a problem on QListView’s code, and my fix also includes that.
*   The rest of the views are creating a pixmap filled with the background color, so when you start a drag with random items selected you can end up with stuff like [this][3]. When working on it, and removing the special case of the listview (that makes Qt inconsistent also), you see that you can get really bad cases like [this one][4].

 [3]: http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop.png
 [4]: http://media.ereslibre.es/2007/10/dolphindraggingiconmode.png

Now with the [fix that you can see here][5], you can get results as [this one][6]. There is still a remaining case… the pixmap created is the size of the viewport, so we still have corner cases that should be taken in count, like [this example][7]. Qt should check if the elements that are on the viewport are completely shown or not, and in that case, forcing the pixmap set to the drag operation bigger to make every item fit in there.

 [5]: http://media.ereslibre.es/2007/10/DragAndDropProblem/qt-copy.diff
 [6]: http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop-fixed.png
 [7]: http://media.ereslibre.es/2007/10/DragAndDropProblem/treeviewdraganddrop-elementcut.png

The test case for the drag & drop is public [here][8].

 [8]: http://media.ereslibre.es/2007/10/DragAndDropProblem/main.cpp

After bug looking and busting… I am going to have some rest ![:)][2] Oh, forgot I have to do some BIC changes for Friday ! ![:)][2]

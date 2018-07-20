---
id: 69
title: Drag pixmap hacking
date: 2007-10-05T03:57:36+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=69

dsq_thread_id:
  - "1301902544"
categories:
  - Archived
  - KDE Development
---
On a quick hack I wanted to change the way things are shown when dragging items from an itemview. Stephen on the last post suggested that doing what we currently do can be improved. I agree with him, and despite I know that this solution is not the best, I still think is slightly better than the current one.

The screenshot in question is here:

<p style="text-align: center" align="left">
  <a href="http://media.ereslibre.es/2007/10/betterdraglooking.png" target="_blank"><img src="http://media.ereslibre.es/2007/10/betterdraglooking.png" border="0" height="240" width="320" /></a>
</p>

You <a href="http://media.ereslibre.es/2007/10/betterDraggingLook.diff" target="_blank">can apply the patch here</a> to test the behavior. Right now, with Dolphin (that uses KFileItemDelegate) I get strange drawing. Probably is because of some changes done to it lastly&#8230; but I&#8217;m right now very tired to track it&#8230; At least, the code I&#8217;ve written (the patch you see there) should be right, and this small test case in theory proves it&#8230; 🙂

From this screenshot you can imagine the layout of the selected items. I know that there are clever ways of doing so&#8230; but this one could work very nicely and without so many screen loss. What do you think ? Have you got an ideal layout ? Mockup please !

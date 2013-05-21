---
title: Capacity bars in properties dialogs
author: ereslibre
layout: post
dsq_thread_id:
  - 1301903116
categories: kde
---
Hi all,

I have been hacking on the ideas I got from people on the previous post mailing lists. I am pretty happy with the results I have got so far:

This is how my properties dialog looks showing the actual device usage level:

![][1]

 [1]: http://media.ereslibre.es/2008/04/kpropertiesdialog12.png

Since I have a pretty small amount of hard disk used, I have taken some shots with the percent hardcoded at 95%. I only have one problem at the moment: I need to think (ideas are welcome) how text can be drawn to correctly be seen even when the capacity bar is below the text:

The first screenshot shows the capacity bar with “fill full blocks” enabled, while on the second it is disabled. When disabled, this property would let the last block to have a different width than the rest if the percent is a certain one.

![][2]

 [2]: http://media.ereslibre.es/2008/04/kpropertiesdialog13.png

![][3]

 [3]: http://media.ereslibre.es/2008/04/kpropertiesdialog14.png

Apart  from improving the general appearance of the capacity bar, I think it would be great to make each block that goes to a higher percent more red. Maybe starting on green, and going through yellow. I will play with that tomorrow, I guess ![:)][4] 

 [4]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

Comments ? Ideas ? Suggestions ?

 

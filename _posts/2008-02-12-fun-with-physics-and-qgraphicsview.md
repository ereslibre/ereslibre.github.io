---
id: 89
title: Fun with physics and QGraphicsView
date: 2008-02-12T22:36:21+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=89

enclosure:
  - |
    http://media.ereslibre.es/2008/02/funwithphysics.mpeg
    5025266
    video/mpeg
    
dsq_thread_id:
  - "1301902886"
categories:
  - KDE Development
---
After some exams I needed to get my head out of worries for a while (still one on the stack to pop&#8230;). I know I shouldn&#8217;t go into a deep problem (as some issues with KToolBar/KMainWindow I need to debug when my exams are over), mainly because I know that if I start debugging them, I probably won&#8217;t stop till I find the problem, and that implies going at 6:00 AM on the morning to bed, what implies not sleeping, what implies not studying ;).

So, here I am, writing a small physics test app on QGraphicsView. I know we have similar stuff, and I know there are plans of getting things of this style to Plasma for icons. It will be hell nice when some of this things can be applied to our real desktop. Meanwhile you can play around.

You can <a href="http://media.ereslibre.es/2008/02/funwithphysics.mpeg" target="_blank">download a video of the example from here</a>, and you can find the <a href="http://media.ereslibre.es/2008/02/iconsproof" target="_blank">sources here</a>. If you want to compile them, you will only need Qt 4 and some terminal to write:

> $ qmake -project
  
> $ qmake
  
> $ make

So, that&#8217;s all for now folks 🙂

_PS: Please note that the code just sucks, but hey&#8230; I&#8217;m still playing with it, and sometimes it is nice to do really dirty stuff, for having the rest of the things clean (as KDE for instance) 😉_
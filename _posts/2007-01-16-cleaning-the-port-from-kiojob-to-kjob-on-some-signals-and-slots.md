---
id: 8
title: 'Cleaning the port from KIO::Job* to KJob* on some signals and slots'
date: 2007-01-16T22:36:24+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=8

dsq_thread_id:
  - "1343302049"
categories:
  - archived
  - kde
---
After some grep, I&#8217;ve noticed lots of signals/slots were wrong. In particular, if you look at kjob.h (at kdecore), you will notice that result signal is on there, and not on KIO::Job. So for example:

>  `SIGNAL(result(KIO::Job*))`

did become some time ago

>  `SIGNAL(result(KJob*))`

and same happened to more signals/slots. Recently, this has happened mainly to totalFiles, totalDirs, slotSpeed, and speed signals, because when coding kuiserver I really have tried to give total support to KJob. Now it is done.

In terms of the kuiserver interface, a configuration dialog has been added. It will let users select some personal settings referent to the kuiserver behaviour.

If you are going to inherit some kind of job from KJob class, please take in count these changes.

---
id: 144
title: Contribution request
date: 2008-08-27T14:27:52+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=144

dsq_thread_id:
  - "1301903356"
categories:
  - KDE Development
---
I don&#8217;t consider this a bugsquash, but I could do it perfectly. However, after fixing toolbar positioning problems on kdelibs, I just saw some applications (probably 3 out of 7 that I started) not doing stuff correctly (ignoring my toolbar positioning preferences). As an example, I fired up: konqueror, gwenview, kate, dolphin, kwrite, umbrello, kopete and kontact.

Konqueror: fine.

Gwenview: fine.

Kate: <span style="text-decoration: line-through;">fail</span>. **(fixed: trunk and 4.1)**

Dolphin: fine (after some fixing I did yesterday), it would have been a fail.

KWrite: fine.

Umbrello: <span style="text-decoration: line-through;">fail</span>. **(fixed: trunk and 4.1)**

Kontact: <span style="text-decoration: line-through;">fail in certain situations (if the component modified is the one being loaded on start)</span>. **(fixed: trunk and 4.1)**

I don&#8217;t consider this is good stats. For that reason I want **you to contribute**, by filling on bug reports which applications are **not restoring correctly your preferences**. Please note, this is **very important**: i am only asking for those applications that are not storing correctly any toolbar/dockview position/configuration (like text next to icon, text below icon)&#8230; And please, later **email me** with the bug report.

I am interested in fixing all this sort of bugs. If libraries are fine, but applications are just doing it in the wrong way, we are doing nothing.

I really would like to stop feeling overwhelmed =) Those so annoying bugs need to be fixed as fast as possible.

Thank you very much for your contribution and collaboration 🙂

**Last update: I think I have fixed all applications that had this problem. Please, if you are using trunk and you see this behavior (toolbars or dockwindows not restoring properly their positions and settings), ping me on IRC or send me a mail. I have backported all commits, so this fix should be also in 4.1 branch.**
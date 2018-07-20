---
id: 86
title: To split or not to split
date: 2008-02-01T16:55:26+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=86

dsq_thread_id:
  - "2155143156"
categories:
  - Archived
  - KDE Development
---
While looking at the <a target="_blank" href="http://techbase.kde.org/index.php?title=Schedules/KDE4/4.1_Feature_Plan">feature plans for KDE 4.1</a>, I saw that Goya was already added by somebody, and I only had to set its state as &#8220;In progress&#8221;. Thanks to whoever added it 🙂

What I&#8217;m sure about Goya is that its place is kdeui. I need to ask anyway on kcd for a more serious discussion if it should be into the kdeui library itself, or it can be a separate library (libgoya.so), as it is right now on playground.

Yesterday I finished the tool button that jpwhiting asked me to add, and probably I will add some label widget (which will help when you want a special font), as well as checkboxes and radioboxes. Those last two probably will be added when being at kdereview (or later, nobody asked for them yet). Before doing the move I need to write, anyway, a techbase tutorial so it&#8217;s usage is better documented.

---
id: 9
title: kio_uiserver from kdelibs/kio/misc moves to kuiserver at kdebase/runtime
date: 2007-01-16T22:41:38+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=9

dsq_thread_id:
  - "1566230897"
categories:
  - Archived
  - KDE Development
---
In order to improve the logical hierarchy of the trunk tree, David Faure moved the kio_uiserver from kdelibs/kio/misc to kdebase/runtime, where it makes more sense.

The renaming is important also. kio\_uiserver gives the idea that is only about io operations, while this is not true with the renewed kio\_uiserver, from now, kuiserver.

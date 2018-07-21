---
id: 158
title: Inline Preview support for Open/Save dialogs
date: 2008-10-01T16:22:54+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=158

dsq_thread_id:
  - "1301903840"
categories:
  - archived
  - kde
---
After some time hidden in the dark &#8220;fixing bugs&#8221; cave, I got out to work on a new feature for Open/Save dialogs. Actually, is somehow a fix-regression. I am working on it to correctly support inline previews. After the KFileWidgetPreviewGenerator code has been moved to kdelibs, it is a pleasure to work on this thing.

I also have hacked out a way to customize the icon size of the views, which I think feels pretty handy.

<a href="http://media.ereslibre.es/2008/10/preview.ogg" target="_blank">You can download the video example by clicking here</a>.

You can follow the develop of this branch <a href="http://gitorious.org/projects/personal-kdelibs/repos/mainline/logs/kfilewidget-previews" target="_blank">by clicking here</a>.

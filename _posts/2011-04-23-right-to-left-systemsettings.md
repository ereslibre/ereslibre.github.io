---
id: 310
title: Right to Left Systemsettings
date: 2011-04-23T23:32:36+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=310

dsq_thread_id:
  - "1301901552"
categories:
  - archived
  - kde
---
It has been a while since my last blog post, but I hope to blog more regularly from now on. I have been looking at my todo list at KDE, and I have some necessary things to do, and others that are just ideas and need to be developed.

For now, I have been hacking today on the Right to Left support on the categorized view. It was on my todo since the big refactor that I made long time ago. It is indeed very well structured in the inside, but was missing this important piece for Right to Left users.

So, <a href="https://bugs.kde.org/show_bug.cgi?id=238508" target="_blank">I have fixed this bug on master and backported it to the 4.6 branch</a>. I have also adapted in this case the category drawer of Systemsettings, which was kind of special because of the neat gradients. So, here is the mandatory screenshot:

Left to Right:

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2011/04/systemsettings-ltr.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2011/04/systemsettings-ltr.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: left;">
  Right to Left:
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2011/04/systemsettings-rtl.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2011/04/systemsettings-rtl.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: left;">
  Next stop: <a href="https://bugs.kde.org/show_bug.cgi?id=237553" target="_blank">keyboard navigation</a>.
</p>

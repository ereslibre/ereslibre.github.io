---
id: 14
title: The power of users, and usability
date: 2007-02-11T14:09:46+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=14

enclosure:
  - |
    http://media.ereslibre.es/2007/02/joining.mpeg
    3966492
    video/mpeg

dsq_thread_id:
  - "1301900695"
categories:
  - Archived
  - KDE Development
---
Short time ago we were discussing at planetkde how users can help KDE project without having programming knowledge. It is, of course, possible. And they really do a great job.If you are good at mockups, draw them. If you can translate, do it. If you have some time to write docs, write them. Well, there are lots of ways helping KDE project, and you can always think for yourself how proud are you for helping such a project.

<a target="_blank" href="http://www.kde-look.org/content/show.php?content=52738">I saw a mockup (that it was originally for Gnome project) on kde-look</a> and I couldn&#8217;t wait to start it. At a first try, I started modifying the exceptional delegate that fredrikh wrote (KFileItemDelegate). Because of the corner drawing, it needed to paint outside of the actual delegate rect, so I had to set clipping property, which is not very good actually. But then, the magical suggestion came from some voices on irc: &#8220;Inherit QListView and reimplement paintEvent method&#8221;. You had to say it :P.

Well, the screenshot that I attach is with the new class view KListView. It needs of course lots of polishing, and without being official we could even try to do this selection thing plugin-based, so where you see a round square indicating an element is selected, you could be seeing a star, a circumference, a cow, or a heart. Whatever.

<p align="center">
  <a target="_blank" href="http://media.ereslibre.es/2007/02/screenshot.png"><img border="0" width="320" src="http://media.ereslibre.es/2007/02/screenshot.png" height="240" style="width: 320px; height: 240px" /></a>
</p>

<a target="_blank" href="http://media.ereslibre.es/2007/02/joining.mpeg">You can take a look at the video too.</a>

Hope you like it 🙂

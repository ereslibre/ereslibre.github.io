---
title: The power of users, and usability
author: ereslibre
layout: post
enclosure:
  - |
    |
        http://media.ereslibre.es/2007/02/joining.mpeg
        3966492
        video/mpeg
        
categories: kde
---
Short time ago we were discussing at planetkde how users can help KDE project without having programming knowledge. It is, of course, possible. And they really do a great job.If you are good at mockups, draw them. If you can translate, do it. If you have some time to write docs, write them. Well, there are lots of ways helping KDE project, and you can always think for yourself how proud are you for helping such a project.

[I saw a mockup (that it was originally for Gnome project) on kde-look][1] and I couldn’t wait to start it. At a first try, I started modifying the exceptional delegate that fredrikh wrote (KFileItemDelegate). Because of the corner drawing, it needed to paint outside of the actual delegate rect, so I had to set clipping property, which is not very good actually. But then, the magical suggestion came from some voices on irc: “Inherit QListView and reimplement paintEvent method”. You had to say it ![:P][2] .

 [1]: http://www.kde-look.org/content/show.php?content=52738
 [2]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_razz.gif

Well, the screenshot that I attach is with the new class view KListView. It needs of course lots of polishing, and without being official we could even try to do this selection thing plugin-based, so where you see a round square indicating an element is selected, you could be seeing a star, a circumference, a cow, or a heart. Whatever.

[![][4]][4]

 []: http://media.ereslibre.es/2007/02/screenshot.png
 [4]: http://media.ereslibre.es/2007/02/screenshot.png

[You can take a look at the video too.][5]  
Hope you like it ![:)][6] 

 [5]: http://media.ereslibre.es/2007/02/joining.mpeg
 [6]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

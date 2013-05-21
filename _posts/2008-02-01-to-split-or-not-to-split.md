---
title: To split or not to split
author: ereslibre
layout: post
categories: kde
---
While looking at the [feature plans for KDE 4.1][1], I saw that Goya was already added by somebody, and I only had to set its state as “In progress”. Thanks to whoever added it ![:)][2] 

 [1]: http://techbase.kde.org/index.php?title=Schedules/KDE4/4.1_Feature_Plan
 [2]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

What I’m sure about Goya is that its place is kdeui. I need to ask anyway on kcd for a more serious discussion if it should be into the kdeui library itself, or it can be a separate library (libgoya.so), as it is right now on playground.

Yesterday I finished the tool button that jpwhiting asked me to add, and probably I will add some label widget (which will help when you want a special font), as well as checkboxes and radioboxes. Those last two probably will be added when being at kdereview (or later, nobody asked for them yet). Before doing the move I need to write, anyway, a techbase tutorial so it’s usage is better documented.

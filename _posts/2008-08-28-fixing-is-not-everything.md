---
title: Fixing is not everything
author: ereslibre
layout: post
categories: kde
---
I have just committed a speed fix for KFadeWidgetEffect. We do use very often the method setOpacity() which results to be really slow on current QPainter (we really hope this will be fixed on new versions of Qt). You can read [this techbase tutorial][1], written by [Fredrik Höglund][2], you will learn a lot about the dark side of QPainter, and how to avoid the more general cases that we usually face.

 [1]: http://techbase.kde.org/Development/Tutorials/Graphics/Performance
 [2]: http://fredrikh.blogspot.com/

I opposed of adding this fade in / fade out effect to page dialogs when this class was introduced because when the screen was maximized the performance was plain painful. Now that this code from KFileItemDelegate has been borrowed by KFadeWidgetEffect we can do fast blending, and I made the page dialogs blend their pages.

The [resulting video is the next one][3].

 [3]: http://media.ereslibre.es/2008/08/paged-blending.ogg

PS: This is not in KDE 4.1.

PS2: It will be possible to disable this effect from the style (probably) KCM from SystemSettings.

---
title: 'Advances: speed at KListView'
author: ereslibre
layout: post
categories: kde
---
After couple weeks with no time for KDE, I have been able to do some work at KListView (or however it will be called at the end). You can check this screenshot to see how it goes:

[![][2]][2]

 []: http://media.ereslibre.es/2007/04/categorization4.png
 [2]: http://media.ereslibre.es/2007/04/categorization4.png

I have increased the speed of the math that looks for each item place. There is still lots of work needed, but I think with some time it is going the right way.

I would really like to see if we can have some kind of “integration” with KStyle. It would be really nice to see how the categorization drawing changes if you have this or that style on KDE, and it would be really nice to see item joinings, since is the view the one that checks all that… and is what I’m writing… so we have some help on that. I will have to give a look to KStyle when improving some things that still need to… the intersectionSet method still stinks, but what I have seen is that it is fast for models > 500 elements, but I need to write a test to really check when it gets slow. I think it will “fly-off the road” when having a fast implementation of intersectionSet.

**Update:**

After the strong critic at comment #3, I want to point out something. Probably having ellipses is totally ugly, but my point was only to show that a category is not only a text, that if we make it come with the style, it can be fully customizable by the style. For that reason I have been told on IRC how to make a better screenshot, so there you go:

[![][4]][4]

 []: http://media.ereslibre.es/2007/04/categorization5.png
 [4]: http://media.ereslibre.es/2007/04/categorization5.png

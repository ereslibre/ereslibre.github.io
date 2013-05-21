---
title: Editable line edits in Goya
author: ereslibre
layout: post
categories: kde
---
After playing for a while with line edits in Goya, I successfully made them editable. There is still some stuff to make work properly (special keys [and characters], as backspace, delete, start, end and so…), but the most important thing at the moment is that you can write stuff on it. It can sound stupid, but I knew it was going to work when I made the keyboard cursor blinking. It wasn’t trivial for Goya, and now is there. I am so happy with it…

[![][2]][2]

 []: http://media.ereslibre.es/2008/02/goyaeditablelineedits.png
 [2]: http://media.ereslibre.es/2008/02/goyaeditablelineedits.png

I would like to thank Percy because he asked me if I was planning to make them editable, and I said “well, I have no plans, it won’t be easy”. But now that I see it, I love them, and it wasn’t that hard actually.

So, as usually the line edit will emit a signal when the text has changed, so your application can be ready for such a change and act in consequence.

You can try Goya from playground/libs/goya, and you can run the test of the line edits widgets with libs/goya/tests/goyatest2.

BTW, I won’t be able to code normally since my exams start this week… let’s see how they go ![:)][3] 

 [3]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

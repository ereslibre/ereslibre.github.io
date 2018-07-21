---
id: 87
title: Editable line edits in Goya
date: 2008-02-04T11:45:25+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=87

dsq_thread_id:
  - "1301900510"
categories:
  - archived
  - kde
---
After playing for a while with line edits in Goya, I successfully made them editable. There is still some stuff to make work properly (special keys [and characters], as backspace, delete, start, end and so&#8230;), but the most important thing at the moment is that you can write stuff on it. It can sound stupid, but I knew it was going to work when I made the keyboard cursor blinking. It wasn&#8217;t trivial for Goya, and now is there. I am so happy with it&#8230;

<p align="center">
  <a href="http://media.ereslibre.es/2008/02/goyaeditablelineedits.png" target="_blank"><img src="http://media.ereslibre.es/2008/02/goyaeditablelineedits.png" border="0" height="240" width="320" /></a>
</p>

I would like to thank Percy because he asked me if I was planning to make them editable, and I said &#8220;well, I have no plans, it won&#8217;t be easy&#8221;. But now that I see it, I love them, and it wasn&#8217;t that hard actually.

So, as usually the line edit will emit a signal when the text has changed, so your application can be ready for such a change and act in consequence.

You can try Goya from playground/libs/goya, and you can run the test of the line edits widgets with libs/goya/tests/goyatest2.

BTW, I won&#8217;t be able to code normally since my exams start this week&#8230; let&#8217;s see how they go 🙂

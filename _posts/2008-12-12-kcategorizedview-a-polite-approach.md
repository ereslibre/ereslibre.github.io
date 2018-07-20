---
id: 166
title: 'KCategorizedView &#8211; a polite approach'
date: 2008-12-12T01:10:52+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=166

dsq_thread_id:
  - "1301900563"
categories:
  - Archived
  - KDE Development
---
<p style="text-align: justify;">
  So many time without blogging&#8230; For being honest I have been really busy with university (still hell busy), and I have had time for coding mostly, without blogging on recent work I have been doing. Anyway, the short story, didn&#8217;t find the time to blog.
</p>

<p style="text-align: justify;">
  At this point, I am really happy to show you the new shiny KCategorizedView. It is not still on KDE&#8217;s SVN, but it will soon hit it. This new implementation will make it for 4.3, and is the implementation I was dreaming about.
</p>

<p style="text-align: justify;">
  When I was rewriting it from scratch, I could read <a href="http://weblog.obso1337.org/2008/system-settings-as-a-design-lesson/" target="_blank">Celeste&#8217;s post</a>, and wrote it down deep in my mind. This was all about KCategorizedView and I had to fix all those problems now that I was on it.
</p>

<p style="text-align: justify;">
  That&#8217;s the time I asked Nuno to design a mockup (talking with Celeste also, to have the usability team approval). He sent me this two mockups:
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/12/image2449.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/12/image2449.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: justify;">
  This one is meant for systemsettings, while the next one is meant for Dolphin:
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/12/image24492.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/12/image24492.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: justify;">
  Until now, the &#8220;category drawer&#8221; was the header of the category. This means, it could say: my height is 15 pixels. The view would ask it to be drawn on a rect of height 15 at the beginning of the category. I understood at this point that this wasn&#8217;t enough. So, after looking at both screenshots I understood the category drawer should be able to draw everywhere on that category bounds (imagine if you want to draw a big folder on the bottom right part of the category &#8216;folders&#8217; when sorting by type). Nowadays, on the new implementation, the category says: my height is 15 pixels. Then the view can do some operations to know the size of the whole block (say, 100 pixels height), and then when the category is asked to be drawn, it gets a 115 pixels height rect where it can draw. Of course is its own decision to only draw on the first 15 pixels if it wants so.
</p>

<p style="text-align: justify;">
  After so many talking, on a first approach of drawing and trying to get those mockups right, I have something like this:
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/12/systemsettings.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/12/systemsettings.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: center;">
  <a href="http://media.ereslibre.es/2008/12/dolphin-alternate.png" target="_blank"><img class="aligncenter" src="http://media.ereslibre.es/2008/12/dolphin-alternate.png" alt="" width="320" height="240" /></a>
</p>

<p style="text-align: justify;">
  Note that the alternate block coloring is not on the mockup, and probably will be removed, it was just for testing purposes.
</p>

<p style="text-align: justify;">
  Note also that this is not even on KDE subversion repository, and even when it gets to it, the way things are drawn can radically change if someone has objections and they are well based.
</p>

<p style="text-align: justify;">
  Please also note that screenshots are not very close to mockups in certain places. Just be patient, they will =)
</p>

<p style="text-align: justify;">
  I really love to see this on KDE SVN soon, since internally it got amazingly polite from my POV, what makes it really easier to maintain than the older view, and also to contain no hacks internally, what is very important.
</p>

<p style="text-align: justify;">
  If you feel like it, you can find all the work I am doing separately <a href="http://repo.or.cz/w/personal-kdelibs.git?a=shortlog;h=refs/heads/categorizedView" target="_blank">here for kdelibs</a>, and <a href="http://repo.or.cz/w/personal-kdebase.git?a=shortlog;h=refs/heads/dolphin" target="_blank">here for kdebase</a>.
</p>

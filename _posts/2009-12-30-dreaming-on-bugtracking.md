---
id: 205
title: Dreaming on bugtracking
date: 2009-12-30T14:45:34+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=205

dsq_thread_id:
  - "1301903831"
categories:
  - archived
  - kde
---
It has been a while since my last post. I have been working mostly for University, and now I got a job offer to work for very little time (even from home) on a new business that is emerging here in Madrid, Spain. I think is a good chance to get things done (R), and finish my studies at the same time that I am working. Hopefully we will be doing some Qt stuff, so I am glad after all. However dreams are still there.

In case you don&#8217;t know, I have been working in a library, called the &#8216;<a href="http://www.ereslibre.es/projects/ideal" target="_blank">Ideal Library</a>&#8216;. The idea was to create something similar to Qt (obviously million years behind in size and features), but with the advantages of the nowadays compilers improvements (c++0x in particular).

While I was setting up the <a href="http://www.mantisbt.org/" target="_blank">Mantis</a> bugtracker I thought that git, mercurial, bazaar are great tools. They allow you to work even offline among other really great features. However, there is a small problem here: what matters if you can work offline, having access to the full history of a project if you can&#8217;t access the bug tracking system because you need connection.

Here is when the idea came up. Why not having a **bugtracking** system that is also **distributed**. Why not even hook it up with git, being it a really great &#8220;one thing&#8221;. You can close bugs from your commit message, everything locally, and then, push those changes on bug reports state when you get connection.

And yes, <a href="http://bugs.kde.org" target="_blank">bugs.kde.org</a> database is actually huge. It would be a matter of just keeping the last 6 months attachments (or even older if you explicitly ask the system to do it for a certain bug report, because you are very interested in that one).

So to finish this blog entry, I&#8217;d like to wish you all a really great 2010 year, and I am looking forward to finish my studies and work hard on KDE. Really. There&#8217;s nothing I expect more than that, being back with this great community that I love so much.

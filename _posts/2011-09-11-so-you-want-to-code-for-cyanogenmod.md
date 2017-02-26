---
id: 316
title: So you want to code for CyanogenMod ?
date: 2011-09-11T02:07:12+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=316

dsq_thread_id:
  - "1302537424"
categories:
  - Android
---
We are living weird days. Kernel.org got compromised, and with it, all git repositories went down. It&#8217;s down for good, down for maintenance, reinstall and to be audited. But, for some cleaning reasons in the day that everything was put offline I cleaned up my android project folder. &#8220;Ok ! No worries ! CyanogenMod should have all repos mirrored !&#8221;. Well&#8230; yes&#8230; no.

So instead of bitching around, just put hands to work, and do some modifications on the &#8216;repo&#8217; helper script in order to fetch sources from wherever it can. It&#8217;s only a temporary fix until the situation gets normalized.

Now, let&#8217;s say we are building CM from scratch for Ace (HTC Desire HD). <a href="http://wiki.cyanogenmod.com/wiki/HTC_Ace:_Compile_CyanogenMod_(Linux)" target="_blank">The instructions are very similar to what you can find on the official wiki</a>.

The **Install the Repository** section needs a bit of tweaking:

<pre>curl https://raw.github.com/ereslibre/tools_repo/master/repo &gt; ~/bin/repo
chmod a+x repo</pre>

<pre>repo init -u git://github.com/ereslibre/android.git -b gingerbread</pre>

So now you only need to proceed normally and start hacking.
---
title: So you want to code for CyanogenMod ?
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=316
categories: android
---
We are living weird days. Kernel.org got compromised, and with it, all git repositories went down. It’s down for good, down for maintenance, reinstall and to be audited. But, for some cleaning reasons in the day that everything was put offline I cleaned up my android project folder. “Ok ! No worries ! CyanogenMod should have all repos mirrored !”. Well… yes… no.

So instead of bitching around, just put hands to work, and do some modifications on the ‘repo’ helper script in order to fetch sources from wherever it can. It’s only a temporary fix until the situation gets normalized.

Now, let’s say we are building CM from scratch for Ace (HTC Desire HD). [The instructions are very similar to what you can find on the official wiki][1].

 [1]: http://wiki.cyanogenmod.com/wiki/HTC_Ace:_Compile_CyanogenMod_(Linux)

The **Install the Repository** section needs a bit of tweaking:

    curl https://raw.github.com/ereslibre/tools_repo/master/repo > ~/bin/repo
    chmod a x repo

    repo init -u git://github.com/ereslibre/android.git -b gingerbread

So now you only need to proceed normally and start hacking.

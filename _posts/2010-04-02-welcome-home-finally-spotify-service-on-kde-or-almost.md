---
title: Welcome home. Finally Spotify service on KDE (or almost)
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=221
categories: kde
---
Hi all,

First of all I want to thank those who did congratulate me by Facebook because of my birthday ![:)][1] 

 [1]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

Next, I really love Spotify. I love it so much that I have been using wine lately for it to run, and I am even a Premium user. I have been always annoyed because of using wine for this purpose. Still, I think paying for \_the service\_ is fair enough, and I didn’t care too much about the client itself, what is important.

Some days ago I started a Spotify client for KDE (called “[Spokify][2]“). It is getting in shape, and well, it plays sound using Alsa for now (Phonon or QtMultimedia wasn’t enough when streaming, as far as I have seen, but I will keep an eye on them). It also can search, load your playlists, filter (this isn’t implemented in the official Spotify client!), load and show covers.

 [2]: http://www.gitorious.org/spokify

I am going to improve it to the point that I can assure it does the same things as Spotify, and more. Next steps are to include KWallet and probably some configuration options.

A**marok**

Some people have asked me why I have started a new application instead having developed an Amarok extension. Well, (and I don’t expect to start a flamewar here, please guys, don’t follow this path), I believe Spotify service is absolutely all I need. I for sure don’t need so many features that Amarok provides, and I wanted to start a small application that has a very well stablished goal.

**lib(open)spotify**

I am currently developing the application based on the official [libspotify][3] library. However, there also exists a library called [libopenspotify][4] which is source and binary compatible with libspotify.

 [3]: http://developer.spotify.com/en/libspotify/overview/
 [4]: http://github.com/noahwilliamsson/openspotify/tree/master/libopenspotify/

For those who really care about their freedom, they are free to use libopenspotify ![:)][1] 

The bad part of the story is that for you listening to music using Spokify you will need to be a Premium user because of the library restrictions (Application Key, better said).

**Packaging**

I still wonder why I have developed Spokify. Spotify service is very restrictive with the libspotify library usage, and they force you to have an appkey that you need to set on compile time.

Only Premium users can have an Application Key. So, my question here is: how is this thing going to be packaged, if ever ? I should assume the packager will be a Premium user, or in that case I could give him mine ? (since in the license, it is explicitly said that team coworkers can share the same Application Key, despite it being private and personal).

I think following this reasoning, the [despotify developers have their Application Key directly on the project repository][5]. I am not that brave. I have added an empty file with an #error that asks you to read HOW\_TO\_DEVELOP file. I can’t assume everyone that clones out my repo will use that Application Key for “legal?” stuff. Since I don’t want to be banned, I keep the Application Key secret.

 [5]: http://despotify.svn.sourceforge.net/viewvc/despotify/src/clients/libspotify-test/appkey.h?revision=304&view=markup

**Screenshots**

[![][7]][7]

 []: http://media.ereslibre.es/2010/04/spokify1.png
 [7]: http://media.ereslibre.es/2010/04/spokify1.png

[![][9]][9]

 []: http://media.ereslibre.es/2010/04/spokify2.png
 [9]: http://media.ereslibre.es/2010/04/spokify2.png

PS: If you try to compile Spokify, you will probably fail ![:)][1] I have written a patch for kdelibs that is not still in kdelibs trunk, [but you can have the patch here][10].

 [10]: http://media.ereslibre.es/2010/04/kdelibs.diff

---
id: 410
title: Fun with Android intents and Spotify
date: 2013-03-29T08:56:22+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=410

dsq_thread_id:
  - "1301812217"
dsq_needs_sync:
  - "1"
categories:
  - archived
  - Android
  - Life
---
I was taking a look on how to make my life easier with [Llama](https://play.google.com/store/apps/details?id=com.kebab.Llama&hl=en). I wanted to start Spotify when my phone connected to the Bluetooth adapter in my car, so instead of using the default &#8220;Launch Application&#8221; feature from Llama, I started looking around on how to improve it. I always start my starred playlist. So, I could directly show it by adding an Android Intent with the following parameters:

<pre>Action:
android.intent.action.VIEW
Data:
spotify:user:ereslibre:starred</pre>

Or the equivalent, with ADB:

<pre>adb shell am start -a android.intent.action.VIEW spotify:user:ereslibre:starred</pre>

Taking a deeper look I could start to directly play something (note that not my starred playlist) using the android.media.action.MEDIA\_PLAY\_FROM_SEARCH feature:

<pre>adb shell am start -n "com.spotify.mobile.android.ui/com.spotify.mobile.android.ui.Launcher" -a android.media.action.MEDIA_PLAY_FROM_SEARCH -e query "artist:heroes del silencio"</pre>

I also managed to fake play/stop key presses, this one is trivial:

<pre>Play:
adb shell input keyevent 126</pre>

<pre>Stop:
adb shell input keyevent 86</pre>

I&#8217;d be glad to hear from you if you manage to directly play your starred playlist, so I could even save a tap on my phone after getting into the car.

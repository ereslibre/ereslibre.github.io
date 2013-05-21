---
title: Fun with Android intents and Spotify
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=410
categories: android life
---
I was taking a look on how to make my life easier with [Llama][1]. I wanted to start Spotify when my phone connected to the Bluetooth adapter in my car, so instead of using the default “Launch Application” feature from Llama, I started looking around on how to improve it. I always start my starred playlist. So, I could directly show it by adding an Android Intent with the following parameters:

 [1]: https://play.google.com/store/apps/details?id=com.kebab.Llama&hl=en

    Action:
    android.intent.action.VIEW
    Data:
    spotify:user:ereslibre:starred

Or the equivalent, with ADB:

    adb shell am start -a android.intent.action.VIEW spotify:user:ereslibre:starred

Taking a deeper look I could start to directly play something (note that not my starred playlist) using the android.media.action.MEDIA\_PLAY\_FROM_SEARCH feature:

    adb shell am start -n "com.spotify.mobile.android.ui/com.spotify.mobile.android.ui.Launcher" -a android.media.action.MEDIA_PLAY_FROM_SEARCH -e query "artist:heroes del silencio"

I also managed to fake play/stop key presses, this one is trivial:

    Play:
    adb shell input keyevent 126

    Stop:
    adb shell input keyevent 86

I’d be glad to hear from you if you manage to directly play your starred playlist, so I could even save a tap on my phone after getting into the car.

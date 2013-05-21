---
title: Bluedevil v1.0 is out !
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=281
categories: kde
---
We, at [UFO Coders][1] are really glad to release version 1.0 of [Bluedevil][2], the new KDE bluetooth stack. It has been kind of long way, but finally is all ours !

 [1]: http://www.ufocoders.com/
 [2]: https://projects.kde.org/projects/extragear/base/bluedevil

We have focused on stability for this v1.0 release. Some highlights:

*   [Albert][3] gave a hand in order to fix about data information on all helpers, thus, making the application more i18n-ish.
*   [Pino][4] fixed some i18n() calls.
*   Now when a device is paired using the wizard, it is automatically set to trusted.
*   We are happily running on the brand new [projects.kde.org][5] instance now.

 [3]: http://tsdgeos.blogspot.com/
 [4]: http://www.kdedevelopers.org/blog/2661
 [5]: https://projects.kde.org/

So from now on, our main target will be to improve user experience (and keep stabilizing on errors that may pop out) where we believe it can be done, so if you have great ideas, don’t hesitate to report your feature requests !; right now we have a set of improvements for the post v1.0 upcoming release:

*   The monolithic application has a slightly different face, that we consider is more usable. Usability experts needed !

I also have some plans for [libbluedevil][6] for the near future:

 [6]: https://projects.kde.org/projects/playground/libs/libbluedevil

*   Fix includes, they are unnecessarily repetitive. For this I have to release a major version, since we are following the Qt/KDE way.
*   Add services, so we can really remove some repeated code in BlueDevil itself.

Now, I have taken some photographs in order to show some features:

![][7]
Monolithic Application

The monolithic application allows you to access the known devices, and connect to the services they provide. For post v1.0 versions we have redesigned this menu in order to be easier to access and less cluttered.

 [7]: http://media.ereslibre.es/2010/11/bluedevil/monolithic.png "Monolithic Application"

[![][9]][9]
Devices KCM

Our KCM’s have been thought to be really easy to use, concise and functional. Three KCM exist: Devices, Adapters and File transfer.

 []: http://media.ereslibre.es/2010/11/bluedevil/devices-kcm.png

*   The Devices KCM allows you to perform operations on already known devices. This includes: trust, untrust, rename (you can give an alias for a certain device) or disconnect. It also allows you to add new devices that are still unknown to your system. On the future, we will add also the ability to connect or disconnect from certain services of devices. Also, some other extended information like the hardware address and such.

[![][10]][10]
Adapters KCM

*   The Adapters KCM allows you to perform all possible operations over your adapters. Usually, you will have only one adapter, but you may have more. This KCM allows you to rename your adapter (that is how others bluetooth devices know and find you), (un)power it, or perform changes on the visibility of the device.

 []: http://media.ereslibre.es/2010/11/bluedevil/adapters-kcm.png

[![][11]][11]
Transfer KCM

*   The file transfer KCM allows you to completely enable or disable incoming transfer operations, and provide a default folder where this incoming transfers will be saved.

 []: http://media.ereslibre.es/2010/11/bluedevil/transfer-kcm.png

Another important bit is the KIO, that directly allows you to discover devices that are next to you, and browse their contents. I have taken some snapshots:

[![][12]][12]
Bluetooth KIO (listing devices)

[![][13]][13]
Bluetooth KIO (listing services)

[![][14]][14]
Bluetooth KIO (listing contents)

Since this is our first official release, we’d like to thank all those who packaged our v1.0-rc4, giving us valuable feedback from the users (in no special order): [Kubuntu][14], [OpenSuSE][15], [Arch Linux AUR][16], [Chakra][17], and probably some others that I am missing.

 []: http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio.png
 []: http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio2.png
 []: http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio3.png
 [14]: http://www.kubuntu.org/
 [15]: http://en.opensuse.org/Main_Page
 [16]: http://aur.archlinux.org/
 [17]: http://chakra-project.org/

Obviously, we also want to thank all users that reported us all kind of valuable info like error reports or feature requests. We will fix them all (in case of bugs) and take them seriously into consideration (in case of feature requests).

**TARBALLS**

*   **[libbluedevil-v1.8-1.tar.bz2][18]** 
    *   MD5: 03c79dd8a6d40e2872fee27c9b81190d
    *   SHA1: ff02c45cd6a8df39e3e8a0d48bcceff770637bad
*   **[bluedevil-v1.0.tar.bz2][19]** 
    *   MD5: b20d9c234adfe3c498f5577a88cd2f03
    *   SHA1: 0193732a383023869ea2e725fd649b257cdb7c38

 [18]: http://media.ereslibre.es/2010/11/libbluedevil-v1.8-1.tar.bz2
 [19]: http://media.ereslibre.es/2010/11/bluedevil-v1.0.tar.bz2

Yours,

[![][21]][21]

 []: http://www.ufocoders.com/

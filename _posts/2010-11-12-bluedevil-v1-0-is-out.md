---
id: 281
title: Bluedevil v1.0 is out !
date: 2010-11-12T16:25:50+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=281

dsq_thread_id:
  - "1301904275"
categories:
  - KDE Development
---
We, at <a href="http://www.ufocoders.com/" target="_blank">UFO Coders</a> are really glad to release version 1.0 of <a href="https://projects.kde.org/projects/extragear/base/bluedevil" target="_blank">Bluedevil</a>, the new KDE bluetooth stack. It has been kind of long way, but finally is all ours !

We have focused on stability for this v1.0 release. Some highlights:

  * <a href="http://tsdgeos.blogspot.com/" target="_blank">Albert</a> gave a hand in order to fix about data information on all helpers, thus, making the application more i18n-ish.
  * <a href="http://www.kdedevelopers.org/blog/2661" target="_blank">Pino</a> fixed some i18n() calls.
  * Now when a device is paired using the wizard, it is automatically set to trusted.
  * We are happily running on the brand new <a href="https://projects.kde.org/" target="_blank">projects.kde.org</a> instance now.

So from now on, our main target will be to improve user experience (and keep stabilizing on errors that may pop out) where we believe it can be done, so if you have great ideas, don&#8217;t hesitate to report your feature requests !; right now we have a set of improvements for the post v1.0 upcoming release:

  * The monolithic application has a slightly different face, that we consider is more usable. Usability experts needed !

I also have some plans for <a href="https://projects.kde.org/projects/playground/libs/libbluedevil" target="_blank">libbluedevil</a> for the near future:

  * Fix includes, they are unnecessarily repetitive. For this I have to release a major version, since we are following the Qt/KDE way.
  * Add services, so we can really remove some repeated code in BlueDevil itself.

Now, I have taken some photographs in order to show some features:

<div style="width: 454px" class="wp-caption aligncenter">
  <img title="Monolithic Application" src="http://media.ereslibre.es/2010/11/bluedevil/monolithic.png" alt="" width="444" height="413" />
  
  <p class="wp-caption-text">
    Monolithic Application
  </p>
</div>

<p style="text-align: left;">
  The monolithic application allows you to access the known devices, and connect to the services they provide. For post v1.0 versions we have redesigned this menu in order to be easier to access and less cluttered.
</p>

<div style="width: 493px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/devices-kcm.png" target="_blank"><img class="       " title="Devices KCM" src="http://media.ereslibre.es/2010/11/bluedevil/devices-kcm.png" alt="" width="483" height="323" /></a>
  
  <p class="wp-caption-text">
    Devices KCM
  </p>
</div>

<p style="text-align: left;">
  Our KCM&#8217;s have been thought to be really easy to use, concise and functional. Three KCM exist: Devices, Adapters and File transfer.
</p>

  * The Devices KCM allows you to perform operations on already known devices. This includes: trust, untrust, rename (you can give an alias for a certain device) or disconnect. It also allows you to add new devices that are still unknown to your system. On the future, we will add also the ability to connect or disconnect from certain services of devices. Also, some other extended information like the hardware address and such.

<div style="width: 564px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/adapters-kcm.png" target="_blank"><img class="    " title="Adapters KCM" src="http://media.ereslibre.es/2010/11/bluedevil/adapters-kcm.png" alt="" width="554" height="368" /></a>
  
  <p class="wp-caption-text">
    Adapters KCM
  </p>
</div>

  * The Adapters KCM allows you to perform all possible operations over your adapters. Usually, you will have only one adapter, but you may have more. This KCM allows you to rename your adapter (that is how others bluetooth devices know and find you), (un)power it, or perform changes on the visibility of the device.

<div style="width: 564px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/transfer-kcm.png" target="_blank"><img class="     " title="Transfer KCM" src="http://media.ereslibre.es/2010/11/bluedevil/transfer-kcm.png" alt="" width="554" height="368" /></a>
  
  <p class="wp-caption-text">
    Transfer KCM
  </p>
</div>

  * The file transfer KCM allows you to completely enable or disable incoming transfer operations, and provide a default folder where this incoming transfers will be saved.

<p style="text-align: left;">
  Another important bit is the KIO, that directly allows you to discover devices that are next to you, and browse their contents. I have taken some snapshots:
</p>

<div style="width: 560px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio.png" target="_blank"><img class="  " title="Bluetooth KIO (listing devices)" src="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio.png" alt="" width="550" height="386" /></a>
  
  <p class="wp-caption-text">
    Bluetooth KIO (listing devices)
  </p>
</div>

<div style="width: 560px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio2.png" target="_blank"><img class=" " title="Bluetooth KIO (listing services)" src="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio2.png" alt="" width="550" height="386" /></a>
  
  <p class="wp-caption-text">
    Bluetooth KIO (listing services)
  </p>
</div>

<div style="width: 576px" class="wp-caption aligncenter">
  <a href="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio3.png" target="_blank"><img class=" " title="Bluetooth KIO (listing contents)" src="http://media.ereslibre.es/2010/11/bluedevil/bluetooth-kio3.png" alt="" width="566" height="412" /></a>
  
  <p class="wp-caption-text">
    Bluetooth KIO (listing contents)
  </p>
</div>

Since this is our first official release, we&#8217;d like to thank all those who packaged our v1.0-rc4, giving us valuable feedback from the users (in no special order): <a href="http://www.kubuntu.org/" target="_blank">Kubuntu</a>, <a href="http://en.opensuse.org/Main_Page" target="_blank">OpenSuSE</a>, <a href="http://aur.archlinux.org/" target="_blank">Arch Linux AUR</a>, <a href="http://chakra-project.org/" target="_blank">Chakra</a>, and probably some others that I am missing.

Obviously, we also want to thank all users that reported us all kind of valuable info like error reports or feature requests. We will fix them all (in case of bugs) and take them seriously into consideration (in case of feature requests).

<p style="text-align: left;">
  <strong>TARBALLS</strong>
</p>

  * **<a href="http://media.ereslibre.es/2010/11/libbluedevil-v1.8-1.tar.bz2" target="_blank">libbluedevil-v1.8-1.tar.bz2</a>** 
      * MD5: <tt>03c79dd8a6d40e2872fee27c9b81190d</tt>
      * SHA1: <tt>ff02c45cd6a8df39e3e8a0d48bcceff770637bad</tt>
  * **<a href="http://media.ereslibre.es/2010/11/bluedevil-v1.0.tar.bz2" target="_blank">bluedevil-v1.0.tar.bz2</a>** 
      * MD5: <tt>b20d9c234adfe3c498f5577a88cd2f03</tt>
      * SHA1: <tt>0193732a383023869ea2e725fd649b257cdb7c38</tt>

<p style="text-align: left;">
  <p style="text-align: left;">
    <p style="text-align: left;">
      Yours,
    </p>
    
    <p style="text-align: center;">
      <a href="http://www.ufocoders.com/" target="_blank"><img class="alignnone" src="http://ufocoders.com/sites/all/themes/arthemia/logo.png" alt="" width="302" height="61" /></a>
    </p>
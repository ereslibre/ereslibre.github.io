---
id: 253
title: libbluedevil
date: 2010-07-28T17:39:37+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=253

dsq_thread_id:
  - "1301902494"
categories:
  - Archived
  - KDE Development
---
libbluedevil is a stable Qt-based library written in C++ to handle all Bluetooth functionality. Here is the man that you want to blame when something isn&#8217;t working properly on this library. It consists of a very easy and straight-forward API, featuring:

  * Manager

<p style="padding-left: 60px;">
  The entry point for the library. The Manager will tell you whether the Bluetooth system is operational, will signal you when adapters have been connected or disconnected, or when the default adapter has changed.
</p>

  * Adapter

<p style="padding-left: 60px;">
  The Adapter class has everything you can imagine to handle Bluetooth adapters. It can retrieve and set all kind of settings for the physical adapter. Summing up: start and stop discovering, visibility, timeout for visibility, retrieve known devices, register or unregister an agent, retrieve device by its hardware address (MAC) or its UBI&#8230; It will also signal you when discovering devices, and a remote device has been found.
</p>

  * Device

<p style="padding-left: 60px;">
  It represents a remote device. It basically retrieves information, but it can also set certain properties such as whether the remote device is trusted, block it, or set an alias for the device. Regarding what it can retrieve&#8230; all kind of information: its name, hardware address (MAC), icon, device class, supported services (UUIDs)&#8230;
</p>

The library is currently at its v1.7 version, and the idea is to keep API/ABI between minor releases as we are used to. The version 2.0 will be released at some point with more handy includes (currently &#8220;#include <bluedevil/bluedevilmanager.h>&#8221;, what will be renamed to &#8220;#include <bluedevil/manager.h>&#8221;).

Since BlueDevil will be moved to KDE upstream soon, eventually libbluedevil will also be placed at kdesupport, since the BlueDevil system has a hard-dependency on this library.

Bug tracking exclusively for library users will be tracked <a href="http://projects.ufocoders.com/projects/libbluedevil" target="_blank">here</a>. The official repository can be cloned by running:

<pre>git clone git://projects.ufocoders.com/libbluedevil</pre>

However, as some of you may know, a completely-always-updated mirror lives at gitorious:

<pre>git clone git://gitorious.org/libbluedevil/libbluedevil.git</pre>

As always, feedback is very important, so I am open to suggestions, patches&#8230; Actually the gitorious mirror is a very nice place to propose merge requests in the case that you want to contribute any patch.

This library is in production since v1.0 and it is stable, being used by BlueDevil as well as other applications KDE-unrelated.

It has been very fun to develop this library, and there is more fun waiting&#8230; I have some more ideas on how to make it even more complete, but those news will come incrementally&#8230;

<p style="text-align: center;">
  <a href="http://www.ufocoders.com" target="_blank"><img class="aligncenter" src="http://ufocoders.com/sites/all/themes/arthemia/logo.png" alt="" width="302" height="61" /></a>
</p>

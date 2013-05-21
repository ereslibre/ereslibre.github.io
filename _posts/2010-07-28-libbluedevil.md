---
title: libbluedevil
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=253
categories: kde
---
libbluedevil is a stable Qt-based library written in C to handle all Bluetooth functionality. Here is the man that you want to blame when something isn’t working properly on this library. It consists of a very easy and straight-forward API, featuring:

*   Manager

The entry point for the library. The Manager will tell you whether the Bluetooth system is operational, will signal you when adapters have been connected or disconnected, or when the default adapter has changed.

*   Adapter

The Adapter class has everything you can imagine to handle Bluetooth adapters. It can retrieve and set all kind of settings for the physical adapter. Summing up: start and stop discovering, visibility, timeout for visibility, retrieve known devices, register or unregister an agent, retrieve device by its hardware address (MAC) or its UBI… It will also signal you when discovering devices, and a remote device has been found.

*   Device

It represents a remote device. It basically retrieves information, but it can also set certain properties such as whether the remote device is trusted, block it, or set an alias for the device. Regarding what it can retrieve… all kind of information: its name, hardware address (MAC), icon, device class, supported services (UUIDs)…

The library is currently at its v1.7 version, and the idea is to keep API/ABI between minor releases as we are used to. The version 2.0 will be released at some point with more handy includes (currently “#include ”, what will be renamed to “#include ”).

Since BlueDevil will be moved to KDE upstream soon, eventually libbluedevil will also be placed at kdesupport, since the BlueDevil system has a hard-dependency on this library.

Bug tracking exclusively for library users will be tracked [here][1]. The official repository can be cloned by running:

 [1]: http://projects.ufocoders.com/projects/libbluedevil

    git clone git://projects.ufocoders.com/libbluedevil

However, as some of you may know, a completely-always-updated mirror lives at gitorious:

    git clone git://gitorious.org/libbluedevil/libbluedevil.git

As always, feedback is very important, so I am open to suggestions, patches… Actually the gitorious mirror is a very nice place to propose merge requests in the case that you want to contribute any patch.

This library is in production since v1.0 and it is stable, being used by BlueDevil as well as other applications KDE-unrelated.

It has been very fun to develop this library, and there is more fun waiting… I have some more ideas on how to make it even more complete, but those news will come incrementally…

[![][3]][3]

 []: http://www.ufocoders.com

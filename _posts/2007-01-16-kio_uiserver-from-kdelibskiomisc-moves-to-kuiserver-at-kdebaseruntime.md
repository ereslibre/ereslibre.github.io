---
title: kio_uiserver from kdelibs/kio/misc moves to kuiserver at kdebase/runtime
author: ereslibre
layout: post
categories: kde
---
In order to improve the logical hierarchy of the trunk tree, David Faure moved the kio_uiserver from kdelibs/kio/misc to kdebase/runtime, where it makes more sense.

The renaming is important also. kio\_uiserver gives the idea that is only about io operations, while this is not true with the renewed kio\_uiserver, from now, kuiserver.

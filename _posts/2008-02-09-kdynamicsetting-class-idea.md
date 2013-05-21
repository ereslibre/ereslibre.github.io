---
title: KDynamicSetting class idea
author: ereslibre
layout: post
categories: kde
---
I’ve been thinking on a new component that could make life easier to us, developers. Nowadays it is very important that the whole desktop seem to just respond to what the user wants. If the users steps into systemsettings and changes some style parameter, he/she can expect it to be changed at the moment on his/her whole desktop, without the need of restarting anything.

Following this ideas, KGlobalSettings as we know is a singleton, that each app uses for reading standard stuff. The main problem is that if you are asking it very frequently you can end up in lots of KConfig calls, what is not funny. KGlobalSettings is nice enough to notify all running instances of applications that some kind of configuration has been changed for letting the application update its appearance or whatever.

This hasn’t been a problem till now, because for instance, when you change a font, that is set in QApplication’s context (QApplication::setFont()), and when KGlobalSettings receives such a signal (something changed in fonts), it will update the fonts of the application. So that’s pretty internal. Same happens with KPushButton, which is connected to the signal that KGlobalSettings emit when something has changed, and just updates itself just in case the user changed the property (icons on buttons).

But this time has been slightly different. I have been working, as you may know if you are suscribed to kcd mailing list, on the global (de)activation of builtin animations in KDE applications. That had an impact on lots of places: KMainWindow, KImageFilePreview, KLineEdit, Plasma::Phase, KFaceWidgetEffect, Konsole… My patches adds to every private class a new slot that is connected to the KGlobalSettings changed signal, and updates themselves internally, just for the reason of not asking KGlobalSettings::animationsEnanbled() so frequently. But I’d prefer to move this logic out of the applications themselves. That means I’d love to do something like:

> KDynamicSetting animsEnabled(KDynamicSetting::AnimationsEnabled);  
> …  
> …  
> if (animsEnabled.content().toBool())  
> doSomething();  
> else  
> doAnotherThing();  
> …  
> … 

Internally KDynamicSetting class when is constructed, connects itself to the KGlobalSettings changed signal, and when the information relevant to that instance (in this case, AnimationsEnabled) is changed, it updates its value automatically, so what our app reads when asking animsEnabled.content().toBool() is always the most updated thing, magically.

Of course, you probably may want to do extra stuff that you \_have to do\_ when something like this happens. KDynamicSetting would contain a signal that you can connect to in the case that the property it contains has changed because of a global setting change (for instance running systemsettings and changing the animation property).

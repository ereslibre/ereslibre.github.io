---
title: A note on plugins
author: ereslibre
layout: post
categories: kde
---
This time I wanted to say a small note on plugins. Well, more than plugins itself, about plugins configuration dialog. KPluginSelector as we know is able to detect if a plugin has configuration dialog or not. It is actually able to detect more than one configuration dialog that a plugin may have and tab them in an unique configuration dialog.

I am an extremely ordered person to what computers means. As far as I have seen right now, lots of people that uses KPluginSelector does use a .so (probably for more than one configuration dialog) for configuration dialog and another .so for the plugin itself. I created an example for KWrite that shows how to “encapsullate” the plugin and its configuration dialog in the same .so file, so it is even prettier: http://websvn.kde.org/trunk/KDE/kdelibs/kate/plugins/timedate.

The most important thing is that we need a desktop file for each configuration widget, and another one for the plugin itself. The plugin of this example only has one configuration widget. When we create the definition we need something like:  
`
K_PLUGIN_FACTORY_DEFINITION(TimeDatePluginFactory,
        registerPlugin("ktexteditor_timedate");
        registerPlugin("ktexteditor_timedate_config");
        )
`

“ktexteditor\_timedate” is the keyword for the plugin itself, while “ktexteditor\_timedate_config” is the keyword for the plugin config widget itself. Of course they could have been named “foo” and “bar”, there is no need to call them in a significant way, but convenient for others to read the code.

***ktexteditor_timedate.desktop***`
[Desktop Entry]
X-KDE-Library=ktexteditor_timedate
X-KDE-PluginKeyword=ktexteditor_timedate
.... entries ....
X-KDE-ServiceTypes=KTextEditor/Plugin
Type=Service
.... the rest of entries ....
`

***ktexteditor\_timedate\_config.desktop***`
[Desktop Entry]
Type=Service
X-KDE-ServiceTypes=KCModule
X-KDE-Library=ktexteditor_timedate
X-KDE-PluginKeyword=ktexteditor_timedate_config
X-KDE-FactoryName=ktexteditor_timedate_config
X-KDE-ParentComponents=ktexteditortimedate
.... the rest of entries ....
`

This is pretty nice since as you can see on the CMakeLists.txt file, the plugin itself and the config widget are on the same .so file. This makes things more ordered. There exist no problem because they have different entry points on the library.

Now, if you would like to make your current plugins more ordered, and you need further info, just ping me on IRC or write me an email.

That’s all for now folks, have fun at Google headquarters, and let’s make KDE 4 series rock.

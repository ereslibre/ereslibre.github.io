---
id: 83
title: A note on plugins
date: 2008-01-05T14:24:49+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=83

dsq_thread_id:
  - "1301902767"
categories:
  - archived
  - kde
---
This time I wanted to say a small note on plugins. Well, more than plugins itself, about plugins + configuration dialog. KPluginSelector as we know is able to detect if a plugin has configuration dialog or not. It is actually able to detect more than one configuration dialog that a plugin may have and tab them in an unique configuration dialog.

I am an extremely ordered person to what computers means. As far as I have seen right now, lots of people that uses KPluginSelector does use a .so (probably for more than one configuration dialog) for configuration dialog and another .so for the plugin itself. I created an example for KWrite that shows how to &#8220;encapsullate&#8221; the plugin and its configuration dialog in the same .so file, so it is even prettier: <a href="http://websvn.kde.org/trunk/KDE/kdelibs/kate/plugins/timedate" target=_blank>http://websvn.kde.org/trunk/KDE/kdelibs/kate/plugins/timedate</a>.

The most important thing is that we need a desktop file for each configuration widget, and another one for the plugin itself. The plugin of this example only has one configuration widget. When we create the definition we need something like:

`<br />
K_PLUGIN_FACTORY_DEFINITION(TimeDatePluginFactory,<br />
        registerPlugin<TimeDatePlugin>("ktexteditor_timedate");<br />
        registerPlugin<TimeDateConfig>("ktexteditor_timedate_config");<br />
        )<br />
`

&#8220;ktexteditor\_timedate&#8221; is the keyword for the plugin itself, while &#8220;ktexteditor\_timedate_config&#8221; is the keyword for the plugin config widget itself. Of course they could have been named &#8220;foo&#8221; and &#8220;bar&#8221;, there is no need to call them in a significant way, but convenient for others to read the code.

_**ktexteditor_timedate.desktop**_`<br />
[Desktop Entry]<br />
X-KDE-Library=ktexteditor_timedate<br />
X-KDE-PluginKeyword=ktexteditor_timedate<br />
.... entries ....<br />
X-KDE-ServiceTypes=KTextEditor/Plugin<br />
Type=Service<br />
.... the rest of entries ....<br />
`

_**ktexteditor\_timedate\_config.desktop**_`<br />
[Desktop Entry]<br />
Type=Service<br />
X-KDE-ServiceTypes=KCModule<br />
X-KDE-Library=ktexteditor_timedate<br />
X-KDE-PluginKeyword=ktexteditor_timedate_config<br />
X-KDE-FactoryName=ktexteditor_timedate_config<br />
X-KDE-ParentComponents=ktexteditortimedate<br />
.... the rest of entries ....<br />
`

This is pretty nice since as you can see on the CMakeLists.txt file, the plugin itself and the config widget are on the same .so file. This makes things more ordered. There exist no problem because they have different entry points on the library.

Now, if you would like to make your current plugins more ordered, and you need further info, just ping me on IRC or write me an email.

That&#8217;s all for now folks, have fun at Google headquarters, and let&#8217;s make KDE 4 series rock.

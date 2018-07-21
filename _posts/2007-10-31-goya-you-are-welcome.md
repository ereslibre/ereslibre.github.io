---
id: 73
title: 'Goya: you are welcome'
date: 2007-10-31T19:12:54+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=73

enclosure:
  - |
    http://media.ereslibre.es/2007/10/goya.mpeg
    19132220
    video/mpeg
dsq_thread_id:
  - "1301901323"
categories:
  - archived
  - kde
---
Now that we are reading really nice news on adding real widgets to a QGraphicsView/QGraphicsScene, I want to tell you a small secret too, on the same shape, more or less.

<span style="font-weight: bold">Explanation and general info</span>:

As anyone who has developed with Model/View programming, I am sure we can agree it is hard (more than hard, \_not trivial\_) to add widgets to delegates. And what&#8217;s more: handle interaction with the user.

I wanted to cover this gap in an easy way. It is really, really new stuff, and it is on a very early phase. That means, no, it is not on SVN yet. I will consider adding it when it gets more or less functional.

The main idea: your model will be asked on certain roles (widget, style, widgetcount), specified by Goya, and it should be able to give that information. For example, a Goya::PushButton is something like:

class KDEUI_EXPORT PushButton

: public Widget

{

[&#8230;]

Q_SIGNALS:

void clicked(const QModelIndex &index);

[&#8230;]

};

That means exactly what you think. Your model will return those widgets to be drawn (for now I only have written push buttons, but this is really easy to expand). It is designed in a way that a same delegate in a row and column can have more than one widget.

So basically, you create your widgets, the model returns them for the delegate to paint them, along with the style properties (rect&#8230;), and you can connect the signals from the Goya::Widget, for example, in the case of Goya::PushButton you will be able to connect the clicked() signal with some slot on your app.

<p style="font-weight: bold">
  Demonstration video:
</p>

<a href="http://media.ereslibre.es/2007/10/goya.mpeg" target="_blank">Click here to download the demonstration video<span style="font-weight: normal"> </span></a>

<a href="http://media.ereslibre.es/2007/10/goya.mpeg" style="font-weight: bold" target="_blank"><span style="font-weight: normal"></span></a>

For now, that&#8217;s all&#8230; I will blog again with improvements 🙂

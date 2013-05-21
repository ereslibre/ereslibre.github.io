---
title: 'Goya: you are welcome'
author: ereslibre
layout: post
enclosure:
  - |
    http://media.ereslibre.es/2007/10/goya.mpeg
    19132220
    video/mpeg
categories: kde
---
Now that we are reading really nice news on adding real widgets to a QGraphicsView/QGraphicsScene, I want to tell you a small secret too, on the same shape, more or less.

Explanation and general info:

As anyone who has developed with Model/View programming, I am sure we can agree it is hard (more than hard, \_not trivial\_) to add widgets to delegates. And what’s more: handle interaction with the user.

I wanted to cover this gap in an easy way. It is really, really new stuff, and it is on a very early phase. That means, no, it is not on SVN yet. I will consider adding it when it gets more or less functional.

The main idea: your model will be asked on certain roles (widget, style, widgetcount), specified by Goya, and it should be able to give that information. For example, a Goya::PushButton is something like:

class KDEUI_EXPORT PushButton  
: public Widget  
{  
[...]

Q_SIGNALS:  
void clicked(const QModelIndex &index);  
[...]  
};

That means exactly what you think. Your model will return those widgets to be drawn (for now I only have written push buttons, but this is really easy to expand). It is designed in a way that a same delegate in a row and column can have more than one widget.

So basically, you create your widgets, the model returns them for the delegate to paint them, along with the style properties (rect…), and you can connect the signals from the Goya::Widget, for example, in the case of Goya::PushButton you will be able to connect the clicked() signal with some slot on your app.

Demonstration video:

[Click here to download the demonstration video ][1]

 [1]: http://media.ereslibre.es/2007/10/goya.mpeg

[][1]  
For now, that’s all… I will blog again with improvements ![:)][2] 

 [2]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

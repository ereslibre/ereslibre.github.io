---
title: KListView finally committed
author: ereslibre
layout: post
categories: kde
---
I finally committed today KListView into kdebase/apps/dolphin. It still expects speed improvements on setSelection() and mouseReleaseEvent() methods. There are a few problems when you change the sorting role on the fly, as well as if items are added/deleted externally. If you experiment strange issues, just press F5 key to make it update everything.

I’m very happy with the way this advanced. I needed to create another class: KSortFilterProxyModel. The main reason is that QSortFilterProxyModel only provides one lessThan() method, and we need mainly two kind of lessThan() methods, one for building categories and creating them, and another to sort items into categories itself.

I am going to continue my work on Dolphin too, to make the rest of sortings work, as right now, the only sortings implemented are by Name and by Size.

It is still pending the class renaming, since I cannot find a better name, and this one could work, but so many people suggested me to rename it. As I have said more times: KListView is a QListView really. It only adds functionality. But you can show a list view (and I mean a list view, not an icon view) with KListView without any problems. Just as you would do with a QListView. From my point of view if KListView is bad named, QListView is also, since it is able (and we use it) for showing a list of icons.

Of course, I’m waiting for your comments, suggestions and whatever ![:)][1] 

 [1]: http://blog.ereslibre.es/wp-includes/images/smilies/icon_smile.gif

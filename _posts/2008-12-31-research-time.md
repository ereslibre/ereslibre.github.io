---
id: 181
title: Research time
date: 2008-12-31T11:53:33+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=181

dsq_thread_id:
  - "1301900591"
categories:
  - KDE Development
---
First of all&#8230; **HAPPY NEW YEAR ALL** !!

I felt I had to do some research&#8230; and I did for couple days till yesterday morning I felt ill as hell. Now, I&#8217;m getting better, and it seems the &#8220;virus&#8221; that hit spain got me too&#8230; Anyway, I&#8217;m winning the battle to my flu.

So, before getting ill, I had a look at Qt&#8217;s signals and slots, and wondered if I could do something similar myself. Well, I called this tiny library &#8220;Ideal&#8221;, and till now it only has signals/&#8221;slots&#8221; (there are no slots, we&#8217;ll see later) and a small timer for testing purposes&#8230;

I don&#8217;t mean this thing to be huge, but I guess I will be working on it from time to time. However, it was a great thing for me seeing it working. The &#8220;bad&#8221; thing: it uses c++0x stuff to work.

Let&#8217;s see a small usage example:

`#include <object.h><br />
#include <iostream>`

`using namespace Ideal;<br />
using namespace Ideal::Core;<br />
using namespace std;`

`class MyObject<br />
: public Object<br />
{<br />
public:<br />
MyObject(Object *object = 0);`

 `IDEAL_SIGNAL(mySignal); // signal with no parameters<br />
IDEAL_SIGNAL(pushed, bool); // signal with a bool parameter<br />
};`

`MyObject::MyObject(Object *object)<br />
: Object(object)<br />
, IDEAL_SIGNAL_INIT(mySignal)<br />
, IDEAL_SIGNAL_INIT(pushed, bool)<br />
{<br />
}`

`class OtherObject<br />
: public Object<br />
{<br />
public:<br />
OtherObject(Object *object = 0);`

 `void receivedSignal(Object *sender);<br />
void buttonPushed(Object *sender, bool param);<br />
};`

`OtherObject::OtherObject(Object *object)<br />
: Object(object)<br />
{<br />
}`

`void OtherObject::receivedSignal(Object *sender)<br />
{<br />
cout << "received a signal ! (from object: " << sender << ")" << endl;<br />
}`

`void OtherObject::buttonPushed(Object *sender, bool param)<br />
{<br />
cout << "button pushed ! (from object: " << sender << " and param " << param << ")" << endl;<br />
}`

`int main(int argc, char **argv)<br />
{<br />
MyObject object;<br />
OtherObject otherObject;<br />
object.mySignal.connect(&otherObject, &OtherObject::receivedSignal);<br />
object.pushed.connect(&otherObject, &OtherObject::buttonPushed);`

 `// simulate that something happened, and see how slots become called<br />
object.mySignal.emit();<br />
object.pushed.emit(true);<br />
object.pushed.emit(false);<br />
object.pushed.disconnect(&otherObject, &OtherObject::buttonPushed);<br />
object.pushed.emit(true); // this two calls won't have any effect (no "slots" called)<br />
object.pushed.emit(false);<br />
object.mySignal.emit();`

 `return 0;<br />
}`

This is the general look of this stuff&#8230; the pros:

  * Signal/Slot type safe at compile time, not runtime.
  * No external tool like &#8216;moc&#8217; needed for signals to work (also a weak point, see later)
  * You know in which order &#8220;slots&#8221; will become called. Planned also a way to &#8220;reorder&#8221; the way they will. At this very moment, they are called in the exact order they are connected.
  * Slightly faster than Qt&#8217;s signal/slot callings (based on a test that was doing 1.000.000 calls).
  * Don&#8217;t know if a strong point: there is no slot concept. They are callbacks, you can call the method you want using signals without mattering if it was declared as a slot or not. I can see the use case where you would have expect something to have been a slot but it isn&#8217;t, so you can&#8217;t call it easily with Qt&#8217;s signals/slots.

Weak points:

  * Tiny tool. At this very moment, this library only contains a timer and the signal/&#8221;slot&#8221; thingy.
  * Because no tool like &#8216;moc&#8217; is needed, I haven&#8217;t got that cool meta object information that Qt has.
  * It uses a new feature from c++0x.

The philosophy:

  * Won&#8217;t be public until I have something more to show.
  * One-way-of-doing-it principle. Will try to KISS by letting the library user doing a certain thing in a certain way.
  * Correction. As everything&#8230; on the real paper this is much more difficult than in the theory 🙂
  * There is no interest in having this library built with old compilers and other systems than GNU/Linux (or better said, POSIX compliant). I mean, we all can get a free operating system which builds this library, so I don&#8217;t find the reason for making this library build for, say Solaris 2. However, the way it is going to be written allows it to be also expandable for other operating systems. Based on conditional d pointers where there is a d pointer for system doing the nasty job behind the cool scenes of the nice API.
  * C++ on steroids usage.
  * Obviously, this will be free software. At this very moment I have licensed the very small work as (LGPLv3), but well, I need to really study better all the licenses and decide.
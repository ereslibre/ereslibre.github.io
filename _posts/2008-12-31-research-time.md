---
title: Research time
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=181
categories: kde
---
First of all… **HAPPY NEW YEAR ALL** !!

I felt I had to do some research… and I did for couple days till yesterday morning I felt ill as hell. Now, I’m getting better, and it seems the “virus” that hit spain got me too… Anyway, I’m winning the battle to my flu.

So, before getting ill, I had a look at Qt’s signals and slots, and wondered if I could do something similar myself. Well, I called this tiny library “Ideal”, and till now it only has signals/”slots” (there are no slots, we’ll see later) and a small timer for testing purposes…

I don’t mean this thing to be huge, but I guess I will be working on it from time to time. However, it was a great thing for me seeing it working. The “bad” thing: it uses c 0x stuff to work.

Let’s see a small usage example:

`#include 
#include `

`using namespace Ideal;
using namespace Ideal::Core;
using namespace std;`

`class MyObject
: public Object
{
public:
MyObject(Object *object = 0);`

` IDEAL_SIGNAL(mySignal); // signal with no parameters
IDEAL_SIGNAL(pushed, bool); // signal with a bool parameter
};`

`MyObject::MyObject(Object *object)
: Object(object)
, IDEAL_SIGNAL_INIT(mySignal)
, IDEAL_SIGNAL_INIT(pushed, bool)
{
}`

`class OtherObject
: public Object
{
public:
OtherObject(Object *object = 0);`

` void receivedSignal(Object *sender);
void buttonPushed(Object *sender, bool param);
};`

`OtherObject::OtherObject(Object *object)
: Object(object)
{
}`

`void OtherObject::receivedSignal(Object *sender)
{
cout 

---
id: 11
title: kuiserver becomes smarter
date: 2007-01-23T19:19:52+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=11

dsq_thread_id:
  - "1301900243"
categories:
  - Archived
  - KDE Development
---
Hi all,

Well yes&#8230; despite I haven&#8217;t got free time (exams !!) I&#8217;ve done an attempt to make kuiserver smarter. All the improvement comes when you have an own job that inherits KJob, for example, MyFancyKJob, and that we have MyFancyKJob *myFancyKJob somewhere on your code.

You know on some part of your application you can do something like

> `Observer::self()->newJob(myFancyKJob, true /* make it visible */);<br />
Observer::self()->addAction(myFancyKJob, i18n("Start computing"), this, SLOT(computeMySelf(KJob*)));<br />
Observer::self()->addAction(myFancyKJob, i18n("Take me a drink"), this, SLOT(takeMyDrink(KJob*,int)));`

If you take a look to the observer header, you will notice the signal emitted have 1 KJob* and 2 int parameters. First one is the job that contains the action that was performed, second is the actionId of the action performed, and third the jobId. So you know at every moment which action was performed.

So on your program you can go:

> `void MyFancyApplication::computeMySelf(KJob *job)<br />
{<br />
MyFancyKJob *thisJob = static_cast<MyFancyKJob*>(job);<br />
thisJob->somethingSpecial();<br />
}<br />
void MyFancyApplication::takeMyDrink(KJob *job, int actionId)<br />
{<br />
MyFancyKJob *thisJob = static_cast<MyFancyKJob*>(job);<br />
if (actionId == myStoredAction)<br />
thisJob->anotherSpecialThing();<br />
else<br />
thisJob->anotherSpecialThing2();<br />
}`

I&#8217;m committing this stuff next monday, tuesday or whenever the bic day is 🙂

---
id: 343
title: Dynamic slugs on Rails 3
date: 2012-05-16T05:03:34+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=343

dsq_thread_id:
  - "1301903611"
dsq_needs_sync:
  - "1"
categories:
  - Rails
  - Ruby
---
**UPDATE: I gemified this code, and you can now find the &#8216;inferred_slug&#8217; gem ([rubygems](http://rubygems.org/gems/inferred_slug), [github](https://github.com/ereslibre/inferred_slug)).**

## Abstract

Slugs have typically been stored in databases. At least that is what I read about slugs. It turns out that I am starting an amazing Rails project, which is pretty complex, and I want to keep it simple, stupid. So, I am setting up some facts:

  * slugs are used for mainly two reasons:
  * secure accesses, repelling information fetching scripts that just increment an id.
  * prettify URI&#8217;s.

  * slugs are actually duplicated information:
  * duplicated information is **never** good. Even if you have amazing callbacks, like those that ActiveRecord provides.
  * you need to take care of keeping them updated. Forget a callback, and your slugs will be outdated. Inconsistent.
  * update the &#8216;no-brainer-logic&#8217; that creates your slugs, and you need to &#8216;migrate&#8217; your whole database, full of information. If you want to be consistent, of course. And I really expect you to be.

From my point of view, and when thought about this issue yesterday, it was a no-brainer that slugs need to **be logic**, **not data.** So, here is my take on the problem.

Please, note that for correctly running this example you need the <span class="lang:default decode:true  crayon-inline">stringex</span> gem, that adds some neat features to Ruby strings (among other nice candy).

## Prettify URI&#8217;s

First of all, and the easiest part. Let&#8217;s prettify all URI&#8217;s. Let&#8217;s make it global for keeping the point (obviously you could decide on which models you want this).

<pre class="lang:ruby decode:true" title="project/lib/slug.rb">module Slug

  def slug
    if not respond_to? :name or name.empty?
      id
    else
      "#{id}-#{name}".to_url
    end
  end

  def to_param
    slug
  end

end</pre>

Ok, this is a no brainer. If there is a <span class="lang:default decode:true  crayon-inline">name</span> attribute on your model, it will be used to prettify your URI&#8217;s. It&#8217;s important to note that the returned string contains the <span class="lang:default decode:true  crayon-inline">id</span> at the beginning, followed by a dash, and whatever you want after that, in this case, the name. This will be explained later.

This way you can also reimplement <span class="lang:default decode:true  crayon-inline">slug</span> method on your model, if your model instead of <span class="lang:default decode:true  crayon-inline">name</span> contains a <span class="lang:default decode:true  crayon-inline ">title</span> column, that you want to show on the slug.

Now, let&#8217;s write an initializer that loads this directly on all your <span class="lang:default decode:true  crayon-inline">ActiveRecord::Base</span> instances:

<pre class="lang:ruby decode:true" title="project/config/initializers/slug.rb">class ActiveRecord::Base
  include Slug
end</pre>

That&#8217;s it ! Now, you might be wondering why it works at all. You did not change any code on your controllers that call, for example, <span class="lang:default decode:true  crayon-inline">Model.find</span>, and they are still able to find the record, when the passed parameter is <span class="lang:default decode:true  crayon-inline">14-john-murray</span>. Well, test on an irb session what returns <span class="lang:default decode:true  crayon-inline">&#8217;14-john-murray&#8217;.to_i</span> before continuing.

Yes, it returns <span class="lang:default decode:true  crayon-inline">14</span>. This is the reason why our slugs are of the form <span class="lang:default decode:true  crayon-inline">id-whatever-you-want-here</span>. <span class="lang:default decode:true  crayon-inline">&#8220;#{id}-whatever-you-want-here&#8221;.to_i</span> , where <span class="lang:default decode:true  crayon-inline ">id</span>  is an integer, will return that integer. We can still use a regular ActiveRecord find method !

We can still follow the links on our website; **but** ! Not everything is so cool. <span class="lang:default decode:true  crayon-inline">/users/14-john-murray</span>, for instance. Try to point directly to <span class="lang:default decode:true  crayon-inline">/users/14-john-doe</span>. It loads. It just fetches the id (14) and there are no checks about the rest of the slug. So it&#8217;s time to fix that. We made URI&#8217;s pretty, but we aren&#8217;t checking that <span class="lang:default decode:true  crayon-inline">14-john-murray</span> is our record with ID <span class="lang:default decode:true  crayon-inline ">14</span> , whose name should be <span class="lang:default decode:true  crayon-inline">John Murray</span>.

##  Protect yourself !

The first brain inner war that comes here is **where** to place this logic, and **how**. Let&#8217;s state some requirements that were basic:

  * This point should not exist, really. This should be crystal clear, but just in case. **Obey MVC**. No hacks.
  * We need to keep <span class="lang:default decode:true  crayon-inline">find</span> method virgin. We&#8217;d like to still use it.
  * We don&#8217;t like to copy and paste code. We really do **love kitties**.

The controller looks like a nice place at a first sight. However you depend on your developer to remember that he/she needs to validate the slug somehow. Doesn&#8217;t look so nice now. The model cannot know anything about the controller. However, the model is given the whole <span class="lang:default decode:true  crayon-inline">id</span> by the controller. There we go.

Let&#8217;s modify our simple slug initializer then:

<pre class="lang:default decode:true" title="project/config/initializers/slug.rb">class ActiveRecord::Base
  include Slug
end

module YourApplication
  module SlugFinders
    def find_by_slug(*args)
      record = find(*args)
      if record and record.respond_to? :slug
        return nil unless record.slug == args.first
      end
      record
    end

    def find_by_slug!(*args)
      find_by_slug(*args) or raise ActiveRecord::RecordNotFound
    end
  end
end

class ActiveRecord::Base
  extend YourApplication::SlugFinders
end</pre>

Okay, great. We added two methods that we can use to search. <span class="lang:default decode:true  crayon-inline">find_by_slug</span>, and <span class="lang:default decode:true  crayon-inline  crayon-selected">find_by_slug!</span>, following the usual Rails convention.

The idea is really easy. Let&#8217;s focus on <span class="lang:default decode:true  crayon-inline">find_by_slug</span>, since <span class="lang:default decode:true  crayon-inline">find_by_slug!</span> contains the exact same logic from the point of view that we are interested in. First, let&#8217;s do a regular find call, that will return (or not) the record. Let&#8217;s suppose we got a record. If that record responds to the <span class="lang:default decode:true  crayon-inline ">:slug</span> message, we just check that its slug is the same as the one that the model was asked for.

## Wrapping up

So, we can do now things like:

  * <span class="lang:default decode:true  crayon-inline">Client.find_by_slug &#8216;1&#8217; => nil</span>
  * <span class="lang:default decode:true  crayon-inline">Client.find_by_slug &#8216;1-john-doe&#8217; => Client(&#8230;)</span>
  * <span class="lang:default decode:true  crayon-inline">Client.find_by_slug &#8216;1-alice-smith&#8217; => nil</span>
  * <span class="lang:default decode:true crayon-inline">Client.first.payments.find_by_slug &#8216;1&#8217; => nil</span>
  * <span class="lang:default decode:true crayon-inline">Client.first.payments.find_by_slug &#8216;1-niceproduct&#8217; => Payment(&#8230;)</span>
  * <span class="lang:default decode:true crayon-inline  crayon-selected">Client.first.payments.find_by_slug &#8216;1-fakeproduct&#8217; => nil</span>

We got lots of things for free (yeah, as in free beer):

  * Avoid data replication. It sounds so wrong, and feels even worse&#8230;
  * Avoid database headaches.
  * Save space in our database. Sounds stupid, right ?
  * Our logic controls the whole slug system. Change your slug logic, and magically all of them change.
  * Little impact in our project source code.

I hope this post was useful to you. Please take into account that is just an example. If someone asks for it, I can create an empty rails project showing how it works.

Happy coding !
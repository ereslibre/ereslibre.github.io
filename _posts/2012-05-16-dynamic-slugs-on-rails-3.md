---
title: Dynamic slugs on Rails 3
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=343
categories: ruby rails
---
**UPDATE: I gemified this code, and you can now find the ‘inferred_slug’ gem ([rubygems][1], [github][2]).**

 [1]: http://rubygems.org/gems/inferred_slug
 [2]: https://github.com/ereslibre/inferred_slug

## Abstract

Slugs have typically been stored in databases. At least that is what I read about slugs. It turns out that I am starting an amazing Rails project, which is pretty complex, and I want to keep it simple, stupid. So, I am setting up some facts:

*   slugs are used for mainly two reasons:
*   secure accesses, repelling information fetching scripts that just increment an id.
*   prettify URI’s.

*   slugs are actually duplicated information:
*   duplicated information is **never** good. Even if you have amazing callbacks, like those that ActiveRecord provides.
*   you need to take care of keeping them updated. Forget a callback, and your slugs will be outdated. Inconsistent.
*   update the ‘no-brainer-logic’ that creates your slugs, and you need to ‘migrate’ your whole database, full of information. If you want to be consistent, of course. And I really expect you to be.

From my point of view, and when thought about this issue yesterday, it was a no-brainer that slugs need to **be logic**, **not data.** So, here is my take on the problem.

Please, note that for correctly running this example you need the stringex gem, that adds some neat features to Ruby strings (among other nice candy).

## Prettify URI’s

First of all, and the easiest part. Let’s prettify all URI’s. Let’s make it global for keeping the point (obviously you could decide on which models you want this).

    module Slug
    
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
    
    end

Ok, this is a no brainer. If there is a name attribute on your model, it will be used to prettify your URI’s. It’s important to note that the returned string contains the id at the beginning, followed by a dash, and whatever you want after that, in this case, the name. This will be explained later.

This way you can also reimplement slug method on your model, if your model instead of name contains a title column, that you want to show on the slug.

Now, let’s write an initializer that loads this directly on all your ActiveRecord::Base instances:

    class ActiveRecord::Base
      include Slug
    end

That’s it ! Now, you might be wondering why it works at all. You did not change any code on your controllers that call, for example, Model.find, and they are still able to find the record, when the passed parameter is 14-john-murray. Well, test on an irb session what returns ’14-john-murray’.to_i before continuing.

Yes, it returns 14. This is the reason why our slugs are of the form id-whatever-you-want-here. “#{id}-whatever-you-want-here”.to_i , where id  is an integer, will return that integer. We can still use a regular ActiveRecord find method !

We can still follow the links on our website; **but** ! Not everything is so cool. /users/14-john-murray, for instance. Try to point directly to /users/14-john-doe. It loads. It just fetches the id (14) and there are no checks about the rest of the slug. So it’s time to fix that. We made URI’s pretty, but we aren’t checking that 14-john-murray is our record with ID 14 , whose name should be John Murray.

##  Protect yourself !

The first brain inner war that comes here is **where** to place this logic, and **how**. Let’s state some requirements that were basic:

*   This point should not exist, really. This should be crystal clear, but just in case. **Obey MVC**. No hacks.
*   We need to keep find method virgin. We’d like to still use it.
*   We don’t like to copy and paste code. We really do **love kitties**.

The controller looks like a nice place at a first sight. However you depend on your developer to remember that he/she needs to validate the slug somehow. Doesn’t look so nice now. The model cannot know anything about the controller. However, the model is given the whole id by the controller. There we go.

Let’s modify our simple slug initializer then:

    class ActiveRecord::Base
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
    end

Okay, great. We added two methods that we can use to search. find\_by\_slug, and find\_by\_slug!, following the usual Rails convention.

The idea is really easy. Let’s focus on find\_by\_slug, since find\_by\_slug! contains the exact same logic from the point of view that we are interested in. First, let’s do a regular find call, that will return (or not) the record. Let’s suppose we got a record. If that record responds to the :slug message, we just check that its slug is the same as the one that the model was asked for.

## Wrapping up

So, we can do now things like:

*   Client.find\_by\_slug ’1′ => nil
*   Client.find\_by\_slug ’1-john-doe’ => Client(…)
*   Client.find\_by\_slug ’1-alice-smith’ => nil
*   Client.first.payments.find\_by\_slug ’1′ => nil
*   Client.first.payments.find\_by\_slug ’1-niceproduct’ => Payment(…)
*   Client.first.payments.find\_by\_slug ’1-fakeproduct’ => nil

We got lots of things for free (yeah, as in free beer):

*   Avoid data replication. It sounds so wrong, and feels even worse…
*   Avoid database headaches.
*   Save space in our database. Sounds stupid, right ?
*   Our logic controls the whole slug system. Change your slug logic, and magically all of them change.
*   Little impact in our project source code.

I hope this post was useful to you. Please take into account that is just an example. If someone asks for it, I can create an empty rails project showing how it works.

Happy coding !

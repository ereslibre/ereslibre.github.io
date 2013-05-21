---
title: realtime-validations rails gem
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=326
categories: rails ruby
tags: gem rails realtime-validations ror ruby validations
---
There is a new gem in the Rails world: [realtime-validations][1].

 [1]: https://rubygems.org/gems/realtime-validations "realtime-validations"

It provides automatic realtime validations on your forms based on the validations set on the model.

The idea is to ask on every ‘blur’ event on every field of the form to the server whether this field is correct or not, creating a new model or finding the row if it contains an id.

This way you don’t need to replicate logic in your client that is already defined and implemented in your model at the server.

You can read more about [realtime-validations here][2]. You can also [find the project on github][3].

 [2]: http://rubydoc.info/gems/realtime-validations/frames
 [3]: https://github.com/ereslibre/realtime-validations

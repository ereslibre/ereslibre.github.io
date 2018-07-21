---
id: 326
title: realtime-validations rails gem
date: 2012-01-04T22:34:22+00:00
author: ereslibre
layout: post
guid: http://blog.ereslibre.es/?p=326

dsq_thread_id:
  - "1301904313"
categories:
  - archived
  - Rails
  - Ruby
tags:
  - gem
  - rails
  - realtime-validations
  - ror
  - ruby
  - validations
---
There is a new gem in the Rails world: <a title="realtime-validations" href="https://rubygems.org/gems/realtime-validations" target="_blank">realtime-validations</a>.

It provides automatic realtime validations on your forms based on the validations set on the model.

The idea is to ask on every &#8216;blur&#8217; event on every field of the form to the server whether this field is correct or not, creating a new model or finding the row if it contains an id.

This way you don&#8217;t need to replicate logic in your client that is already defined and implemented in your model at the server.

You can read more about [realtime-validations here](http://rubydoc.info/gems/realtime-validations/frames). You can also [find the project on github](https://github.com/ereslibre/realtime-validations).
